---
title: Power BI Desktop (プレビュー) での多対多のリレーションシップ
description: Power BI Desktop で多対多のリレーションシップを使用する
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/31/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 40799bb2716b2f6e85405e76c2a301acef3509aa
ms.sourcegitcommit: 06f59902105c93700e71e913dff8453e221e4f82
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39388757"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>Power BI Desktop (プレビュー) での多対多のリレーションシップ

**Power BI Desktop** の**多対多のリレーションシップ**機能を使用すると、**多対多**のカーディナリティを使用してテーブルを結合し、複数のデータ ソースを含むデータ モデルを作成する操作をより簡単に、また直感的に行うことができます。 **多対多のリレーションシップ**機能は、**Power BI Desktop** のより大きな機能である**複合モデル**の一部です。

![[リレーションシップの編集] ダイアログの多対多](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

**Power BI Desktop** の**多対多のリレーションシップ**機能は、3 つの関連する機能群の一部です。

* **複合モデル**: 複数のデータ接続 (DirectQuery 接続やインポートなど) を任意の組み合わせでレポートに含めることができます。
* **多対多のリレーションシップ**: **複合モデル**を使用すると、テーブル間に**多対多のリレーションシップ**を確立できます。これにより、テーブル内の一意の値に関する要件と、リレーションシップを確立するためだけに新しいテーブルを導入するなどの以前の回避策が不要になります。 
* **ストレージ モード**: DirectQuery に基づく場合でも、バックエンド データ ソースに対するクエリが必要で、インポートが不要なビジュアルを指定できるようになりました。その結果、パフォーマンスが向上し、バックエンドの負荷が軽減されます。 以前は、スライサーのような単純なビジュアルでも、バックエンド ソースに対してクエリの送信が開始されました。 

**複合モデル**のこの 3 つの関連機能群については、それぞれ別々の記事で説明されています。

* **複合モデル**の詳細については、「[Power BI Desktop の複合モデル (プレビュー)](desktop-composite-models.md)」を参照してください。
* **多対多のリレーションシップ**については、この記事で説明されています。
* **ストレージ モード**については、「[Power BI Desktop のストレージ モード (プレビュー)](desktop-storage-mode.md)」を参照してください。

## <a name="enabling-the-many-to-many-relationships-preview-feature"></a>多対多のリレーションシップ プレビュー機能を有効にする

**多対多のリレーションシップ**機能は**複合モデル**機能の一部であり、プレビュー段階です。**Power BI Desktop** で有効にする必要があります。 **複合モデル**を有効にするには、**[ファイル] > [オプションと設定] > [オプション] > [プレビュー機能]** の順に選択し、**[複合モデル]** チェックボックスをオンにします。

![プレビュー機能を有効にする](media/desktop-composite-models/composite-models_02.png)

この機能を有効にするには、**Power BI Desktop** を再起動する必要があります。

![変更を有効にするには再起動が必要](media/desktop-composite-models/composite-models_03.png)


## <a name="what-many-to-many-relationships-solves"></a>多対多のリレーションシップで解決できること

**多対多のリレーションシップ**を利用できるようになる前は、Power BI で 2 つのテーブル間にリレーションシップを定義する場合、リレーションシップに関係する列の少なくとも 1 つに一意の値が含まれている必要がありました。 ただし、多くの場合、テーブル内の列には一意の値が含まれていませんでした。 

たとえば、2 つのテーブルに *Country* (国) を含む列があり、*Country* (国) の値がいずれのテーブルでも一意ではない場合です。 このようなテーブル間を結合するには、必要な一意の値を含む追加のテーブルをモデルに導入するなどの回避策を採る必要がありました。 **多対多のリレーションシップ**機能は、そのようなテーブルを**多対多**のカーディナリティを使用して直接結合することができる代替のアプローチを提供します。  

## <a name="using-many-to-many-relationships"></a>多対多のリレーションシップを使用する

Power BI で 2 つのテーブル間のリレーションシップを定義する場合、リレーションシップのカーディナリティを定義する必要があります。 たとえば、(*ProductSales[ProductCode]* と *Product[ProductCode]* を使用する) *ProductSales* (製品売上) テーブルと *Product* (製品) テーブル間のリレーションシップは、各製品の売上数が多く、*Product* (製品) テーブルの *(ProductCode)* の列は一意なので、**多対 1** です。 Power BI でリレーションシップのカーディナリティを**多対 1**、**1 対多**、または **1 対 1** と定義すると、選択されたカーディナリティが実際のデータと一致することが検証されます。

たとえば、次の図の単純なモデルを見てみましょう。

![リレーションシップ ビュー](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

*Product* (製品) テーブルに 2 行しかないとします。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

また、*Sales* (売上) テーブルには、*Product* (製品) テーブルには存在しない製品 **C** の *Sales* (売上) を含め、4 行しかないとします (参照整合性エラーのため)。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

*ProductName* (製品名) と *Price* (価格) (*Product* (製品) テーブル) と各製品の合計 *Qty* (数量) (*ProductSales* (製品売上) テーブル) が表示されるビジュアルには、次の図のように表示されます。 

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

前の図でわかるように、ビジュアルには空白の *ProductName* (製品名) 行があり、製品 *C* の売上と関連付けられています。この空白行は次のことを示します。

* *Product* (製品) テーブルに対応する行が存在しない *ProductSales* (製品売上) テーブルの行があります。つまり、この例の製品 *C* のように、参照整合性の問題があります。

* 外部キー列が Null である *ProductSales* (製品売上) テーブルの行があります。 

これらの理由により、いずれの場合でも、空白行は *ProductName* (製品名) と *Price* (価格) が不明な売上を示します。

ただし、テーブルが 2 つの列で結合される場合に、どちらの列も一意ではないことがあります。 たとえば、次の 2 つのテーブルを考えてみましょう。

* *Sales* (売上) テーブルには、*State* (州) 別の売上データが含まれており、各行はその州 (カリフォルニア州、ワシントン州、テキサス州など) の売上の種類を示します。 

    ![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* *CityData* (市区町村データ) テーブルには、人口や州 (カリフォルニア州、ワシントン州、ニューヨーク州など) など、市区町村に関するデータが含まれています。

    ![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

両方のテーブルに *State* (州) の列があり、*State* (州) 別の *Sales* (売上) と、各州の合計人口についてレポートを表示したいところですが、どちらのテーブルでも *State* (州) 列が一意ではないという問題があります。 

## <a name="the-prior-workaround"></a>以前の回避策

2018 年 7 月リリースより前のバージョンの **Power BI Desktop** では、このようなテーブル間に直接リレーションシップを作成することはできませんでした。 この問題の一般的な回避策は、以下の手順を実行することでした。

* 一意の *State* ID のみを含む第 3 のテーブルを作成します。 計算されたテーブル (DAX を使用して定義されたテーブル)、または**クエリ エディター**で定義したクエリを使用して定義されたテーブル (いずれかのテーブルまたは和集合から抽出された一意の ID を含むテーブル) のいずれかを使用できます。

* 一般的な**多対 1* リレーションシップを使用して、2 つの元のテーブルをその新しいテーブルに関連付けます。

この回避策のテーブルは、表示したままにするか、フィールド リストに表示されないように非表示にすることができます。 非表示にする場合、一般的に**多対 1** リレーションシップを双方向でフィルター処理するように設定することで、いずれかのテーブルの *State* (州) フィールドを使用し、以降のクロス フィルター処理がもう 1 つのテーブルに反映されるようにします。 この回避策のアプローチを次の**リレーションシップ ビュー**の図に示します。

![リレーションシップ ビュー](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

*State* (州) (*CityData* (市区町村データ) テーブル) と共に合計の *Population* (人口) と合計の *Sales* (売上) を表示するビジュアルは以下のようになります。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

この回避策で *CityData* (市区町村データ) テーブルの州を使用すると、そのテーブルに含まれる *State* (州) のみが一覧表示されます (そのため、テキサス州は除外されます)。 また、**多対 1** リレーションシップの場合とは異なり、合計行にはすべての *Sales* (売上) (テキサス州のデータを含む) が含まれますが、このような不一致の行を対象とする空白行は含まれません。 同様に、*State* (州) が null 値の *Sales* (売上) を対象とする空白行はありません。

このビジュアルに *City* (市区町村) も追加した場合、*City* (市区町村) の人口がわかるので、次の図のように、*City* (市区町村) の *Sales* (売上) には、対応する *State* (州) の *Sales* (売上) が繰り返し表示されます (通常、集計メジャーに関連付けられていない列でグループ化する場合と同様です)。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

この回避策ですべての *States* (州) の和集合になるように新しいテーブル *Sales* (売上) を定義し、フィールド リストに表示した場合、(新しいテーブルの) *State* (州) と共に合計の *Population* (人口) と *Sales* (売上) が表示されます。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

この場合、ビジュアルには*テキサス* (*Sales* (売上) はあるが人口が不明) と*ニューヨーク* (人口はわかるが、*Sales* (売上) がない) が含まれます。 

ご覧のとおり、この回避策は最適ではなく、多くの問題があります。 **多対多のリレーションシップ**を作成されると、これらの問題が解決されます。次のセクションで詳細について説明します。

## <a name="using-many-to-many-relationships-instead-of-the-workaround"></a>回避策ではなく多対多のリレーションシップを使用する

2018 年 7 月以降のバージョンの **Power BI Desktop** では、このような回避策に頼ることなく、前のセクションで説明したテーブルを直接関連付けることができます。 リレーションシップのカーディナリティを**多対多**に設定し、いずれの表にも一意の値が含まれていないことを示すことができるようになりました。 このようなリレーションシップでも、どちらのテーブルがもう一方のテーブルをフィルター処理するかを制御できます。また、両方のテーブルが相互にフィルター処理する双方向のフィルター処理を指定できます。  

> [!NOTE]
> **多対多**のリレーションシップを作成する機能はプレビュー段階です。プレビュー中は、**多対多**のリレーションシップを使用するモデルを Power BI サービスに発行することはできません。 

**Power BI Desktop** では、いずれのテーブルにもリレーションシップの列に一意の値が含まれていないと判断された場合、カーディナリティの既定値は**多対多**になります。 このような場合、リレーションシップの設定が、データの問題の意図しない結果ではなく、意図した動作であることを確認する警告が表示されます。 

たとえば、*CityData* (市区町村データ) と *Sales* (売上) 間に直接リレーションシップを作成し、フィルターのフローが *CityData* (市区町村データ) から *Sales* (売上) になるように設定すると、次の図のようなリレーションシップ ダイアログが表示されます。

![[リレーションシップの編集] ダイアログ](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

結果の**リレーションシップ ビュー**には、2 つのテーブル間に直接の**多対多**のリレーションシップが表示されるようになります。 **[フィールド]** リストの表示と、ビジュアルが作成された以降の動作は、前のセクションで説明した回避策を採用した場合と同じで、(個別の *States* (州) が含まれる) 余計なテーブルは表示されていません。 たとえば、前のセクションで説明した回避策と同様に、*States* (州) と合計の人口と売上を示すビジュアルは次のようになります。

![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

**多対多**のリレーションシップとより一般的な**多対 1** のリレーションシップの主な違いは次のとおりです。

* 表示される値に、もう一方のテーブルに一致しない行がある場合を示す空白行は含まれていません。また、もう一方のテーブルのリレーションシップで使用されている列が null の行も含まれていません。
* *RELATED()* 関数を使用することはできません (複数の行が関連する可能性があるため)
* テーブルに *ALL()* 関数を使用しても、**多対多**のリレーションシップによって関連付けられているもう一方のテーブルに適用されているフィルターは削除されません。 たとえば、前の例で次のように定義されたメジャーでは、関連する *CityData* (市区町村データ) テーブルの列に対するフィルターは削除されません。

    ![スクリプトの例](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    その結果、*State* (州)、*Sales* (売上)、および *Sales total* (売上合計) を表示するビジュアルは次のようになります。

    ![テーブルのビジュアル](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

このため、*合計の %* など、*ALL(\<Table>)* を使用した計算が意図した結果を返していることをよく確認する必要があります。 


## <a name="limitations-and-considerations"></a>制限事項と考慮事項

このリリースの**多対多のリレーションシップ**と**複合モデル**にはいくつかの制限事項があります。

次の多次元ソースは、**複合モデル**に使用できません。

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI データ セット

DirectQuery を使用してこのような多次元ソースに接続する場合、別の DirectQuery ソースに接続することも、インポートしたデータと結合することもできません。

DirectQuery を使用する際の既存の制限は、**多対多のリレーションシップ**を使用する場合にも適用されます。 これらの制限事項の多くは、テーブルの**ストレージ モード**に応じてテーブルごとに適用されるようになりました。 たとえば、インポートされたテーブルの計算列からは他のテーブルを参照できますが、DirectQuery テーブルの計算列は同じテーブルの列のみを参照するように制限されています。 モデル内のテーブルのいずれかが DirectQuery の場合、モデル全体に他の制限事項が適用されます。 たとえば、モデル内のいずれかのテーブルに**ストレージ モード**の DirectQuery がある場合、**QuickInsights** 機能と **Q&A** 機能は使用できません。 

## <a name="next-steps"></a>次の手順

以下の記事では、複合モデルと DirectQuery について詳しく説明しています。

* [Power BI Desktop の複合モデル (プレビュー)](desktop-composite-models.md)
* [Power BI Desktop のストレージ モード (プレビュー)](desktop-storage-mode.md)

DirectQuery に関する記事:

* [Power BI で DirectQuery を使用する](desktop-directquery-about.md)
* [Power BI の DirectQuery でサポートされるデータ ソース](desktop-directquery-data-sources.md)

