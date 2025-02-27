# 変更の作成と公開

パブリケーションツールは、DXPインスタンスのバージョン公開設定を管理するための便利な方法を提供します。 このツールを使用して、チームは、準備ができたときにまとめて公開できる並列ブロックに変更内容をまとめてグループ化する複数の*パブリケーション*を作成できます。

公開設定エクスペリエンスを向上させるために、パブリケーションを使用してインスタンスに変更を加えて公開する方法を学習します。

  - [変更のためのパブリケーションの作成](#creating-a-publication-for-your-changes)
  - [単一のパブリケーションに変更を加える](#making-changes-on-a-single-publication)
  - [並行パブリケーションに変更を加える](#making-changes-on-parallel-publications)
  - [パブリケーションの変更の確認](#reviewing-publication-changes)
  - [変更内容の公開](#publishing-your-changes)

## 変更のためのパブリケーションの作成

変更を追跡するためのパブリケーションをまだ作成していない場合は、[Publications]バーのドロップダウンメニューで*[新規公開を作成]* をクリックします。

![[Publications]バーのドロップダウンメニューで[新規公開を作成]をクリックします。](./making-and-publishing-changes/images/01.png)

*[新規公開を作成]* ページにリダイレクトされます。このページで、新しいパブリケーションの名前と説明を設定できます。 詳細は、[パブリケーションの作成と管理](./creating-and-managing-publications.md)を参照してください。

## 単一のパブリケーションに変更を加える

インスタンスに変更を加える前に、本番環境や別のパブリケーションではなく、正しいパブリケーションで作業していることを確認してください。 これは、現在のパブリケーション名が表示されている[Publications]バーで確認できます。

目的のパブリケーションで作業していない場合は、*[公開を選択]* をクリックして、正しいパブリケーションを選択してください。

![[公開を選択]をクリックして、作業するパブリケーションを選択します。](./making-and-publishing-changes/images/02.png)

追跡可能な場合、インスタンス上のWebコンテンツ、ドキュメント、およびページに加えられた変更は、現在のパブリケーションの変更履歴のリストに追加されます。 各パブリケーションはインスタンスに範囲指定されているため、変更履歴は複数のサイトにまたがることがあります。 同じパブリケーション内の異なるサイトを編集する場合、すべての変更履歴は、パブリケーションの公開時に本番環境に適用されることに注意してください。

パブリケーションを使用すると、複数のユーザーが同じパブリケーションに変更を加えて、それらの変更をまとめて公開できます。 また、さまざまなパブリケーションで並行して作業し、それらの変更を本番環境に個別に公開することもできます。

### アセットの追加と編集

パブリケーションでアセットを追加、編集、または削除すると、変更内容は、アセットが作成されたパブリケーションとパブリケーションの*[変更の確認]* ページでのみ表示されます。 それらは、本番環境または別のパブリケーションのユーザーには表示されません。 各アプリケーションは、アセットのどの部分をパブリケーションで追跡できるかを制御します。

### アセットの表示

パブリケーションの一部として、アセットがウィジェットにどのように表示されるかを編集することもできます。 パブリケーションをサポートしていないアプリケーションやコンテンツタイプに関連するウィジェットも、ページの一部としてパブリケーションに追加できます。

### アセットの削除

パブリケーション内のアセットを削除すると、DXPはアセットに削除のマークを付け、パブリケーションを表示するときにそのアセットを非表示にします。 パブリケーションでのアセットの削除は論理的な削除にすぎないため、アセットは本番環境やその他のパブリケーションで引き続き表示できます。

## 並行パブリケーションに変更を加える

2つのパブリケーションが同じベースラインで作成されると、それらは並行パブリケーションになります。 ユーザーは、これらの並行パブリケーションに変更を加えて、インスタンスエンティティの代替編集履歴を作成できます。 これらの変更は、同じコンテンツを変更するか関連するコンテンツを変更するかに応じて、互換性がある場合と競合する場合があります。

### 互換性のある変更

並行パブリケーションに互換性のある変更が含まれている場合、問題なく公開できます。 この場合、両方のパブリケーションの変更履歴が本番環境に適用されます。

### 競合する変更

ユーザーがパブリケーションで変更を作成しているときに本番環境が更新されると、公開設定プロセス中に競合が発生する可能性があります。 ユーザーが現在のバージョンの本番環境と互換性のない変更を含むパブリケーションを公開しようとすると、競合する変更が通知されます。 これらの通知には、各競合の原因が表示されており、自動または手動で解決できます。

本番環境が直接更新される場合、これらの変更はインスタンスのパブリケーション履歴の一部として追跡されません。 パブリケーションの作成後に本番環境を変更すると、本番環境が直接変更されたか、別のパブリケーションで変更されたかに関係なく、パブリケーションの競合が発生する可能性があります。 このプロセスの詳細は、[競合の解決](./resolving-conflicts.md)を参照してください。

## パブリケーションの変更の確認

公開する前に、パブリケーションの変更履歴を確認します。 これを行うには、[Publications]バーのドロップダウンメニューで*[変更の確認]* を選択します。

![[Publications]バーのドロップダウンメニューで[変更の確認]をクリックします。](./making-and-publishing-changes/images/03.png)

または、[Publications]概要ページの*[進行中]* タブで、パブリケーションの変更履歴を確認できます。 確認するパブリケーションの*アクション*ボタン（![Actions button](../../../images/icon-actions.png)）をクリックし、*[変更の確認]* を選択して、選択したパブリケーションに含まれるすべての変更を表示します。

### シンプルで高度な変更の概要

デフォルトでは、DXPはパブリケーションの変更履歴の簡単な要約を表示しますが、トグルスイッチを*[すべての項目を表示]* に設定して、変更に関連するすべてのプロセスを表示できます。

*[すべての項目を表示]* が有効になっている場合、個々の変更をクリックすると、その変更に関連するすべてのプロセスを含む詳細が表示されます。 追跡する変更の*アクション*ボタン（![Actions button](../../../images/icon-actions.png)）をクリックして、*[編集]* または*[破棄]* に切り替えることができます。

### 表示スタイル

ここでは、*変更*と*コンテキスト*の2つの表示スタイル間を切り替えることもできます。

  - **変更**：すべての変更履歴が一覧で表示され、*変更の種類*、*編集日時*、*サイト*、*タイトル*、または*ユーザー*でソートできます。

    ![変更履歴をリストに表示します。](./making-and-publishing-changes/images/04.png)

  - **コンテキスト**：すべての変更がツリー内に表示され、それぞれの変更を相対的なコンテキストで確認できます。

    ![変更履歴をコンテキストで表示します。](./making-and-publishing-changes/images/05.png)

## 変更内容の公開

変更作業が完了したら、すぐに公開するか、後で公開するようにスケジュールすることができます。 公開されると、パブリケーションは編集できず、それ以上の変更を追加することはできません。 これにより、明確な監査証跡が維持され、必要に応じて最新の変更のみをロールバックできます。

ただし、[Publications]ページの*[履歴]* タブからパブリケーションを簡単に*元に戻す*ことができます。 ここから、パブリケーションに含まれている変更を確認し、選択したパブリケーションによって行われた変更を元に戻す変更が既に含まれている新しいパブリケーションを作成できます。 詳細は、[変更を元に戻す](./reverting-changes.md)を参照してください。

### 今すぐ公開

変更をすぐに公開するには、本番環境に公開するパブリケーションにいることを確認してください。 次に、*[Publications]* バーのドロップダウンメニューで*[公開]* をクリックします。

![[Publications]バーのドロップダウンメニューで[公開]をクリックします。](./making-and-publishing-changes/images/06.png)

または、*[Changes]* ページに移動し、*[公開]* をクリックして、パブリケーションを公開することもできます。

DXPは競合検出を実行して、競合する変更があるかどうかを確認します。 競合が検出された場合、DXPは、自動的に解決されたすべての競合と、手動による解決が必要な競合があるかどうかを通知します。 すべての競合が解決されるまで、公開を進めることはできません。 このプロセスの詳細は、[競合の解決](./resolving-conflicts.md)を参照してください。

すべての競合が解決されたら、*[公開]* をクリックして、変更を本番環境で公開できます。 *[公開]* をクリックすると、[Publications]ページの*[履歴]* タブにリダイレクトされ、日付、発行者、ステータスなどのパブリケーションの詳細を確認できます。 ここで、変更を元に戻すこともできます。 詳細は、[変更を元に戻す](./reverting-changes.md)を参照してください。

### 後でスケジュールする

変更を後で公開するには、本番環境に公開するパブリケーションにいることを確認してください。 次に、*[Publications]* バーのドロップダウンメニューで*[スケジュール]* をクリックします。

![[Publications]バーのドロップダウンメニューで[スケジュール]をクリックします。](./making-and-publishing-changes/images/07.png)

または、パブリケーションの*[Changes]* ページに移動し、*[スケジュール]* をクリックして公開することもできます。

DXPは予備的な競合検出を実行して、既存の競合があるかどうかを確認します。 競合がない場合、またはすべての競合が解決されている場合は、変更を公開する日時を設定できます。

![変更を公開する日時を設定します。](./making-and-publishing-changes/images/08.png)

公開時に、DXPは2回目の競合検出を実行して、新たな競合する変更がないことを確認します。 DXPが自動的に解決できない新しい競合を検出すると、公開は失敗します。 競合を自動的に解決できる場合、DXPは公開を続行します。

## 追加情報

  - [Publications Overview](../publications.md)
  - [Enabling Publications](./enabling-publications.md)
  - [パブリケーションの作成と管理](./creating-and-managing-publications.md)
