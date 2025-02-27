# DXP CloudでのSSOの使用

お客様はSAML 2.0準拠のシングルサインオンIDプロバイダーを使用して、DXP Cloudプラットフォームに対してユーザーを認証できます。 このドキュメントでは、この統合を有効にするプロセスについて詳しく説明します。

SAMLを使用してSSOを実行するには、クライアント、サービスプロバイダー（SP）、アイデンティティプロバイダー（IdP）の3つのエージェントが必要です。 クライアントがサービスプロバイダーに接続しようとすると、サービスプロバイダーはクライアントをアイデンティティプロバイダーにリダイレクトします。 クライアントがIDプロバイダーによって認証された後、IDプロバイダーはクライアントの資格情報へのアクセスをサービスプロバイダーに許可します。

このシナリオでは、DXP Cloudはサービスプロバイダーとして機能します。 DXP Cloudにログインしようとしているお客様がクライアントです。 IDプロバイダーは、顧客が管理するエンタープライズディレクトリソリューションです。

## DXP CloudプロジェクトのSSOの有効化

DXP CloudプロジェクトでSSOを有効にするには、次の手順を実行する必要があります。

1.  [IdPメタデータをDXP Cloudチームに提供する](#provide-identity-provider-metadata-to-the-dxp-cloud-team)
2.  [DXP Cloudチームは提供されたIdPデータをインポートし、サービスプロバイダー（SP）メタデータを提供します](#dxp-cloud-team-imports-provided-idp-data-and-provides-service-provider-metadata)
3.  [Liferay DXP Cloudチームが提供するSPメタデータをインポートする](#import-sp-metadata-provided-by-the-liferay-dxp-cloud-team)

### IDプロバイダーメタデータをDXP Cloudチームに提供する

DXP CloudプロジェクトでSSOを有効にしたいクライアントは、次の情報を含む必要がある **IdP** システムのメタデータを提供する必要があります。

| フィールド                              | 説明                                                                                                                            |
| :--- | :--- |
| IdP発行者                             | 通常、 `EntityDescriptor` メタデータの `EntityID` 属性                                                                                   |
| IdPシングルサインオンURL                    | SAML認証要求（例：受信するリクエストエンドポイント [http://adfs.customer.com/saml/sso）を](http://adfs.customer.com/saml/sso))                         |
| IdP署名証明書                           | SAMLメッセージおよびアサーション署名へのIdPの公開鍵証明書                                                                                              |
| IdPシングルサインオンHTTPメソッド（リクエストバインディング） | 認証要求を受信するために顧客のIDプロバイダーによってサポートされるHTTPメソッド。 有効な回答は `POST` （デフォルト）と `GET`のみです。                                                 |
| 署名リクエスト                            | お客様のIDプロバイダーに送信されたSAMLリクエストに署名する必要がある場合は、 `TRUE` 設定します。 それ以外の場合は `設定FALSE`                                                    |
| 署名アルゴリズムのリクエスト（RSA）                | `Sign Requests` が `TRUE`設定されている場合は、要求の署名に使用されるアルゴリズムを提供します。 現時点では、SHA-1（非推奨）およびSHA-256をサポートしています。 要求の署名が無効になっている場合、この設定は不要です。 |

#### ADFS固有の情報

Microsoft ADFSを使用するクライアントは、SAMLを使用してSSOを設定するために必要な次の設定に注意する必要があります。

| フィールド           | 説明                                                                           |
| :--- | :--- |
| IdP発行者URI       | [全般]タブの *フェデレーションサービス識別子* にあり、デフォルト値は <http://domain/adfs/services/trust>です。 |
| IdPシングルサインオンURL | デフォルト設定は `/ adfs/ls`です。 例： <http://adfs.example.com/adfs/ls/>                |
| IdP署名証明書        | DERエンコードされたバイナリX.509証明書ファイル                                                  |

IdPメタデータが生成されたら、 [DXP Cloudチームでチケットを開きます](https://help.liferay.com/hc/)。 IdP のメタデータは XML ファイルまたは URL エンドポイント（<https://localhost:8080/c/saml/metadata> が基本的な例です）の形式で送信することができます。

### DXP Cloudチームは提供されたIdPデータをインポートし、サービスプロバイダーのメタデータを提供します

DXP Cloudチームは、次のSPメタデータ値をクライアントに提供します。

| フィールド                    | 説明                                                                                                   |
| :--- | :--- |
| アサーションコンシューマサービス（ACS）URL | DXP Cloudが受信したSAML応答。 これは常に [からのアドレスサーバーになりますhttps://auth.liferay.cloud](https://auth.liferay.cloud) |
| オーディエンスURL               | 顧客のIDプロバイダーにアクセスするために使用されるURL Liferay Cloud                                                          |

### Liferay DXP Cloudチームが提供するSPメタデータをインポートする

DXP CloudチームからSPメタデータを受け取ったら、SPメタデータ値をIdPに入力します。

## SSOの使用

SSOを使用してDXP Cloudにログインするには：

1.  <https://console.liferay.cloud/login> に移動します。

2.  [ *SSO経由でログイン*]クリックします 。

    ![ログインページ](./using-sso-with-dxp-cloud/images/01.png)

3.  *組織ID* フィールドに **会社名** 入力します。

4.  [ *続行*]クリックします。

    > **注：** 組織のSSOで既に認証されている場合は、次の手順を実行する必要がない場合があります。

5.  *Email Address* フィールドに **Email Address** 入力します。 これは、会社のデータベースまたはディレクトリサービス（LDAPやADFSなど）に保存されているメールアドレスと同じである必要があります。

6.  *パスワード* フィールドに **パスワード** 入力します。 これは、会社のデータベースまたはディレクトリサービスに保存されているメールアドレスに関連付けられているパスワードと同じである必要があります。

7.  [ *ログイン*]をクリックします。

ログインすると、ユーザーはすべてのプロジェクトと環境を確認できます。

![プロジェクトページ](./using-sso-with-dxp-cloud/images/02.png)
