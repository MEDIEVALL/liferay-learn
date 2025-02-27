# インスタンス設定

インスタンス設定は、仮想インスタンスの外観から利用規約まで、ユーザーが最初にサインインするときに同意する仮想インスタンスの構成情報を定義します。 コントロールパネルの*[設定]* → *[Instance Settings]* のセクションからインスタンス設定にアクセスし、*[プラットフォーム]* の下の *[インスタンス設定]* カテゴリを選択します。 インスタンス設定には、次の4つのエントリが含まれています。

| 構成    | 目的                                         |
| :--- | :--- |
| 外観    | デフォルトのロゴと全体的なルックアンドフィールを定義します              |
| 連絡先情報 | インスタンスの物理アドレス、メールアドレス、Webサイト、および電話番号を設定します |
| 一般    | ランディングページ、法的情報、およびその他の詳細を指定します             |
| 利用規約  | インスタンスのカスタム利用規約を提供します                      |

## 外観

外観設定エントリは、仮想インスタンスのデフォルトのロゴと全体的なルックアンドフィールを定義します。 これは、[ロゴ]セクションと[ルック&フィール]セクションで編成されています。

**ロゴ：**デフォルトのロゴを変更し、*[Allow site administrators to use their own logo?]* チェックボックス（デフォルトでは有効）をオン/オフにして、サイト管理者がサイトを構成するときにロゴをアップロードできるかどうかを指定します。 新しいロゴを設定するときは、スペースに合う画像ファイルを選択するように注意してください。 大きな画像はナビゲーションと重なる場合があります。

**ルックアンドフィール：**インスタンスとコントロールパネルのデフォルトのテーマを設定します。

![仮想インスタンスの外観を設定します。](./instance-configuration/images/01.png)

## 連絡先情報

連絡先情報設定エントリは、仮想インスタンスを所有している組織に連絡する方法を指定します。 これはいくつかのセクションに分かれています：

**アドレス：**組織のプライマリ、郵送、配送、私書箱 などのアドレスを指定します。

**電話番号：**組織のFAX、ローカルなどの電話番号を提供します。

**追加メールアドレス：**組織に関連付けられている追加のメールアドレスを指定します。

**Webサイト：**組織の公開Webサイトや社内ポータルWebサイトを指定します。

開発者は、アプリケーションでこの連絡先情報を照会できます。 プラスボタンとマイナスボタンをそれぞれ使用して、セクション内のエントリを追加したり削除したりできます。

![仮想インスタンスの連絡先情報を設定します。](./instance-configuration/images/02.png)

## 一般

一般エントリは、仮想インスタンスの構成情報、ランディングページ、および関連する組織の基本的な法的情報を指定します。 2つのセクションがあります。

**メイン設定：**仮想インスタンスの次の情報を設定します。

  - 仮想インスタンスの実行を担当するエンティティの名前を設定します。
  - メールアドレスのドメインを設定します。
  - バーチャルホストを設定します。
  - 静的リソースを提供するように構成されたCDNにURLを設定します。

**Navigation：** 仮想インスタンスのホームページと、デフォルトのランディングページおよびログアウトページを設定します。 これらのページを設定するには、ドメインに続くページの相対URLを使用します。 たとえば、`http://localhost:8080/web/guest/login`にデフォルトのランディングページを設定するには、`/web/guest/login`を使用します。 アドレスの一部として変数 `${liferay:screenName}` を使用して、ログイン時にユーザーを個人ページにリダイレクトできます。 たとえば、ユーザー `marvin` の個人ページへのデフォルトのURLは次のようになります。

``` bash
http://localhost:8080/user/marvin
```

ログイン時にそこに誘導されるようにするには、[ログインページ]フィールドに `/user/${liferay:screenName}` を入れます。 これらのURLは、`portal-ext.properties`ファイルの中で、システムスコープで設定することもできます。

``` properties
default.landing.page.path=
default.logout.page.path=
company.default.home.url=
```

すべての仮想インスタンスは、プロパティファイルで指定された値を共有します。 インスタンス設定で行われた変更は、プロパティファイルで設定された値を上書きします。 詳細については、[Portal Properties documentation](https://docs.liferay.com/ce/portal/7.3-latest/propertiesdoc/portal.properties.html)を参照してください。

**追加情報：** 仮想インスタンスの所有者の正式名称、ID、会社タイプ、SICコード、証券シンボル、業界、および業界タイプを指定します。

![仮想インスタンスの一般情報を設定します。](./instance-configuration/images/03.png)

## 利用規約

[利用規約]ページはデフォルトで有効になっているため、最初のアクションの1つとして、プレースホルダー規約を無効にするか置き換える必要があります。 すべてのユーザーが利用規約を読むという要件を無効にしたり、利用規約を含むWebコンテンツ記事のグループIDと記事IDを設定したりできます。 いずれにせよ、利用規約エントリには、ユーザーの利用規約を設定するために必要なすべてのものが含まれています。

![仮想インスタンスの利用規約を設定します。](./instance-configuration/images/04.png)

グループIDは、Webコンテンツを含むサイトのIDです。

グループ/サイトIDを見つけるには、

1.  *[サイトメニュー]* → *[設定]* → *[Settings]* に移動します。

2.  [一般]タブで[サイトID]フィールドを見つけます。 それを[グループID]フィールドに入力します。

![サイト設定のサイトID（20125）は、利用規約設定のグループIDです。](./instance-configuration/images/05.png)

Webコンテンツ記事のIDを見つけるには、

1.  *[サイトメニュー]* → *[Content & Data]* → *[Webコンテンツ]* に移動します。

2.  利用規約の記事をクリックします。 そのIDは、画面右側の[Properties]パネルの[Version and Workflow Status]の下に表示されます。

![編集画面にWebコンテンツ記事のID（37808）が表示されます。](./instance-configuration/images/06.png)

設定を保存します。 初めてサインインするすべてのユーザーには、利用規約の記事が表示されます。 ユーザーは、ユーザーアカウントを登録するために、利用規約に同意する必要があります。
