# CORSの設定

CORSは、クロスオリジンリソース共有（Cross-Origin Resource Sharing）の略です。 オリジンとは別のドメインにあるWebサーバーであり、リソースは画像、PDF、HTMLファイルなど、サーバーに保存されているアセットです。 別のオリジンに保存されているリソースを要求する必要がある場合があります。 これはクロスオリジン要求と呼ばれ、Webサーバーにはそのような要求を許可または拒否するポリシーがあります。

たとえば、ブラウザ自体は、[クロスサイトスクリプト](https://en.wikipedia.org/wiki/Cross-site_scripting)攻撃を軽減するために、スクリプトからのクロスオリジンAJAXスタイルの要求を許可していません。 これらのAPIは*同一オリジン*のポリシーに従います。 ただし、特定のリソースについては、Liferay DXPがそれらを異なるオリジンに提供できるようにすると便利な場合があります。

たとえば、Docs & Mediaで画像を管理している場合、それらに対してクロスオリジン要求を許可することができます。 Liferay Portalの一致するURLまたはJAX-RSアプリケーションリソースに対してCORSを有効にできます。

## Liferay DXPサービス用にCORSを有効にする

設定は、[Configuration] → [System Settings] → [Security] → [Security Tools] → [Portal Cross Resource Origin Sharing (CORS)]にあります。

1.  *[Add]* をクリックして構成エントリを作成します。

2.  フォームのフィールドに入力します。 完了したら、* [保存]* をクリックします。

    ![図1：CORSのシステム設定は、LiferayサービスのCORSヘッダーを構成する方法を提供します。](./setting-up-cors/images/01.png)

### ポータルCORS構成リファレンス

| 構成                        | 説明                                                                                                                                                                                                                |
| :--- | :--- |
| **有効**                    | エントリを有効にするには、このボックスをオンにします。                                                                                                                                                                                       |
| **Name**                  | 構成エントリに名前を付けます。                                                                                                                                                                                                   |
| **URL Pattern**           | プラスボタンを使用して、必要な数のパターンを追加します。 共有するリソースへのURLと一致するパターンを定義します。 たとえば、ナレッジベースアプリケーションに多くの添付ファイルがある場合、パターン<br> `/knowledge_base/*` <br>を定義できます。これにより、以下の応答ヘッダーで設定したポリシーに適用できるように、ナレッジベースに格納されているリソースが定義されます。 |
| **CORS Response Headers** | プラスボタンを使用して、必要な数のヘッダーを追加します。 ここで、[CORSヘッダー](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers#CORS)に対しポリシーを定義します。                                                                                         |
CORS を設定するには、設定ファイルを使用することもできます。

## JAX-RSアプリケーション用にCORSを有効にする

設定は、[Configuration] → [System Settings] → [Security] → [Security Tools] → [Web Contexts Resource Origin Sharing (CORS)]にあります。

1.  *[Add]* をクリックして構成エントリを作成します。

2.  フォームのフィールドに入力します。 完了したら、* [保存]* をクリックします。

    ![図2：CORS Webコンテキストには、個別のシステム設定カテゴリがあります。](./setting-up-cors/images/02.png)

### JAX-RS CORS構成リファレンス

| 設定                                  | 説明                                                                                                                                                                                                                                                                                                                                                                            |
| :--- | :--- |
| **Dynamic Web Context OSGi Filter** | LDAPスタイルの[フィルター](https://osgi.org/specification/osgi.cmpn/7.0.0/service.http.whiteboard.html)を定義して、このエントリーのCORSヘッダーが適用されるJAX-RSホワイトボードアプリケーションを定義します。 デフォルトのフィルターは<br> `(&(!(liferay.cors=false))(osgi.jaxrs.name=*))` <br>です。このフィルターは、CORSヘッダーを、`liferay.cors=false` プロパティなしでデプロイされたすべてのJAX-RSホワイトボードアプリケーションに適用します。 これは開発時に役立ちますが、本番環境では可能な限り狭い構成を使用してください。 |
| **URL Pattern**                     | プラスボタンを使用して、必要な数のパターンを追加します。 アクセスするWebサービスへのURLに一致するパターンを定義します。                                                                                                                                                                                                                                                                                                               |
| **CORS Response Headers**           | プラスボタンを使用して、必要な数のヘッダーを追加します。 ここで、[CORSヘッダー](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers#CORS)に対しポリシーを定義します。                                                                                                                                                                                                                                                     |
JAX-RS開発者は、 `@CORS` アノテーションを使用して、デプロイされたアプリケーションのポリシーを設定できます。

## 追加情報

  - [Securing Liferay](../../securing-liferay.md)
  - [Introduction to Securing Web Services](../securing-web-services.md)
