# 検索結果のフィルタリング

カスタムフィルターを使用すると、メインの検索クエリにクエリを提供し、検索結果をフィルタリングして、検索結果ウィジェットで返される結果を制御できます。 フィルターウィジェットを表示または非表示にして、変更可能か不変かを決定できます。

![カスタムフィルターを適用して、特定の検索結果を除外します。](./filtering-search-results/images/03.png)

カスタムフィルターを検索ページに組み込むことで満足できる多くの使用例があります。

とりあえず、以下の基本的な使用法を検討してください。

| 使用事例                                                                      | `構成` *（値）*                                                                                                                                    |
| :--- | :--- |
| **ユーザータイトルフィルター：** エンドユーザーは、フィルターキーを直接操作して、タイトルを使用して結果を探していたものに絞り込みます     | `フィルターフィールド` *（title \ _en \ _US）* <br /> `フィルター値` *（ポッドキャスト）* <br /> `フィルタークエリタイプ` *（一致）* <br /> `発生タイプ` *（必須\ _not）* |
| **ハードコード化されたフィルタリング：** 管理ユーザーは、エンドユーザーには表示されず変更できないフィルターを使用して検索ページを構成します。 | ***上記の構成に追加*** <br /> `` *（True-チェック済み）* <br /> `不変` *（True-チェックあり）*                                                              |

カスタムフィルターは非常に多くのことを実行でき、それらすべてをリストすることは不可能です。 以下はウィジェット設定ツアーです。

## カスタムフィルターの追加

カスタムフィルターウィジェットのすべてのオプションを調べるには、ページに1つ必要です。

1.  ページの[追加]メニュー（![Add](../../../images/icon-add-widget.png)）を開き、[ウィジェット]セクションを展開します。

2.  [検索]セクションから、カスタムフィルターをページにドラッグします。

![カスタムフィルターは、構成するまで影響がありません。](./filtering-search-results/images/01.png)

## カスタムフィルター構成

検索結果のフィルタリングを開始するには、ウィジェットのオプションメニュー（![Options](../../../images/icon-app-options.png)）を開き、[ *構成*]をクリックします。

**フィルターフィールド（テキスト）：** ほとんどの場合、フィルターは特定のフィールドに作用します。 フィルタリングするインデックス付きフィールドの名前を設定します（たとえば、 `title`）。 [フィルタークエリタイプ]が、フィールドを必要としないタイプ（ *Regexp*など）に設定されている場合、これは必要ありません。

クエリ文字列とスクリプトクエリでは、フィルターフィールドを設定する必要はありません。 他のすべてのクエリには、少なくとも1つのフィールドが必要です。

<!--Note: Multi Match and Simple Query String take an array of fields according to the Elasticsearch docs, but our config doesn't seem to support it. -->

Liferay DXPインデックスに存在するフィールドを見つけるには、コントロールパネルのフィールドマッピングUIで [使用します](#finding-fields)。

**フィルター値（テキスト）：** ほとんどのフィルターでは、指定したフィールドにフィルターを適用するテキストを指定するテキスト値をここに入力する必要があります（たとえば、 *マッチ* クエリをテキスト *ストリート* に設定します `title_en_US` フィールド）。 一部のフィルタークエリタイプでは、 [*Regexp*](https://www.elastic.co/guide/en/elasticsearch/reference/7.x/query-dsl-regexp-query.html) クエリの場合のように、特別な表記が必要です。

**クエリタイプのフィルター（選択リスト）：** 結果をフィルターするクエリタイプを選択します。 使用可能なタイプには、ブール、存在、ファジー、一致、一致フレーズ、一致フレーズプレフィックス、マルチ一致、プレフィックス、クエリ文字列、正規表現、スクリプト、単純クエリ文字列、用語、ワイルドカードが含まれます。

これらのクエリの詳細については、 [Elasticsearchのドキュメント](https://www.elastic.co/guide/en/elasticsearch/reference/7.x/query-dsl.html)ご覧ください。

**発生（選択リスト）：** 検索に提供されるクエリの発生タイプを設定します。 オプションには、Filter、must、must\_not、およびshouldが含まれます。

各タイプを理解するには、 [Elasticsearchのドキュメント](https://www.elastic.co/guide/en/elasticsearch/reference/7.x/query-dsl-bool-query.html)参照してください。

**クエリ名（テキスト）：** 提供されたクエリの名前を設定します。 このフィルターが、子句を提供する別のフィルターに対する親クエリとして機能しない限り、これは不要です。その場合、このフィルターのクエリ名を子フィルターの親クエリ名として設定します。 この親/子動作は、Boolタイプのフィルターでのみ使用できます。

**親クエリ名（テキスト）：** Boolクエリに子句を提供する場合、これを設定して、親カスタムフィルターウィジェットで構成されたクエリ名と一致させます。 それ以外の場合は、空白のままにします。

**ブースト（数値）：** [Boost](https://www.elastic.co/guide/en/elasticsearch/reference/7.x/query-dsl-term-query.html#term-field-params) このクエリに一致する結果のスコア。 ここでは、意味のある整数または10進数を指定します。

常にこれと一致する結果が常に必要な場合は、Boost値を非常に高く設定します（例： *1000*）。

**カスタム見出し（テキスト）：** このフィルターに表示する見出しを入力します。 設定されていない場合、フィルターフィールドの値が表示されます。

**カスタムパラメータ名（テキスト）：** フィルタのURLパラメータ名を指定します。 設定されていない場合、フィルターフィールドの値が使用されます。

**Invisible (boolean)：** チェックすると、ウィジェットは通常のユーザーには表示されません。 構成のフィルター値はデフォルトで適用されますが、ユーザーは引き続きURLパラメーターを介して他の値をフィルターできます。 不変設定（以下を参照）を使用すると、URLパラメータのフィルタリングを防ぐことができます。

**Immutable (boolean):** これを有効にして、通常のユーザーがフィルター値を変更できないようにします。 ウィジェットは非表示になり、** URLパラメーターを介して設定されたフィルター値は受け入れられません。 ウィジェット構成で設定されたフィルター値は、（無効にされていない限り）常に適用されます。

**Disabled (boolean):** チェックすると、クエリは無視され、検索に参加しません。 これにより、フィルターを簡単に停止できますが、構成を保持して後で再度有効にすることができます。

**統合検索キー（テキスト）:** このウィジェットが参加している代替検索のキーを入力します。 設定されている場合、デフォルトのインデックスはまったく検索されないことに注意してください。 設定されていない場合、このウィジェットはデフォルトの検索に参加します。

このフィールドの値は、通常、アプリケーション定義のインデックスの名前と一致します。

## フィールドを見つける

カスタムフィルターウィジェットでフィルターに使用できるフィールドを見つけるために、適切な権限を持つユーザーは *コントロールパネル* → *構成* → *検索*移動できます。 そこから、[フィールドマッピング]タブを開き、 `liferay-[companyId]` インデックスのマッピングを参照します。 マッピングの [`プロパティ`](https://www.elastic.co/guide/en/elasticsearch/reference/current/properties.html) セクションまでスクロールします。

![フィールドマッピングを参照して、Liferay DXPのインデックス付きフィールドを見つけます。](./filtering-search-results/images/04.png)
