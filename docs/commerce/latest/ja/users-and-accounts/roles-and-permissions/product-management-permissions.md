# 商品管理の権限

Liferay Commerceでは、グローバルメニュー（![Global Menu](../../images/icon-applications-menu.png)）のCommerceタブで、権限を使用して商品管理アプリケーションやリソースへのアクセスを制御することができます。

![商品管理アプリケーションやリソースへのアクセスを制御します。](./product-management-permissions/images/01.png)

ユーザーロールの商品管理権限は、［権限の定義］タブの ［**コマース**］ &rarr; ［**商品管理**］ で管理することができます。 権限を個別に割り当てるか、 **アクション** をチェックして、アプリケーションまたはリソースにすべての権限を割り当てます。

![ [権限の定義]タブで、ユーザーロールの商品管理権限を管理します。](./product-management-permissions/images/02.png)

<a name="application-permissions" />

## アプリケーションの権限

アプリケーションの権限は、アプリケーション自体に権限の機能を付与しますが、 [関連するリソース権限](#resource-permissions) は含まれません。

商品管理には、次のアプリケーションが含まれます：

**カタログ** ：このアプリケーションは、カタログエンティティを作成および管理するために使用されます。

**商品** ：このアプリケーションは、カタログ内の商品エンティティを作成および管理するために使用されます。

**オプション** : このアプリケーションは、商品オプションのテンプレートを作成および管理するために使用されます。

**仕様** : このアプリケーションは、商品仕様を分類するためのラベル、グループ、およびテンプレートを作成するために使用されます。

**Shop by Diagram Admin**(旧称：部品表管理者)：このアプリケーションは、部品表の図の作成および注釈付けに使用されます。

**アプリケーション管理者** : このアプリケーションは、ブランドとそのモデルエントリーを作成および管理するために使用されます。

全ての商品管理アプリケーションには、次の権限があります：

| 権限              | 説明                           |
| :--- | :--- |
| コントロールパネルへのアクセス | グローバルメニューからアプリケーションにアクセスする機能 |
| 設定              | アプリケーションの構成オプションを表示および設定する機能 |
| 権限の設定           | アプリケーションの権限を表示および変更する機能      |
| 詳細設定            | アプリケーションプリファレンスを表示および設定する機能  |
| 表示              | アプリケーションを表示する機能              |

<a name="resource-permissions" />

## リソース権限

リソース権限は、アプリケーションリソースに関連する特定の機能を付与します。 これらの権限の中には、データベースのエンティティ（＝モデルリソース）に対して操作を実行する能力を付与するものもあります。 また、アプリケーションコンテキストでリソース関連の操作を行う能力を付与するものもあります（例えば、新しいリソースエンティティを作成する能力など）。

商品管理アプリケーションは、以下のリソースを参照しています：

**コマースカタログ**（カタログに記載）：これらの権限は、関連する商品の保存と管理に使用されるカタログエンティティの操作を実行する機能を付与します。 各カタログには、デフォルトの言語、通貨、画像、基本価格表、および基本プロモーション表があります。

**コマースカタログ**（カタログに記載されています。以前はコントロールパネル > 通常権限に記載されていました）：これらの権限は、カタログアプリケーションでリソース関連の操作を実行する機能を付与します。

**コマース商品**（商品、オプション、商品仕様ラベルに記載）：これらの権限は、商品エンティティに操作を実行する機能を付与します。 各商品エンティティは、カタログに保管されていて、1つまたは複数の関連するSKUを持っています。 また、リンクされたメディア（画像や添付ファイル）、仕様、カテゴリー、オプション、在庫、価格エントリーなどを含めることも可能です。

**コマース商品・オプション**（カタログに記載）：これらの権限は、商品にカスタムフィールドを追加する時に使われる商品オプションエンティティの操作を実行する機能を付与します。 各オプションには、その動作を決定するフィールドタイプがあります。 オプションはそのタイプによって、顧客からインプットを受けたり、商品のバリエーションのためのSKUを生成したりするために使用されます。

**コマースの商品オプションカテゴリー**（カタログに記載）：これらの権限は、仕様を分類するために仕様される仕様グループである商品オプションカテゴリーエンティティの操作を実行する機能を付与します。

**コマース商品仕様**（カタログに記載）：これらの権限は、商品の属性に関する情報を保管するために使用される商品仕様エンティティの操作を実行する機能を付与します。 それぞれが仕様テンプレートのインスタンスです。

**コマース価格**（商品グループと商品に記載されています。以前は［コントロールパネル］ > ［通常権限］に記載されていました）：これらの権限は、商品グループアプリケーションでリソース関連の操作を実行する機能を付与します。 商品グループエンティティは、関連する商品をグループ化することによって、価格表と割引を簡単に適用できるようにするために使用されます。

**コマース倉庫**（商品、 [出荷](./order-management-permissions.md)、 [倉庫](./inventory-management-permissions.md)の下に表示されています）：これらの権限は、倉庫エンティティの操作を実行する機能を付与します。 各倉庫は商品在庫を保管し、チャネルに接続されており、住所と地理的位置とともに物理的な場所を表しています。

**コマースBOM**（Shop by Diagram Adminに記載されています。以前は［コントロールパネル］ > ［通常権限］に記載されていました）：これらの権限は、Shop by Diagramアプリケーションでリソース関連の操作を実行する機能を付与します。 BOMリソースエンティティは、オブジェクトコンポーネントを商品SKU にマッピングする図です。

**コマースBOMフォルダー**（Shop by Diagram Adminに記載）：これらの権限は、BOM （部品表）の定義を保存するために使用される BOMフォルダエンティティの操作を実行する機能を付与します。 各フォルダにはそれぞれイメージが関連付けられており、アプリケーション管理者で定義されたモデルにリンクすることができます。

**コマースBOMの定義**（Shop by Diagram Adminに記載）：これらの権限は、商品SKUにリンクする注釈付きの図であるBOM定義エンティティの操作を実行する機能を付与します。 各図は、大規模なシステム内で商品SKUが互いにどのように関連しているかを表しています。

**コマースアプリケーション**（アプリケーション管理者に記載されています。以前は［コントロールパネル］ > ［通常権限］に記載されていました）：これらの権限は、アプリケーション管理者でリソース関連の操作を実行する機能を付与します。 これらのリソースには、ブランドエンティティとモデルエンティティが含まれています。

**コマースのアプリケーションブランド**(アプリケーション管理者に記載)：これらの権限は、アプリケーションモデルの保管と整理のために使用されるアプリケーションブランドエンティティの操作を実行する機能を付与します。

**コマースのアプリケーションモデル**（アプリケーション管理者に記載）：これらの権限は、アプリケーションモデルエンティティの操作を実行する機能を付与します。このエンティティは、BOM（部品表）フォルダーとリンクして BOM 図をバージョンごとに整理できるブランドエントリです。 それぞれのモデルには名前と年式があります。

### 標準的なリソース権限

上記のリソースのほとんどには、以下の標準的な権限があります：

| 権限     | 説明                        |
| :--- | :--- |
| 削除     | リソースエンティティを削除する機能         |
| 権限の設定  | リソースエンティティの権限を表示および変更する機能 |
| アップデート | リソースエンティティをアップデートする機能     |
| 表示     | リソースエンティティを表示する機能         |

### ユニークなリソース権限

ただし、コマース商品、コマースカタログ、コマース価格、およびコマースBOMにはユニークな権限があります。

#### コマース商品

| 権限               | 説明                            |
| :--- | :--- |
| コマース商品仕様オプションを追加 | 商品に仕様を追加する機能                  |
| オプションを追加         | 商品にオプションを追加する機能               |
| オプションカテゴリを追加     | 仕様を分類するために商品に仕様グループを追加する機能    |
| 付属品管理            | [メディア]タブで商品の付属品を管理する機能        |
| 画像管理             | [メディア]タブで商品の画像を管理する機能         |
| 計量単位管理           | 個々の商品のエンティティに使用される計量単位を管理する機能 |
| 権限の設定            | 個々の商品エンティティの権限を表示および変更する機能    |
| 価格を見る            | 商品価格エントリーを表示する機能              |
| ルールを表示           | 商品ルールを表示する機能                  |

```{note}
Liferay DXP 7.3以前では、*コマース商品仕様オプションの追加*および*オプションカテゴリーを追加*の権限がコントロールパネル >一般権限に記載されていました。
```

#### コマースのカタログ

| 権限          | 説明                                     |
| :--- | :--- |
| コマースカタログを追加 | カタログアプリケーションでカタログエンティティを作成する機能         |
| 権限の設定       | カタログアプリケーションでカタログエンティティの権限を表示および変更する機能 |
| コマースカタログを表示 | カタログアプリケーションでリソース権限を表示および変更する機能        |

#### コマースの価格設定

| 権限          | 説明                                |
| :--- | :--- |
| コマース価格種類を追加 | 商品グループアプリケーションで価格種類エンティティを作成する機能  |
| 権限の設定       | 商品グループアプリケーションでリソース権限を表示および変更する機能 |

#### コマースBOM

| 権限             | 説明                                           |
| :--- | :--- |
| コマースBOM定義を追加   | Shop by DiagramアプリケーションでBOM定義エンティティを作成する機能   |
| コマースBOMフォルダを追加 | Shop by DiagramアプリケーションでBOMフォルダエンティティを作成する機能 |
| 権限の設定          | Shop by Diagramアプリケーションでリソース権限を表示および変更する機能   |

#### コマースのアプリケーション

| 権限          | 説明                               |
| :--- | :--- |
| コマースブランドを追加 | アプリケーション管理者でブランドエンティティを作成する機能    |
| コマースモデルを追加  | アプリケーション管理者でブランドにモデルエントリーを追加する機能 |
| 権限の設定       | アプリケーション管理者でリソース権限を表示および変更する機能   |

<a name="additional-information" />

## 追加情報

* [商品の概要](../../managing-a-catalog/creating-and-managing-products/products/products-overview.md)
* [新しいカタログを作成する](../../managing-a-catalog/catalogs/creating-a-new-catalog.md)
* [商品オプションの使用](../../managing-a-catalog/creating-and-managing-products/products/using-product-options.md)
