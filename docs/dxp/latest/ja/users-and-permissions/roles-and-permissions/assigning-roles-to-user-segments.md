# ユーザーセグメントへのロールの割り当て

> 利用可能:Liferay DXP 7.2 SP2 +、Liferay CE 7.3.1 GA2

ユーザーセグメントは、動的に割り当てられたユーザーコレクションです。 使用可能な基準</a>で

セグメントを明確に定義できる場合、ユーザー管理の管理オーバーヘッドを大幅に削減できます。 さらに、サイトスコープで作成されたユーザーセグメントに対して [パーソナライズされたエクスペリエンス](../../site-building/personalizing-site-experience/personalizing-site-experience.md) を定義して、ユーザーがサイトで最も関連性の高いコンテンツを表示できるようにすることができます。</p> 

| ユーザーセグメントはどこに作成しますか？                    | それらは何のため？                          | セグメントにロールをどこに割り当てますか？       |
| :--- | :--- | :--- |
| サイトセグメント（サイトメニュー→People→セグメント）          | サイトのユーザー向けにパーソナライズされたエクスペリエンスを作成する | サイトメニュー→People→セグメント（アクション） |
| インスタンスセグメント（コントロールパネル→ユーザー→ロール（通常のロール）） | ユーザーとその権限を効率的かつ動的に管理する             | コントロールパネル→ユーザー→ロール（通常のロール）  |




## 通常のロールをユーザーセグメントに割り当てる



> 対応可能：Liferay DXP 7.2 SP2以降

通常のロールは、グローバルスコープで作成されたユーザーセグメントに割り当てることができます。 通常のロールをユーザーセグメントに割り当てるには、

1.  製品メニューを開き、 *[Control Panel]* → *[Users]* → *[Roles]* に移動します。

2.  通常のロールの横にあるアクションメニュー（![Actions](../../images/icon-actions.png)）を開き、[ *Edit*を選択します。
   
   ![ロールを編集して、ユーザーセグメントを割り当てます。](./assigning-roles-to-user-segments/images/01.png)

3.  *[Assignees]* → *[Segments]* タブを選択し、（![Add Button](../../images/icon-add.png)）をクリックしてユーザーセグメントを選択します。
   
   ![[Assignees]の下の[Segments]タブに移動して、ロールを割り当てます。](./assigning-roles-to-user-segments/images/02.png)

4.  既存のユーザーセグメントの横にあるチェックボックスをオンにし、*[Add]* をクリックしてロールを割り当てます。 ユーザーセグメントが存在しない場合は、（![Add Button](../../images/icon-add.png)）をクリックして新しいユーザーセグメントを作成します。
   
   ![ロールを割り当てるユーザーセグメントの横にあるチェックボックスをオンにします。](./assigning-roles-to-user-segments/images/03.png)

ロールの担当者のリストに選択したユーザーセグメントが表示されます。

![ロールの担当者のリストにユーザーセグメントが表示されます。](./assigning-roles-to-user-segments/images/04.png)



## ユーザーセグメントへのサイトロールの割り当て



> 利用可能：Liferay DXP 7.2 SP3 +

[サイトロール](./understanding-roles-and-permissions.md) はセグメントに割り当てることができますが、サイト管理者とサイト所有者の2つの例外があります。

1.  サイトメニュー→People→セグメント（アクション）

2.  セグメントの[アクション]メニュー（![Actions](../../images/icon-actions.png)）を開き、[ *サイトのロールの割り当て*]をクリックします。

3.  セグメントにサイトロールを割り当て、[ *追加*]をクリックします。
   
   ![サイトロールをセグメントに割り当てることができます。](./assigning-roles-to-user-segments/images/05.png)



## 関連情報

  - [ユーザーセグメントの作成](../../site-building/personalizing-site-experience/segmentation/creating-and-managing-user-segments.md)
