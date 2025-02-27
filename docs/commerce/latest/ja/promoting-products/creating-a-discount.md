# 割引を作成する

以下の手順に従って、割引タイプ、対象顧客を選択し、割引率を設定して割引を作成します。 割引が作成されたら、割引の対象となる追加の条件を指定します。

新しい割引を作成するには：

1. ［**グローバルアプリケーション**］ → ［**コマース**］ → ［**割引**］に移動します。
1. （![Add](../images/icon-add.png)）ボタンをクリックして、新しい割引を追加します。
1. 名前を入力します（**スプリングセール**）。
1. ［**適用先**］ ドロップダウンから割引タイプ（たとえば、 ［**小計に適用**］）を選択します。 （さまざまな割引タイプの詳細は、 [割引タイプ](./introduction-to-discounts.md#types-of-discounts) を参照してください。）
1. ［**パーセント**］ または ［**固定金額**］ を、 ［**タイプ**］ ドロップダウンメニューから選択します。

    ![新規割引を作成します。](./creating-a-discount/images/03.png)

1. **Submit** クリックし* 。</p></li> </ol>

<a name="configuring-a-discount" />

## 割引の設定

パーセント（パーセントベースの割引を使用する場合）、最大割引額、 [割引レベル](./introduction-to-discounts.md#tiered-discounts) などの割引の詳細を指定して、有効にすることができます。

詳細セクションには：

1. 次のように入力します：

    ***Amount** ：20%
    ***最大割引額** ：20.00
    ***レベル** ：L1

1. ［**有効**］ トグルを ［**YES**］に切り替えます。

    ![割引率と最大割引額を設定します。](./creating-a-discount/images/04.png)

1. 完了したら、［**公開**］をクリックします。

これで割引が有効になりました。 割引のルールと適合性を設定します。

### クーポンコードの設定

クーポンコードを使用する場合、

1. ［**クーポンコードを使用**］ トグルを ［**はい**］に切り替えます。
1. 次のように入力します：

    ***クーポンコード** : スプリングセール
    ***最大合計使用数** : 1
    ***ユーザーごとの最大使用数** ：1

1. 完了したら、［**公開**］をクリックします。

これでクーポンコードが追加されました。

<a name="adding-rules-to-a-discount" />

## ルールを割引に追加する

割引の対象となる要件を指定するルールを定義できます。 詳細は、 [割引ルール](./introduction-to-discounts.md#discount-rules) を参照してください。

複数のルールを使用する場合は、ルールを集約するか、どれが効果的かを決定することができます。決定するには、 **And** または **Or** ラジオボタンのいずれかをクリックします。

新しい割引ルールを追加するには：

1. ルールが作成されたら、 ［**ルール**］ のセクションまでスクロールダウンします。
1. （![Add icon](../images/icon-add.png)）ボタンをクリックして、新しい割引ルールを追加します。
1. 名前を入力します： **スプリングセール** 。
1. ［**ルールタイプ**］ ドロップダウンメニューから ［**カートの合計金額**］を選択します。

    ![新規割引ルールを作成します。](./creating-a-discount/images/05.png)

1. **Submit** クリックし* 。</p></li>
1 ［**スプリングセール**］ をクリックして、ルールを設定します。
1
［**カートの合計最小金額**］フィールドに15.00と入力します。

    ![カートの合計最低金額フィールドに値を入力します。](./creating-a-discount/images/06.png)

1

［**保存**］ をクリックします。
1 ウィンドウを閉じます。</ol>

割引ルールが設定されました。

<a name="configure-discounts-eligibility-rules" />

## 割引の適格性ルールを設定する

この割引は、すべてのアカウント、特定のアカウント、またはアカウントグループに使用できるようにすることができます。

この割引の対象となるアカウントとアカウントグループを指定するには、次の手順に従います：

1. ［**適合性**］ タブをクリックします。
1. [［アカウントグループを選択］](../users-and-accounts/account-management/creating-a-new-account-group.md) ラジオボタンをクリックします。
1. ［**アカウントを追加する**］ の検索バーで、目的のアカウントグループを検索します。この例では、 **US Accounts East** となっています。
1. ［**選択**］ をクリックして、アカウントグループを追加します。

    ![この割引の対象となるアカウントグループを選択してください。](./creating-a-discount/images/07.png)

1. 完了したら、［**公開**］をクリックします。

この割引は、すべてのチャネルまたは特定のチャネルで利用できるようにすることができます。 この割引の対象となるチャネルを指定するには、次の手順に従います:

1. ［**適合性タブ**］で、 ［**特定のチャネル**］ラジオボタンをクリックします。
1. ［**チャネルの追加**］ 検索バーで、目的のチャネルを検索します。
1. ［**選択**］ をクリックして、チャネルを追加します。

    ![割引の対象となる希望のチャネルを選択します。](./creating-a-discount/images/08.png)

1. 完了したら、［**公開**］をクリックします。

ストアでは、指定されたアカウントグループの商品を対象に、選択した商品に20%割引が適用されるようになりました。

<a name="commerce-21-and-below" />

## Commerce 2.1以前

割引を作成するには：

1. ［**コントロールパネル**］ → ［**コマース**］ → ［**割引**］に移動します。
1. （![Add](../images/icon-add.png)）ボタンをクリックして、新しい割引を追加します。
1. 名前を入力します（**スプリングセール**）。
1. **ターゲット** ドロップダウンから割引タイプ（たとえば、 **小計** 適用）を選択します。 （さまざまな割引タイプの詳細は、 [割引タイプ](./introduction-to-discounts.md#types-of-discounts) を参照してください。）
1. この割引が適用されるチャネルのボックスをオンにします。
1. この割引が適用される [アカウントグループ](../users-and-accounts/account-management/creating-a-new-account-group.md) を選択します。 この例では、 **US East Coast** 。
1. クーポンコードを使用する場合は、［**クーポンコードを使用** を **はい** に切り替えます。 次に、「**カップルコード**」フィールドにコードを入力します。 それ以外の場合は、 **NO** ままにします 。
1. パーセンテージを使用する場合は、 **Use Percentage** トグルを **Yes** に切り替えます。
1. **最大割引額** 入力：$ 20.00
1. [_Level_](./introduction-to-discounts.md#tiered-discounts) ：20.00と入力し
 。 これにより、小計から20％オフになります。</li> 
   
   1 ［**Active**］ トグルを ［**YES**］に切り替えます。
  
  ![新しい割引](./creating-a-discount/images/01.png)

1 ［**公開**］をクリックします。</ol> 

ストアでは、指定されたアカウントグループの商品を対象に、選択した商品に20%割引が適用されるようになりました。



### 割引ルールの追加

1. 割引が作成されると、［**Detail**］および［**ルール**］の2つのタブが用意されます。 ［**ルール**］タブをクリックします。
   
   ![割引ルールタブ](./creating-a-discount/images/02.png)

1. （![Add icon](../images/icon-add.png)）ボタンをクリックして、新しい割引ルールを追加します。

1. ［**タイプ**］ ドロップダウンメニューから ［**Cart Total**］を選択します。
1. ［カートの合計最小金額］フィールドに15.00と入力します。
1. ［**保存**］ をクリックします。

この例では、この特定の割引に割引ルールが適用されました。 顧客は、設定された金額を超えるすべての購入に対してこの割引を受けます。



<a name="additional-information" />

## 追加情報

* [割引について](./introduction-to-discounts.md)
* [新規アカウントグループの作成](../users-and-accounts/account-management/creating-a-new-account-group.md)
* [価格表の作成](../managing-a-catalog/managing-prices/creating-a-price-list.md)
* [価格レートを使う](../managing-a-catalog/managing-prices/using-price-tiers.md)
