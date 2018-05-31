---
title: 'チュートリアル: Power BI Desktop で Excel と OData フィードのデータを結合する'
description: 'チュートリアル: Excel と OData フィードのデータを結合します'
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 00c4915df0e18504ec6f5d26540d9289c2f5ddb2
ms.sourcegitcommit: 773ba0d1cc1d1fcee8e666e1c20450f5e343c5c1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "33945988"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>チュートリアル: Excel と OData フィードの売上データを結合する

製品情報を入れるデータベースと売上情報を入れるデータベースが異なるなど、データが複数のデータ ソースにまたがることは珍しくありません。 **Power BI Desktop** では、異なるソースからのデータを組み合わせて、興味深く説得力のあるデータ分析と視覚エフェクトを作成できます。 

このチュートリアルでは、2 つのデータ ソースからのデータを結合する方法を学習します。製品情報を含む Excel ブックと、注文データを含む OData フィードです。 各データセットをインポートし、変換と集計の手順を実行した後、両方のソースからのデータを使って、対話型の視覚エフェクトを含む売上分析レポートを生成します。 これらの手法は、SQL Server クエリ、CSV ファイル、および Power BI Desktop の他の任意のデータ ソースにも適用できます。

>[!NOTE]
>Power BI Desktop では多くの場合、タスクを複数の方法で実行できます。 たとえば、リボンのオプションの多くは、右クリックや、列またはセルの **[その他のオプション]** メニューを使って、使用することもできます。 以下の手順では、複数の代替方法を説明します。 

## <a name="import-the-product-data-from-excel"></a>Excel から製品データをインポートする

最初に、Excel の Products.xlsx ブックから Power BI Desktop に製品データをインポートします。

1. [Products.xlsx Excel ブックをダウンロード](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)し、**Products.xlsx** として保存します。
   
2. Power BI Desktop リボンの **[ホーム]** タブの **[データを取得]** の横にあるドロップダウン矢印を選んで、**[よく使われる]** ドロップダウンから **[Excel]** を選びます。 
   
   ![データの取得](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >**[データを取得]** 項目自体を選ぶか、Power BI の **[作業の開始]** ダイアログから **[データを取得]** を選び、**[データを取得]** ダイアログで **[Excel]** または **[ファイル]** > **[Excel]** を選んで、**[接続]** を選ぶこともできます。
   
3. **[開く]** ダイアログ ボックスで、**Products.xlsx** ファイルを探して選び、**[開く]** を選びます。
   
4. **[ナビゲーター]** ウィンドウで **[製品]** テーブルを選択してから、 **[編集]** を選択します。
   
   ![Excel の [ナビゲーター] ウィンドウ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
テーブルのプレビューが **Power Query エディター**で開きます。ここで、変換を適用してデータをクリーンアップできます。 
   
![Power Query エディター](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>また、Power BI Desktop の **[ホーム]** リボンから **[クエリの編集]** > **[クエリの編集]** を選ぶことで、または**レポート ビュー**で右クリックするかクエリの横にある **[その他のオプション]** を選んでから **[クエリの編集]** を選ぶことで、**Power Query エディター**を開くこともできます。

## <a name="clean-up-the-products-columns"></a>製品の列をクリーンアップする

結合されたレポートでは、Excel ブックの **ProductID**、**ProductName**、**QuantityPerUnit**、**UnitsInStock** 列だけを使うので、他の列は削除できます。 

1. **Power Query エディター**で、**ProductID**、**ProductName**、**QuantityPerUnit**、および **UnitsInStock** 列 を選びます (1 つ以上の列を選ぶには **Ctrl** キーを押しながら**クリック**し、隣り合う複数の列を選ぶには **Shift** キーを押しながら**クリック**します)。
   
2. 選んだいずれかの列のヘッダーを右クリックし、ドロップダウンから **[他の列の削除]** を選んで、選んだ列を除くすべての列をテーブルから削除します。 
   **[ホーム]** リボン タブの **[列の管理]** グループから **[列の削除]** > **[他の列の削除]** を選んでもかまいません。 
   
   ![他の列の削除](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>OData フィードから注文データをインポートする

次に、サンプルの Northwind 販売システムの OData フィードから注文データをインポートします。 

1. **Power Query エディター**で、**[新しいソース]** を選び、**[よく使われる]** ドロップダウンから **[OData フィード]** を選びます。 
   
   ![OData を取得する](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. **[OData フィード]** ダイアログ ボックスで、Northwind OData フィードの URL `http://services.odata.org/V3/Northwind/Northwind.svc/` を貼り付けて、**[OK]** を選びます。
   
   ![[OData フィード] ダイアログ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. **[ナビゲーター]** ウィンドウで、**Orders** テーブルを選び、**[OK]** を選んで、**Power Query エディター**にデータを読み込みます。
   
   ![OData の [ナビゲーター] ウィンドウ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >**[ナビゲーター]** では、チェック ボックスを選択せずにテーブル名を選んで、プレビューを表示できます。

## <a name="expand-the-order-data"></a>注文データを展開する

リレーショナル データベースや Northwind OData フィードのように複数のテーブルが含まれるデータ ソースに接続するときは、テーブル間の参照を使ってクエリを作成できます。 **Orders** テーブルには、複数の関連テーブルへの参照が含まれています。 **展開**操作を使うことによって、関連する **Order_Details** テーブルの **ProductID**、**UnitPrice**、および **Quantity** 列を、サブジェクト (**Orders**) テーブルに追加できます。 

1. **Order_Details** 列が表示されるまで、**Orders** テーブルを右にスクロールします。 この列にはデータではなく別のテーブルへの参照が含まれていることに注意してください。
   
   ![Order_Details 列](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. **Order_Details** 列のヘッダーで、**[展開]** アイコン ![[展開] アイコン](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png) を選びます。 
   
3. **[展開]** ドロップダウンで以下の操作を行います。
   
   1. すべての列をオフにするため、 **(すべての列を選択)** を選択します。
      
   2. **ProductID**、**UnitPrice**、**Quantity** を選んで、**[OK]** を選びます。
      
      ![[展開] ダイアログ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

**Order_Details** テーブルを展開すると、**Order_Details** 列が入れ子になったテーブルからの 3 つの新しい列に置き換えられ、各注文から追加されたデータの新しい行がテーブルに存在するようになります。 

![展開された列](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>カスタム計算列を作成する

Power Query エディターでは、データを充実させるために計算フィールドとカスタム フィールドを作成できます。 単価と項目の数量を乗算することによって注文の各明細項目の合計価格を計算するカスタム列を作成します。

1. Power Query エディターの **[列の追加]** リボン タブで、**[カスタム列]** を選びます。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. **[カスタム列]** ダイアログ ボックスで、**[新しい列名]** フィールドに「**LineTotal**」と入力します。

3. **[カスタム列の式]** フィールドの **=** の後に、「**[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]**」と入力します。 (入力する代わりに、**[使用できる列]** スクロール ボックスからフィールド名を選び、**[<< 挿入]** を選んでもかまいません。) 
3. **[OK]** を選択します。
   
   ![[カスタム列] ダイアログ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

**Orders** テーブルの最後の列として、新しい **LineTotal** フィールドが表示されます。

## <a name="set-the-data-type-for-the-new-field"></a>新しいフィールドのデータ型を設定する

Power Query エディターは、データに接続するとき、各フィールドの最適なデータ型を決定し、それに応じてデータを表示します。 フィールドに割り当てられているデータ型は、ヘッダーのアイコンで、または **[ホーム]** リボン タブの **[変換]** グループの **[データ型]** で、確認できます。 

新しい **LineTotal** 列のデータ型は **[すべて]** になっていますが、その値は通貨です。 データ型を割り当てるには、**LineTotal** 列のヘッダーを右クリックし、ドロップダウンから **[データ型の変更]** を選んで、**[固定小数点数]** を選びます。 

![データ型を変更する](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>または、**LineTotal** 列を選び、**[ホーム]** リボン タブの **[変換]** 領域の **[データ型]** の横にあるドロップダウン矢印を選んで、**[固定小数点数]** を選んでもかまいません。

## <a name="clean-up-the-orders-columns"></a>注文列をクリーンアップする

レポートでモデルの作業をしやすくするため、列の削除、名前変更、順序変更を行うことができます。

このレポートでは、**OrderDate**、**ShipCity**、**ShipCountry**、**Order_Details.ProductID**、**Order_Details.UnitPrice**、**Order_Details.Quantity** 列だけを使います。 Excel データで行ったようにこれらの列を選んで **[他の列の削除]** を使うか、上記の列以外のすべての列を選び、選んだ列のいずれかを右クリックして **[列の削除]** を選んで、すべての列を削除することもできます。 

列名から *Order_Details.* プレフィックスを削除することにより、**Order_Details.ProductID**、**Order_Details.UnitPrice**、**Order_Details.Quantity** 列を 識別しやすくすることができます。 列の名前を **ProductID**、**UnitPrice**、**Quantity** に変更するには、次のようにします。

1. 各列のヘッダーをダブルクリックまたは長押しします。または、列ヘッダーを右クリックして、ドロップダウンから **[名前の変更]** を選びます。 
2. *Order_Details.* プレフィックスを各名前から削除して、**Enter** キーを押します。

最後に、**LineTotal** 列にアクセスしやすくするため、この列を左にドラッグして **ShipCountry** 列のすぐ右にドロップします。

![クリーンアップされたテーブル](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>クエリのステップを確認する

Power Query エディターでデータを整形して変換すると、Power Query エディターの右側にある **[クエリの設定]** ウィンドウの **[適用したステップ]** 領域に、各ステップが記録されています。 [適用したステップ] をさかのぼり、行った変更を正確に確認し、必要に応じて編集、削除、または再配置を行うことができます (ただし、前のステップを変更すると後のステップが動作しなくなる可能性があるため、危険な可能性があります)。 

Power Query エディターの左側にある **[クエリ]** の一覧で各クエリを選び、**[クエリの設定]** で **[適用したステップ]** を確認します。 これまでのデータ変換を適用すると、2 つのクエリの [適用したステップ] は次のようになります。

![製品クエリの適用したステップ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![注文クエリの適用したステップ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>[適用したステップ] の基礎は、**M** 言語とも呼ばれる **Power Query 言語**で記述された数式です。 数式を表示および編集するには、リボンの [ホーム] タブの **[クエリ]** グループで **[詳細エディター]** を選択します。 

## <a name="import-the-transformed-queries"></a>変換されたクエリをインポートする

変換したデータに問題がなければ、**[ホーム]** リボン タブの **[閉じる]** グループで **[閉じて適用]** > **[閉じて適用]** の順に選び、Power BI Desktop のレポート ビューにデータをインポートします。 

![閉じて適用](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

データが読み込まれると、Power BI Desktop のレポート ビューの **[フィールド]** 一覧にクエリが表示されます。

![[フィールド] 一覧のクエリ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>データセット間のリレーションシップを管理する

Power BI Desktop では、レポート作成のためにクエリを結合する必要はありません。 ただし、共通に存在するフィールドに基づくデータセット間のリレーションシップを使うと、レポートを拡張して充実させることができます。 Power BI Desktop でリレーションシップを自動的に検出できます。または、Power BI Desktop の **[リレーションシップの管理]** ダイアログで作成することもできます。 Power BI Desktop でのリレーションシップについて詳しくは、「[Power BI Desktop でのリレーションシップの作成と管理](desktop-create-and-manage-relationships.md)」をご覧ください。

このチュートリアルの Orders データセットと Products データセットには共通の *ProductID* フィールドがあるので、これらの間にはその列に基づくリレーションシップがあります。 

1. Power BI Desktop のレポート ビューで、**[ホーム]** リボン タブの **[リレーションシップ]** 領域の **[リレーションシップの管理]** を選びます。
   
   ![[リレーションシップの管理] リボン](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. **[リレーションシップの管理]** ダイアログでは、Power BI Desktop によって Products テーブルと Orders テーブルの間のアクティブなリレーションシップが既に検出されて一覧に表示されていることに注意してください。 リレーションシップを表示するには、**[編集]** を選びます。 
   
   ![[リレーションシップの管理] ダイアログ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   **[リレーションシップの編集]** ダイアログが開き、リレーションシップに関する詳細が示されます。  
   
   ![[リレーションシップの編集] ダイアログ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop はリレーションシップを正しく自動検出しているので、**[キャンセル]**、**[閉じる]** の順に選んでリレーションシップ ダイアログを終了できます。

Power BI Desktop ウィンドウの左側で **[リレーションシップ]** ビューを選んで、クエリ間のリレーションシップを表示および管理することもできます。 2 つのクエリを接続する線の矢印をダブルクリックして **[リレーションシップの編集]** ダイアログを開き、リレーションシップを表示または変更します。 

![リレーションシップ ビュー](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

リレーションシップ ビューからレポート ビューに戻るには、**[レポートの表示]** アイコンを選びます。 

![レポート ビュー](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>データを使って視覚エフェクトを作成する

Power BI Desktop のレポート ビューでは、データから分析情報を得るためにさまざまな視覚エフェクトを作成できます。 複数のページで構成されるレポートを作成し、各ページに複数のビジュアルを含めることができます。 そうした視覚エフェクトと対話して、データの分析や把握に役立てることができます。 Power BI サービス (お使いのサイト) でのレポートの表示と編集について詳しくは、[レポートの編集](service-interact-with-a-report-in-editing-view.md)に関する記事をご覧ください。

両方のデータセットおよびそれらの間のリレーションシップを使うと、売上データの視覚化と分析に役立ちます。 

最初に、両方のクエリからのフィールドを使う積み上げ縦棒グラフを作成し、各製品の注文数量を示します。 

1. 右側の **[フィールド]** ウィンドウで **Orders** の **Quantity** フィールドを選ぶか、フィールドをキャンバスの空白の領域にドラッグします。 これにより、製品の合計注文数量を示す積み上げ縦棒グラフが作成されます。 
   
2. **[フィールド]** ウィンドウで **Products** の **ProductName** を選ぶか、フィールドをグラフにドラッグして、各製品の注文数量を表示します。 
   
3. 注文の多い順に製品を並べ替えるには、視覚エフェクトの右上にある **[その他のオプション]** の省略記号 **[...]** を選び、**[Quantity で並べ替え]** を選びます。
   
4. グラフの隅にあるハンドルを使ってグラフを拡大し、より多くの製品名が表示されるようにします。 
   
   ![ProductName 別数量の横棒グラフ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

次に、時間の経過 (**OrderDate**) に伴う注文の金額 (**LineTotal**) を示すグラフを作成します。 

1. キャンバスで何も選択されていない状態で、**[フィールド]** ウィンドウの **Orders** から **LineTotal** を選ぶか、キャンバスの空白領域にドラッグします。 積み上げ縦棒グラフに、すべての注文の合計金額が表示されます。 
   
2. グラフを選び、**Orders** から **OrderDate** を選ぶか、グラフにドラッグします。 グラフに各注文日の明細合計が表示されるようになります。 
   
3. 視覚エフェクトの隅をドラッグしてサイズを変更し、表示されるデータを増やします。 
   
   ![OrderDate 別 LineTotals の折れ線グラフ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >グラフに Years のみが表示される場合は (3 つのデータ ポイントだけ)、**[視覚化]** ウィンドウの **[軸]** フィールドで **OrderDate** の横にある矢印をドロップダウンし、**[日付の階層]** の代わりに **OrderDate** を選びます。 

最後に、各国の注文金額を示すマップ視覚エフェクトを作成します。 

1. キャンバスで何も選択されていない状態で、**[フィールド]** ウィンドウの **Orders** から **ShipCountry** を選ぶか、キャンバスの空白領域にドラッグします。 Power BI Desktop によってデータが国名であることが検出され、注文があった各国のデータ ポイントを含むマップ視覚エフェクトが自動的に作成されます。 
   
2. 各国の注文金額をデータ ポイントのサイズに反映させるには、**LineTotal** フィールドをマップにドラッグします (または、**[視覚化]** ウィンドウの下半分にある **[サイズ]** の **[ここにデータ フィールドをドラッグしてください]** にドラッグします)。 マップ上の円のサイズが、各国からの注文の金額を反映するようになります。 
   
   ![ShipCountry 別 LineTotals のマップ視覚エフェクト](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>レポートのビジュアルと対話してさらに分析する

Power BI Desktop を使うと、相互に強調表示したり、フィルター処理したりすることによってビジュアルと対話して、さらに傾向を明らかにすることができます。 詳しくは、[レポートにおけるフィルター処理と強調表示](power-bi-reports-filters-and-highlighting.md)に関する記事をご覧ください。 

クエリ間のリレーションシップのため、ある視覚エフェクトと対話すると、そのページ上の他のすべての視覚エフェクトに反映されます。 

マップ視覚エフェクトで、**カナダ**の中央にある円を選びます。 他の 2 つの視覚エフェクトがフィルター処理されて、カナダの明細金額と注文数量だけが強調表示されることに注意してください。

![カナダについてフィルター処理された売上データ](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

**Quantity by ProductName** グラフで製品の 1 つを選ぶと、マップと日付グラフがその製品のデータを反映するようにフィルター処理され、**LineTotal by OrderDate** グラフで日付の 1 つを選ぶと、マップと製品グラフがその日付のデータを表示するようにフィルター処理されます。 
>[!TIP]
>選択を解除するには、再びクリックするか、他の視覚エフェクトのいずれかをクリックします。 

## <a name="complete-the-sales-analysis-report"></a>完成した売上分析レポート

完成したレポートでは、Products.xlsx Excel ファイルと Northwind OData フィードからのデータが、異なる国、期間、および製品の注文情報を分析するのに役立つビジュアルに結合されています。 レポートの準備ができたら、[それを Power BI サービスにアップロード](desktop-upload-desktop-files.md)して、他の Power BI ユーザーと共有できます。

## <a name="next-steps"></a>次の手順
* [他の Power BI Desktop のチュートリアルを読む](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop のビデオを見る](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI フォーラムにアクセスする](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI ブログを読む](http://go.microsoft.com/fwlink/?LinkID=519327)