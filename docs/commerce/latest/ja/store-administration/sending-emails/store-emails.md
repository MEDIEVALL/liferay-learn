# ストアメール

Liferay Commerceは、さまざまな店舗イベントによってトリガーされるメール通知を送信するように構成できます。 テンプレートはカスタマイズ可能で、メールの内容を定義します。 単一のイベントを設定して、さまざまな対象者（顧客、販売代理店、管理者）にメールを送信し、各当事者に固有のテンプレートを使用できます。

```{note}
   Liferay Commerceの通知機能を使用するには、最初にLiferay Digital Experience Platform（DXP）のメール設定を構成します。 詳細は、 [メールサーバーへの接続](https://learn.liferay.com/dxp/latest/ja/installation-and-upgrades/setting-up-liferay/configuring-mail/connecting-to-a-mail-server.html) を参照してください。
```

<a name="configuring-store-email-notifications" />

## ストアメール通知の構成

Liferay Commerceのメール設定が構成されたら、 ［**コントロールパネル**］ &rarr; ［**コマース**］ &rarr; ［**チャネル**］ に移動して、ストアのメール通知設定を作成します。 メール通知は [チャネル](../../starting-a-store/channels/introduction-to-channels.md)ごとに構成されます。 使用 [加速器](../../starting-a-store/accelerators.md) あなたが開始するための店、カタログ、およびチャネルを作成します。

![利用可能な通知テンプレート](./store-emails/images/02.png)

<a name="event-triggers" />

## イベントトリガー

メール通知をトリガーできるイベントは10個あります。 対応する標準の通知テンプレートの1つを使用して、標準化されたメール通知を作成します。

| 通知タイプ                 | イベント                                         |
| :--- | :--- |
| 注文済み                  | ストアは注文を受けました。                                |
| 注文処理                  | ストアは注文の処理を開始しました。                            |
| 発送待ちの注文               | 注文の発送準備が整いました。                               |
| 部分的に出荷された注文           | アイテムが個別に発送される場合は、お客様に通知されます。                 |
| 発送済み                  | 注文は発送されました。                                  |
| 注文完了                  | 注文が完了しました。お届けしました。                           |
| サブスクリプションが更新されました     | サブスクリプション（定期注文）が更新されました。                     |
| サブスクリプションがアクティブになりました | サブスクリプションがアクティブになりました。                       |
| サブスクリプションが一時停止されました   | サブスクリプションは、ストアによる保留中のレビューまたはアクションを一時停止しています。 |
| サブスクリプションがキャンセルされました  | サブスクリプションはキャンセルされました。                        |

![利用可能な通知テンプレート](./store-emails/images/01.png)

<a name="viewing-the-notification-queue" />

## 通知キューの表示

チャネルの **通知キュー** ですべてのメール通知を表示できます。 ここでは、イベントによってトリガーされたメールのステータスを確認できます。

![メッセージキュー](./store-emails/images/03.png)

デフォルトでは、システムは未送信の通知がないか15分間隔で通知キューをチェックします。 チェック間隔の変更の詳細は、 [コマース通知キュー](./configuring-the-commerce-notification-queue.md) 設定の記事を参照してください。

<a name="customizing-an-email-notification-template" />

## メール通知テンプレートのカスタマイズ

独自のテキストとプレースホルダー値を使用して通知テンプレートをカスタマイズし、 **Email Settings** および **Body** フィールドのキー値を置き換えることができます。 キーの値には、顧客の名前、注文ID、配送先と請求先の住所、注文のアイテムのリストが含まれます。

たとえば、「**Email Body**」フィールドには次のものが含まれます。

```
[%ORDER_CREATOR%]様、

お客様のご注文 ［%ORDER_ID%］ は ［%ORDER_SHIPPING_ADDRESS%］に出荷されました。
```

変数は、メールの送信時に関連するコンテンツに置き換えられます。

詳細は、 [通知テンプレート変数リファレンスガイド](./notification-template-variables-reference-guide.md) 記事を参照してください。

<a name="viewing-order-communications-history" />

## 注文通信履歴の表示

注文に関連するメール通知は追跡され、注文を表示するときに［**Emails**］タブで確認できます。 ［**コントロールパネル**］ → ［**コマース**］ → ［**注文**］ に移動します。 注文IDをクリックし、次に［**Email**］タブをクリックします。 詳細は、 [注文情報](../../orders-and-fulfillment/orders/order-information.md) を参照してください。

![メッセージログは注文情報にあります。](./store-emails/images/04.png)

<a name="additional-information" />

## 追加情報

* [通知テンプレートの使用](./using-notification-templates.md)
* [コマース通知キューの構成](./configuring-the-commerce-notification-queue.md)
* [通知テンプレート変数リファレンスガイド](./notification-template-variables-reference-guide.md)
