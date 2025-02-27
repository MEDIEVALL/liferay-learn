# 個人サイトの管理

デフォルトでは、Liferay DXPで作成されたすべてのユーザーには、パブリック（プロフィール）ページとプライベート（ダッシュボード）ページで構成される、自分だけがメンバーである個人サイトが生成されます。 この動作が望ましくない場合、このユーザーごとの個人サイトは[簡単に無効](#customizing-personal-sites-with-portal-properties)にできます。

## プロフィールページとダッシュボードページ

ユーザーの個人サイトのパブリックページ（プロフィール）は、ブログ（ブログエントリウィジェットを介して）やアクティビティ（アクティビティウィジェットを介して）など、ユーザーが公開したいものに使用できるため、他のユーザーが自分の近況を確認できます。 デフォルトでは、ユーザーに関する基本情報が表示され、ユーザーの連絡先情報をダウンロードするためのvCard（仮想名刺）へのリンクが提供されます。

![プロフィールページには、連絡先情報など、他のユーザーが閲覧できる公開情報が表示されます。](./managing-personal-sites/images/01.png)

ユーザーの個人サイトのプライベートページ（ダッシュボード）を使用して、プライベートファイルリポジトリ（ドキュメントとメディアウィジェットから）やパーソナライズされたRSSフィード（RSSリーダーウィジェットから）などの個人情報を表示したり、所属するサイト（マイサイトウィジェットから）や管理している組織などの項目を管理したりできます。

![ダッシュボードページには、所属するサイトなど、自分にだけ表示される個人情報が表示されます。](./managing-personal-sites/images/02.png)

## 個人サイトページの管理

個人サイトのページにアクセスするには、次の手順に従います。

1.  個人用メニューアイコンを開き、*[My Profile]* または *[My Dashboard]* を選択します。

    ![個人用メニューから個人サイトページにアクセスします。](./managing-personal-sites/images/03.png)

2.  プロダクトメニューを開き、サイトメニューから*[サイトビルダー]* → *[Pages]* に移動します。

3.  [ウィジェットページ](../creating-pages/using-widget-pages/adding-widgets-to-a-page.md)と同じようにページを管理します。

    ```{tip}
    [Public Pages]メニューと[Private Pages]メニューを切り替え、ページの[アクション]メニューから*View*オプションを選択することで、[ページ]ページから[ダッシュボード]ページと[Profile]ページを切り替えることができます。
    ```

ユーザーグループを介して、ユーザーの個人サイトのページを追加および定義することもできます。 詳細は、[ユーザーグループサイト](../../users-and-permissions/user-groups/user-group-sites.md)を参照してください。

## 個人サイトの権限とロール

個人用サイトの権限とロールは、以下に示す動作に従います。

  - ユーザーは、個人サイトのサイト管理者として機能します。個人サイトのページやアプリケーションを変更できます。
  - 管理者は、ロールから権限を削除することにより、Liferay Portalの権限システムを介して個人サイトの変更可能な部分をカスタマイズできます（ユーザーロールから関連する権限を削除することにより、すべてのユーザーが何も変更できないようにします）。

## ポータルプロパティを使用した個人サイトのカスタマイズ

個人サイトのデフォルトページをカスタマイズするために、[`portal-ext.properties`](../../installation-and-upgrades/reference/portal-properties.md)に追加できるポータルプロパティがいくつかあります。 ページの名前、ページに表示されるアプリケーション、ページのテーマとレイアウトテンプレートなどをカスタマイズできます。 詳細は、`portal.properties`ファイルの[Default User Public Layouts](https://docs.liferay.com/dxp/portal/7.3-latest/propertiesdoc/portal.properties.html#Default%20User%20Public%20Layouts)および[Default User Private Layouts](https://docs.liferay.com/dxp/portal/7.3-latest/propertiesdoc/portal.properties.html#Default%20User%20Private%20Layouts)セクションを参照してください。 これらのプロパティの一部を以下の表に示します。

| 機能                          | プロパティ                                           |
| :--- | :--- |
| 個人サイトを無効にする                 | `layout.user.public.layouts.enabled=false`      |
| 個人サイトのプライベートページを無効にする       | `layout.user.private.layouts.enabled=false`     |
| 個人サイトの自動作成を無効にする            | `layout.user.public.layouts.auto.create=false`  |
| 個人サイトでのプライベートページの自動作成を無効にする | `layout.user.private.layouts.auto.create=false` |

個人サイトのパブリックページセットとプライベートページセットは別々に処理されます。 一方のページセットを有効のままにして、もう一方を無効にすることができます。 最初にインスタンスに対してユーザーの個人サイトを有効にしてから無効にした場合、既存の個人サイトは、次にユーザーがサインインするまでインスタンスに残り、その時点で削除されます。
