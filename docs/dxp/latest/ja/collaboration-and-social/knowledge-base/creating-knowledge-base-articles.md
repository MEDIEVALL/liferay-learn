# ナレッジベース記事の作成

ナレッジベースアプリには、記事のリポジトリを作成するために必要なすべてのものが含まれています。 記事の作成は、アプリのWYSIWYGエディターで作成するか、ZIPアーカイブ内のMarkdownファイル（`.markdown`、`.md`）からインポートして行うことができます。 以下のセクションでは、記事を作成する両方の方法について説明します。

```{note}
サイト管理でナレッジベースにアクセスするには、ロールに*サイト管理*の*ナレッジベース* > [Access]へのアクセス権限が必要です。 記事、フォルダー、または提案を追加または操作するには、サイト管理者はナレッジベースの[権限設定]ウィンドウを使用して適切なアクセス許可を付与する必要があります。 
```

ナレッジベースアプリに移動するには、 *メニュー*アイコン（![Menu icon](../../images/icon-menu.png)）をクリックし、 *[コンテンツとデータ]* → *[ナレッジベース]* に移動します。 ナレッジベースアプリには、次の3つのタブがあります。

**記事:** 記事とフォルダーを作成および管理します。

**テンプレート:** テンプレートを作成および管理します。

**候補:** ユーザーが投稿した記事のフィードバックを管理します。

![ナレッジベースアプリには、タブからアクセスできるさまざまなセクションがあります。](./creating-knowledge-base-articles/images/01.png)

## エディターでの記事の作成

1.  [記事]タブで、*追加*アイコン（![Add icon](../../images/icon-add.png)）をクリックし、*[基本記事]* をクリックします。

    ![記事を書くための新しいウィンドウが表示されます](./creating-knowledge-base-articles/images/02.png)

2.  記事のタイトルを入力します。 指定したタイトルのURLセーフバージョンが、記事のフレンドリURLの最後に追加されます。 フレンドリURLは、[設定]セクションの[フレンドリURL]フィールドで管理できます。

3.  WYSIWYGエディターを使用して、記事のコンテンツを作成します。 記事のHTMLソースを表示または編集するには、エディターの*[ソース]* ボタンをクリックします。 エディターの下のセクションを使用して、添付ファイルとタグを追加し、関連するアセットを指定し、記事の権限を設定します。 デフォルトでは、表示権限はゲストロールに付与されます。つまり、誰でも記事を表示できます。

4.  *[Publish]* をクリックして記事を公開するか、*[下書きとして保存]* をクリックして後で作業を続けることができます。 ナレッジベースのワークフローを有効にしている場合は、公開する前に記事を承認する必要があることに注意してください。

記事が保存されると、ナレッジベースのHTMLに自動的に変換されます。 記事は[記事]タブのテーブルに表示されます。

## ナレッジベース記事のインポート

また、Markdown形式（`.markdown`、`.md`）の記事を含むZIPアーカイブから記事をインポートして、新しいナレッジベースの記事を作成することもできます。 たとえば、お気に入りのMarkdownエディターで記事を作成し、それらをZIPファイルにパッケージ化してから、そのZIPファイルをインポートして、ナレッジベースにそれらの記事を作成できます。 ナレッジベースでは、ファイル名の数字の接頭辞によって記事に優先順位を付けることもできます。 例えば、ナレッジベースでは、`01-article.markdown`と`02-article.markdown`が数字の接頭辞（`01`、`02`）の昇順で一覧表示されます。 記事の優先順位については、ナレッジベースのインポーターの詳細情報に関する[ナレッジベース記事の管理](managing-the-knowledge-base.md#managing-knowledge-base-articles)を参照してください。

  - [Importing Knowledge Base Articles](importing-knowledge-base-articles.md)
  - [Knowledge Base ZIP File Requirements](knowledge-base-zip-file-requirements.md)
  - [Knowledge Base Importer FAQs](knowledge-base-importer-faq.md)

<!-- end list -->

```{note}
記事をインポートするには、ロールに[ナレッジベース] → [リソース権限: 記事をインポートする]へのアクセス許可が必要です。
```

記事をナレッジベースにインポートするには、

1.  [記事]タブで、*追加*アイコン（![Add icon](../../images/icon-add.png)）をクリックし、*[インポート]* をクリックします。

    ![この新しいページにZIPファイルをアップロードします。](./creating-knowledge-base-articles/images/03.png)

2.  *[Choose File]* をクリックし、インポートするZIPファイルを探します。

3.  ファイルの数字の接頭辞を使用してナレッジベースにインポートされた記事に優先順位を付ける場合は、*[Apply numerical prefixes of article files as priorities]* を選択します。

4.  完了したら、*[保存]* をクリックします。

すべての記事と同様に、インポートされた記事はナレッジベースのHTMLに自動的に変換され、テーブルに一覧表示され、残りの記事は[記事]タブに表示されます。
