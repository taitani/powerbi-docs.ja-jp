---
title: "チュートリアル: Power BI Desktop で Excel と OData フィードの売上データを分析する"
description: "チュートリアル: Excel と OData フィードの売上データを分析する"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 03c5afae78e1688cadfdef9c0a96ca9f24247e12
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>チュートリアル: Excel と OData フィードの売上データを分析する
**Power BI Desktop** では、あらゆる種類のデータ ソースに接続でき、さまざまに結合したり整形したりすることができます。これにより、興味深く説得力のあるデータ分析と視覚化を簡単に実現できます。 このチュートリアルでは、2 つのデータ ソースのデータを結合する方法について取り上げます。 

製品情報を入れるデータベースと売上情報を入れるデータベースが異なるなど、データが複数のデータ ソースにまたがることは珍しくありません。 このドキュメントで習得する手法では、Excel ブックと OData フィードを使用しますが、これらの手法は他のデータ ソース (SQL Server クエリ、CSV ファイル、Power BI Desktop の他のデータ ソースなど) にも適用できます。

このチュートリアルでは、Excel (製品情報を含む) および OData フィード (注文データを含む) からデータをインポートします。 変換と集約の手順を実行してから 2 つのソースのデータを結合して、対話式の視覚化が含まれている **製品と年度ごとの売上合計** レポートを生成します。 

最終的なレポートは次のようになります。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

このチュートリアルの手順を実行するには、製品のブックをダウンロード**:**[する必要があります。](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[ここ](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[をクリックすると、](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[.](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) をダウンロードできます。

**[名前を付けて保存]** ダイアログ ボックスで、ファイルに **Products.xlsx**という名前を指定します。

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>タスク 1: Excel ブックから製品データを取得する
このタスクでは、製品を Products.xlsx ファイルから Power BI Desktop にインポートします。

### <a name="step-1-connect-to-an-excel-workbook"></a>手順 1: Excel ブックに接続する
1. Power BI Desktop を起動します。
2. [ホーム] リボンで **[データの取得]**を選択します。 Excel は、 **最も一般的な** データ接続の 1 つであるため、 **[データの取り込み]** メニューから直接選択できます。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. [データの取り込み] ボタンを直接選択する場合は、**[ファイル] \> [Excel]** を選択し、**[接続]** を選択する方法もあります。
4. **[ファイルを開く]** ダイアログ ボックスで **Products.xlsx** ファイルを選択します。
5. **[ナビゲーター]** ウィンドウで **[製品]** テーブルを選択してから、 **[編集]**を選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>手順 2: 必要な列のみを表示するため、他の列を削除する
この手順では、 **ProductID**、 **ProductName**、 **UnitsInStock**、 **QuantityPerUnit**以外のすべての列を削除します。 Power BI Desktop では多くの場合、同じタスクを複数の方法で実行できます。 たとえば、リボンのボタンの多くは、列またはセルの右クリック メニューからも実行できます。

Power BI Desktop にはクエリ エディターが組み込まれており、このエディターでデータ接続を整形したり変換したりすることができます。 **[ナビゲーター]** から **[編集]**を選択すると、クエリ エディターが自動的に開きます。 また、Power BI Desktop の **[ホーム]** リボンで **[クエリを編集]** を選択することによって、クエリ エディターを開くこともできます。 以下の手順は、クエリ エディターで実行します。

1. クエリ エディターで、 **ProductID**、 **ProductName**、 **QuantityPerUnit**、および **UnitsInStock** 列 を選択します (1 つ以上の列を選択するには **Ctrl キーを押しながらクリック** し、隣り合う複数の列を選択するには **Shift キーを押しながらクリック** します)。
2. リボンで **[列の削除]**\>**[他の列の削除]** を選択するか、列ヘッダーを右クリックして **[他の列の削除]** をクリックします。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>手順 3: UnitsInStock 列のデータ型を変更する
クエリ エディターは、データに接続されると、各フィールドを再確認し、最適なデータ型を判別します。 Excel ブックの場合は、製品在庫は常に整数であるため、この手順で **UnitsInStock** 列のデータ型が整数であることをユーザーが確認します。

1. **UnitsInStock** 列を選択します。
2. **[ホーム]** リボンの **[データ型]** ドロップダウン ボタンを選択します。
3. まだ整数になっていない場合は、ドロップ ダウンから **[整数]** データ型を選択します ( **[データ型]** ボタンにも現在選択されているデータ型が表示されます)。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>作成される Power BI Desktop の手順
クエリ エディターでクエリ操作を実行すると、 **[クエリの設定]** ウィンドウの **[適用される手順]** 一覧にクエリの手順が作成されて表示されます。 各クエリ ステップには、"M" 言語とも呼ばれる対応する式があります。 “M” 数式言語について詳しくは、「[Power BI の数式について](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)」をご覧ください。

| タスク | クエリの手順 | 式 |
| --- | --- | --- |
| Excel ブックに接続する |Source |Source{[Name="Products"]}[Data] |
| 最初の行をテーブルの列ヘッダーに昇格させる |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (製品) |
| 必要な列のみを表示するため、他の列を削除する |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| データ型を変更する |Changed Type |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>タスク 2: OData フィードから注文データをインポートする
このタスクでは、注文データを取り込みます。 この手順では、販売システムに接続します。 下記の URL にあるサンプルの Northwind OData フィードからデータを Power BI Desktop にインポートし、下記の手順でコピーし (貼り付け) ます。<http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>手順 1: OData フィードに接続する
1. クエリ エディターの **[ホーム]** リボンで、**[データの取得]** を選択します。
2. **[OData フィード]** データ ソースを参照します。
3. **[OData フィード]** ダイアログ ボックスで、Northwind OData フィードの **[URL]** を入力します。
4. **[OK]**を選択します。
5. **[ナビゲーター]** ウィンドウで **[注文]** テーブルを選択してから、 **[編集]**を選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>チェック ボックスを選択せずにテーブル名をクリックすると、プレビューを表示できます。

### <a name="step-2-expand-the-orderdetails-table"></a>手順 2: Order\_Details テーブルを展開する
**Orders** テーブルには、**Details** テーブルへの参照が含まれます。このテーブルには、各注文に含まれている個別の製品が含まれています。 複数のテーブルが含まれるデータ ソース (リレーショナル データベースなど) に接続する場合は、これらの参照を使用してクエリを作成できます。 

この手順では、**Orders** テーブルと関連がある **Order\_Details** テーブルを展開し、**Order\_Details** の **ProductID**、**UnitPrice**、**Quantity** の各列を **Orders** テーブルに結合します。 これらのテーブル内のデータを次に示します。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

**[展開]** 操作によって、関連テーブルの列が、サブジェクト テーブルに結合されます。 クエリを実行すると、関連テーブルの行 (**Order\_Details**) がサブジェクト テーブル (**Orders**) の行に結合されます。

**Order\_Details** テーブルを展開すると、入れ子になったテーブルまたは関連テーブルの各行ごとに、3 つの新しい列と追加行が **Orders** テーブルに加えられます。

1. **クエリ ビュー**で、**Order\_Details** 列までスクロールします。
2. **Order\_Details** 列で、[展開] アイコン (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) を選択します。
3. **[展開]** ドロップダウンで以下の操作を行います。
   1. すべての列をオフにするため、 **(すべての列を選択)** を選択します。
   2. **ProductID**、 **UnitPrice**、 **Quantity**を選択します。
   3. **[OK]**をクリックします。
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>手順 3: 必要な列のみを表示するため、他の列を削除する
この手順では、**OrderDate、ShipCity**、**ShipCountry**、**Order\_Details.ProductID**、**Order\_Details.UnitPrice**、**Order\_Details.Quantity** 列以外のすべての列を削除します。 前のタスクでは、 **[他の列の削除]**を使用しました。 このタスクでは、選択した列を削除します。

1. **クエリ ビュー**で、すべての列を選択するため、a. と b. を実行します。
   1. 最初の列 (**OrderID**) をクリックします。
   2. Shift キーを押しながら最後の列 (**Shipper**) をクリックします。
   3. すべての列が選択されたので、Ctrl キーを押しながら、**OrderDate**、**ShipCity**、**ShipCountry**、**Order\_Details.ProductID**、**Order\_Details.UnitPrice**、**Order\_Details.Quantity** をクリックして選択解除します。
2. これで、削除する必要がある列のみが選択されたため、選択した列ヘッダーを右クリックし、 **[列の削除]**をクリックします。

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>手順 4: Order\_Details の各行で行の合計を計算する
Power BI Desktop を使用すると、インポートする列に基づいて計算を作成して、接続対象データを強化できます。 この手順では、**[カスタム列]** を作成し、**Order\_Details** の各行の行合計を計算します。

**Order\_Details** 行ごとの行合計を計算する

1. **[列の追加]** リボン タブで、 **[カスタム列の** **追加**] をクリックします。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. **[カスタム列の追加]** ダイアログ ボックスの **[カスタム列の数式]** テキスト ボックスに、**[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]** と入力します。
3. **[新しい列名]** テキスト ボックスに、 **LineTotal**と入力します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. **[OK]**をクリックします。

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>手順 5: LineTotal フィールドのデータ型を設定する
1. **LineTotal** 列を右クリックします。
2. **[型の変更]** を選択した後、**[10 進数] を選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>手順 6: クエリ内の列の名前の変更と順序の変更
この手順では、モデルを処理しやすいものにする最終段階として、レポートの作成時に、最終的な列の名前と順序を変更します。

1. **クエリ エディター**で、 **LineTotal** 列を、左側の **ShipCountry**の後にドラッグします。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. *Order\_Details.* プレフィックスを **Order\_Details.ProductID**、**Order\_Details.UnitPrice**、**Order\_Details.Quantity** の各列から削除します。削除するには、それぞれの列ヘッダーをダブルクリックした後、列名からテキストを削除します。

### <a name="power-bi-desktop-steps-created"></a>作成される Power BI Desktop の手順
クエリ エディターでクエリ操作を実行すると、 **[クエリの設定]** ウィンドウの **[適用される手順]** 一覧にクエリの手順が作成されて表示されます。 各クエリ ステップには、"M" 言語とも呼ばれる対応する Power Query 式があります。 この数式言語について詳しくは、「[Power BI の式について](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Power Query の式について")」をご覧ください。

| タスク | クエリの手順 | 式 |
| --- | --- | --- |
| OData フィードに接続する |Source |Source{[Name="Orders"]}[Data] |
| Order\_Details テーブルを展開する |Order\_Details を展開する |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| 必要な列のみを表示するため、他の列を削除する |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Order\_Details 行ごとの行合計を計算する |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>タスク 3: Products クエリと Total Sales クエリを結合する
Power BI Desktop では、レポート作成のためにクエリを結合する必要はありません。 代わりに、データセット間に **リレーションシップ** を作成できます。 データセットに共通する任意の列で、これらのリレーションシップを作成できます。 詳しくは、「[リレーションシップの作成と管理](desktop-create-and-manage-relationships.md)」をご覧ください。

このチュートリアルでは、共通の 'ProductID' フィールドを共有する注文データと製品データを使用します。そのため、Power BI Desktop で使用するモデルにおいてそれらの間にリレーションシップを持たせる必要があります。 これには単に、Power BI Desktop で各テーブルの列を関連付ける (つまり、列が同じ値を持つ) ように指定します。 Power BI Desktop がリレーションシップの方向とカーディナリティを自動的に判別します。 リレーションシップ自体を自動的に検出する場合もあります。

このタスクでは、Power BI Desktop で **製品** クエリと **売上合計** クエリの間にリレーションシップが確立されていることを確認します。

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>手順 1: 製品と売上合計の間のリレーションシップを確認する
1. 最初に、クエリ エディターで作成したモデルを Power BI Desktop に読み込む必要があります。 クエリ エディターの **[ホーム]** リボンで、**[閉じて読み込む]** を選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop が 2 つのクエリからデータを読み込みます。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. データが読み込まれたら、 **[ホーム]** リボンの **[リレーションシップの管理]** ボタンを選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. **[新規...]** ボタンを 選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. リレーションシップを作成しようとしましたが、既に 1 つ存在していることがわかりました。 **[リレーションシップの作成]** ダイアログで (列に影が付けられて) 示されているように、各クエリ内の **ProductsID** フィールドには既にリレーションシップが確立されています。
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. **[キャンセル]**を選択してから、Power BI Desktop の **リレーションシップ** ビューを選択します。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. 次のように表示され、クエリ間にリレーションシップがあることを確認できます。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. クエリにつながっている線の矢印をダブルクリックすると、 **[リレーションシップの編集]** ダイアログが表示されます。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. 変更を加える必要はないため、 **[キャンセル]** を選択して、 **[リレーションシップの編集]** ダイアログを閉じます。

## <a name="task-4-build-visuals-using-your-data"></a>タスク 4: データをビジュアル化する
Power BI Desktop を使用すると、データから洞察を得るためにさまざまな視覚エフェクトを作成できます。 複数のページで構成されるレポートを作成し、各ページに複数のビジュアルを含めることができます。 そうした視覚エフェクトと対話して、データの分析や把握に役立てることができます。 レポートの編集に関する詳細については、「[レポートの編集](service-interact-with-a-report-in-editing-view.md)」をご覧ください。

このタスクでは、既に読み込んだデータに基づいてレポートを作成します。 [フィールド] ウィンドウを使用して、視覚エフェクトを作成する列を選択します。

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>手順 1: 製品ごとの在庫数および年ごとの売上合計を示すグラフを作成する
[フィールド] ウィンドウ (画面の右側にあるウィンドウ) からキャンバス上の空白領域まで **UnitsInStock** をドラッグします。 テーブルの視覚エフェクトが作成されます。 次に、[視覚化] ウィンドウの下半分にある [軸] ボックスまで ProductName をドラッグします。 その後、視覚エフェクトの右上隅にある記号から **[並べ替え] \> [UnitsInStock]** を選択します。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

**OrderDate** をキャンバスの最初のグラフの下までドラッグし、さらに LineTotal を (再度 [フィールド] ウィンドウから) ビジュアル上にドラッグしてから、[折れ線グラフ] を選択します。 次の視覚エフェクトが作成されます。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 次に、**ShipCountry** を右上にあるキャンバス上の空白部分にドラッグします。 地理的なフィールドを選択したので、自動的にマップが作成されました。 ここで、**LineTotal** を **[値]** フィールドまでドラッグします。各国のマップ上の円のサイズが、その国に出荷された注文の **LineTotal** に合わせて調整されます。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>手順 2: レポートのビジュアルと対話を行い、さらに分析する
Power BI Desktop を使用すると、相互に強調表示したり、フィルター処理したりすることによってビジュアルと対話して、さらに傾向を明らかにすることができます。 詳細については、「[レポートにおけるフィルター処理と強調表示](power-bi-reports-filters-and-highlighting.md)」をご覧ください。

1. **Canad****a** の中心にある水色の円をクリックします。 他のビジュアルがフィルター処理され、カナダの在庫 (**ShipCountry**) と注文合計数 (**LineTotal**) だけが表示されていることに注目してください。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>完成した売上分析レポート
これらすべての手順を実行すると、Products.xlsx ファイルと Northwind OData フィードのデータを結合させた売上レポートが完成します。 このレポートには、さまざまな国の売上情報の分析に役立つビジュアルが示されています。 このチュートリアルの完成した Power BI Desktop ファイルは[ここ](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix)からダウンロードできます。

## <a name="next-steps"></a>次の手順
* [他の Power BI Desktop のチュートリアルを読む](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop のビデオを見る](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI フォーラムにアクセスする](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI ブログを読む](http://go.microsoft.com/fwlink/?LinkID=519327)



