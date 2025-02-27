# 評価システムの使用

LiferayDXPのアセットフレームワーク <!-- TODO: 利用可能な場合はアセットフレームワークの記事へのリンクを追加  --> は、ユーザーがコンテンツを評価できるコンテンツの評価システムをサポートしています。 DXPの組み込みコンテンツの種類の多くでは、デフォルトで評価が有効になっています。

## 評価の種類

互換性のあるアセットについては、以下のタイプの評価を追加設定なしで使用できます。

  - **高評価**: コンテンツには、ユーザーがコンテンツに「高評価」を付けるためのボタン（ハートのアイコン）が1つだけあります。 ハートボタンの横に高評価の総数が表示されます。

    ![ユーザーは、「高評価」評価タイプでコンテンツに高評価を付けることができます。](./using-the-ratings-system/images/01.png)

  - **スター**: コンテンツはドロップダウンメニューで1から5のスターで評価されます。 コンテンツのスター評価の総合が横に表示されます。

    ![ユーザーは、「スター」評価タイプで1〜5のスターでコンテンツを評価できます。](./using-the-ratings-system/images/02.png)

  - **山積みの星**: コンテンツは1から5のスターを水平方向に選択して評価されます。 コンテンツのスター評価の総合がユーザー選択の上に表示されます。 この評価タイプと標準のスタータイプの唯一の違いは、画面上での見え方のみです。

    ![ユーザーは、標準のスター評価タイプと同様に、「山積みの星」評価タイプで1〜5のスターでコンテンツを評価できます。](./using-the-ratings-system/images/03.png)

  - **サムズマーク**: コンテンツに「サムズアップ」または「サムズダウン」のいずれかの評価が付きます。 サムズアップまたはサムズダウンの総数は、各サムボタンの横に表示されます。

    ![ユーザーは、「サムズマーク」評価タイプを使用して、コンテンツにサムズアップまたはサムズダウンを付けることができます。](./using-the-ratings-system/images/04.png)

## 評価値の変換

設定可能な評価の種類（高評価、スターなど）の表示方法が異なるため、データベースには、それらが有効になっているアセットに対する正規化された評価値が格納されます。 アセットの評価タイプが変更された場合、評価は変換され、新しいタイプに引き継がれます。

次の表は、各タイプの評価を他のタイプに変換する方法を示しています。

|            | **高評価に変換**                 | **スターに変換**                      | **サムズアップ/ダウンに変換**                    |
| :--- | :--- | :--- | :--- |
| **高評価**    | 変更なし                       | 1高評価 = 5 スター評価                  | 1高評価 = 1サムズアップ                       |
| **スター**    | 3～5個のスター＝ 1高評価、1～2個のスターは省略 | 変更なし                            | 3～5個のスター＝ 1サムズアップ、1～2個のスター ＝ 1サムズダウン |
| **サムズマーク** | 1サムズアップ＝ 1高評価、サムズダウンは省略    | 1サムズアップ＝ 5スター評価、1サムズダウン＝ 1スター評価 | 変更なし                                 |

## コンテンツの評価を有効にする

[サイト設定]メニューからコンテンツの評価を設定できます（サイトごとに個別に）。

サイトメニューから、*[設定]* → *[Settings]* に移動し、*[ソーシャル]* タブをクリックします。 *[評価]* セクションでは、使用可能な各アセットタイプの評価タイプを個別に設定できます。

![[サイト設定]メニューから、アセットタイプごとに特定の評価タイプを設定できます。](./using-the-ratings-system/images/05.png)

また、管理者はコントロールパネルを介して、 *[Instance Settings]*（単一の仮想DXPインスタンス用）または *[システム設定]*（グローバル）のいずれかで、複数のサイト間で特定のウィジェットに対する評価を有効または無効にすることができます。

これらの設定メニューのいずれかから、 *[コンテンツとデータ]* の下で、選択したアセットタイプのアイコンを見つけます（例えば、 *[Blogs]* や*[Wiki]* など）。 次に、*[ウィジェットスコープ]* ヘッダの下にある特定のウィジェットのメニューオプションを選択します（例：*[ウィジェット表示]*）。

![管理者は、複数のサイトにわたるウィジェットの評価を有効または無効にすることもできます。](./using-the-ratings-system/images/06.png)

```{note}
コンテンツの評価をサポートするすべてのウィジェットで、コントロールパネルから評価を有効または無効にできるわけではありません。
``` <!-- TODO: (When developer-oriented article available) You can also enable ratings for your own applications by adding just a few lines of code. See the article on \[adding support for ratings\](link) to your content widgets for more information. --> ## 追加情報

  - [Using the Activities Widget](./using-the-activities-widget.md)
