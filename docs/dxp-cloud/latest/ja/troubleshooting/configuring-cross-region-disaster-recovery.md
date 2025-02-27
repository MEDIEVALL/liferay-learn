
# クロスリージョンディザスタ リカバリの設定

DXP Cloudは、大規模なインシデントの場合にお客様が障害復旧（DR）手順を利用するための2つの方法を提供します：自動障害復旧と地域間障害復旧。 障害復旧シナリオに対するDXP Cloudのアプローチについては、 [障害復旧の概要](./disaster-recovery-overview.md)を参照してください。

この記事では、地域を越えた障害時にお客様が手動でデータを回復するのに必要な手順について説明します。 これらの手順は、同じリージョン内の3つのアベイラビリティーゾーンすべてに同時に妥協がある場合にのみ必要です。

  - [初期設定](#initial-setup)
  - [インシデント中](#during-an-incident)
  - [事故後の回復](#post-incident-recovery)

## 初期設定

ライフレイは、地域間の障害を管理するための専用のDXP Cloud環境を提供します。 この例では、本番環境が *europe-west2* リージョンに格納されており、リージョンが危険にさらされていると想定しています。 本番環境でのダウンタイムとデータ損失を防ぐには、ディザスタリカバリ環境を、 *us-west1*などの運用領域外にシフトする必要があります。 したがって、この5番目の障害復旧（DRに短縮された）環境は、インシデント中に生成された新しいユーザーデータを格納するバックアップとして機能します。

障害復旧環境のセットアップを希望するDXP Cloudのお客様は、DR環境をプロビジョニングするために、まず営業担当者に連絡する必要があります。 この新しい環境は、他の利用可能な環境 (例えば、 `dev`、 `infra`、 `uat`、および `prd`) と一緒にリストアップされています。

![図1：障害復旧環境を作成したら、他の環境と同じようにそれを選択できます。](./configuring-cross-region-disaster-recovery/images/01.png)

DXP Cloudシステム管理者は、DR環境と本番環境の両方に対する完全な管理権限を持っている必要があります。

### DR環境でのVPN設定の確認

本番環境でVPNが有効になっている場合は、DR環境のVPNも有効になっていることを確認してください。

2つの環境が接続されていることを確認するには：

1.  左側のメニューで、DR環境の[ *設定* ]タブをクリックします。

2.  [VPN]セクションで、次のように入力します。

      - **VPNタイプ**：OpenVPN
      - **サーバーアドレス**：サーバーアドレス。
      - **アカウント名**：管理者のメールアドレス。
      - **パスワード**：管理者のパスワード。
      - **証明書**：証明書コード。
      - **転送IP**：転送IPアドレス。
      - **転送ポート**：転送ポート番号。
      - **ローカルホスト名**：VPNのホスト名。
      - **ローカルポート**：ローカルポート番号。

3.  [ *Connect VPN*] をクリックします。

VPNへの接続の詳細は、 [VPN接続](../infrastructure-and-operations/networking/connecting-a-vpn-to-dxp-cloud.md)を参照してください。

### 最新の安定したビルドを本番環境からDR環境にデプロイする

次に、最新の安定したビルドを本番環境でDR環境にデプロイする必要があります。 そのためには、 [DXP Cloud展開ワークフローの概要](../build-and-deploy/overview-of-the-dxp-cloud-deployment-workflow.md)で説明したのと同じ手順に従ってください。

## インシデント中

上記の例を続けて、 *europe-west2* リージョンでホストされている本番環境が、現地時間の午後2時に1時間ごとにバックアップされるようにスケジュールされていると想定します。 このシナリオでは、現地時間の午後2時30分に地域が危険にさらされます。 その間の30分間はバックアップが生成されていないため、データベースとドキュメントのバックアップを本番環境から障害復旧環境に復元する必要があります。 最後の安定した環境は、午後2時に作成されたバージョンです。

### 最新の本番データをDR環境にコピーする

次の手順に従って、本番環境の最新の安定したバックアップをDR環境に復元します。

1.  DR環境で、[ *バックアップ* ]タブをクリックします。

2.  本番環境に対応するタブをクリックします。

    > 注：バックアップ履歴では、バックアップが2つのタブに一覧表示されます。 1つはDR環境用、もう1つは本番環境用です。

3.  [ *アクション* ]ボタン（![Actions](./configuring-cross-region-disaster-recovery/images/03.png)）をクリックして、本番環境の最新の安定したバックアップを取得し、[ *復元*]を選択します。

    ![図2：最新の安定したバックアップを本番環境からDR環境に復元します。](./configuring-cross-region-disaster-recovery/images/04.png)

### カスタムドメイントラフィックをDR環境に送信する

DR環境でのWebサーバーサービスのカスタムドメインは、元の本番環境のものと一致する必要があります。 また、その設定を実稼働環境から削除する必要もあります。 次の手順に従ってください。

1.  DR環境では、左側のメニューで *Services* を選択します。
2.  サービスのリストで *webserver* をクリックします。
3.  [ *Custom Domains* ]タブをクリックし、本番環境のドメインと一致するようにカスタムドメインを設定します。
4.  本番環境で同じ設定に移動し、カスタムドメイン設定を削除します。
5.  DNSレコードを更新します。 詳細は、 [カスタムドメイン](../infrastructure-and-operations/networking/custom-domains.md)を参照してください。

これにより、すべてのトラフィックがDR環境に送られます。

![図3：webserverサービスの場合、DR環境のカスタムドメインを設定して、本番環境のカスタムドメインと一致させます。](./configuring-cross-region-disaster-recovery/images/07.png)

## 事故後の回復

リージョンインシデントが終了したら、元のリージョンの本番環境（この例では*europe-west2* ）に戻す必要があります。 次の手順を実行します：

  - [DR環境で手動バックアップを作成する](#create-a-manual-backup-in-the-dr-environment)
  - [DRから本番環境への手動バックアップの復元](#restore-the-manual-backup-from-dr-to-Production)
  - [本番環境でWebサーバーのカスタムドメインを更新する](#update-the-web-server-custom-domain-in-Production)

### DR環境の手動バックアップを作成する

インシデント中、DR環境は本番環境として機能するため、障害時に生成された新しいデータが含まれます。 このデータを保持するには、DR環境をバックアップする必要があります。 次の手順に従ってください。

1.  DR環境では、左側のメニューで[ *Backups* ]をクリックします。
2.  *[Backup Now]* をクリックします。

![図4：DR環境の手動バックアップを作成します。](./configuring-cross-region-disaster-recovery/images/08.png)

### 最新のDR環境データを本番環境にコピー

1.  DR環境では、左側のメニューで[ *Backups* ]をクリックします。

2.  DR環境に対応するタブをクリックします。

    > **注：** バックアップ履歴では、バックアップが2つのタブに一覧表示されます。 1つはDR環境用で、もう1つは本番環境用です。

3.  最新のバックアップ（作成したばかりのバックアップ）の場合は、[ *アクション* ]ボタン（![Actions](./configuring-cross-region-disaster-recovery/images/03.png)）をクリックし、[ *復元*]を選択します。

4.  本番環境を選択し、[ *Deploy Build*]をクリックします。

![図5：バックアップを運用環境に展開します。](./configuring-cross-region-disaster-recovery/images/09.png)

### サーバーのカスタムトラフィックを本番環境に復元する

インシデント中にWebサーバーサービスがすべてのトラフィックをDR環境にリダイレクトしたため、すべてのトラフィックが元の本番環境にリダイレクトされるように、これらの設定を再度更新する必要があります。

1.  左側のメニューで *Services* に移動します。

2.  サービスのリストで *webserver* クリックします。

3.  [ *Custom Domains* ]タブをクリックします。

    ![カスタムドメインを削除](./configuring-cross-region-disaster-recovery/images/10.png)

4.  本番環境からカスタムドメインを削除します。

5.  DNSレコードを更新します。 詳細は、 [カスタムドメイン](https://help.liferay.com/hc/en-us/articles/360032856292) を参照してください。

6.  [ *Update Custom Domain*]クリックします。

これでトラフィックは元の本番環境に戻され、障害復旧プロセスが終了しました。
