---
title: "Power BI の散布図 (チュートリアル)"
description: "チュートリアル: Power BI の散布図"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: c1801db4135d6d97a940e593de37ca2886194b53
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Power BI の散布図とバブル チャート (チュートリアル)
散布図には、必ず 2 つの値軸があり、横軸に沿って数値データの 1 つのセットが表示され、縦軸に沿って数値データのもう 1 つのセットが表示されます。 このグラフには x と y の数値が交差する位置に点が表示され、この 2 つの値が 1 つのデータ ポイントに結合されます。 これらのデータ ポイントは、データに応じて、横軸に沿って値が均等に分布したり、不均等に分布したりします。

バブル チャートは、データ ポイントをバブルに置き換えます。バブルの*サイズ*は、データの追加のディメンションを表します。

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>散布図とバブル チャートの使い分けについて
### <a name="scatter-charts-are-a-great-choice"></a>散布図は、次のような場合に最適な選択肢になります。
* 2 つの **数値** (散布図)、または 3 つの数値 (バブル) の間の関係を示す。
* 2 つのグループの数値を、xy 座標の 1 つの系列としてプロットする。
* 水平軸のスケールを変更する場合に、折れ線グラフの代わりに使用する。    
* 水平軸を対数スケールに変更する。
* ペアまたはグループになった値のセットを含むワークシート データを表示する。 散布図では、2 つの軸のスケールを独立して調整し、グループ化された値についてより多くの情報を引き出すことができます。
* 大きなデータ セットからパターンを表示する。たとえば、線形の傾向や非線形の傾向、クラスター、外れ値を見つけることができます。
* 時間に関係なく大量のデータ点を比較する。散布図に含めるデータが多いほど、より適切な比較を行うことができます。

### <a name="bubble-charts-are-a-great-choice"></a>バブル チャートは、次のような場合に最適な選択肢になります。
* それぞれ値のセットを含む 3 つのデータ系列で構成されたデータがある。
* 財務データを表示する。  バブル サイズを変更すると、特定の値を視覚的に強調できます。
* 象限 (四分円) を使用する。

## <a name="create-a-scatter-chart"></a>散布図を作成する
<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. [編集ビュー](service-interact-with-a-report-in-editing-view.md)で小売りの分析のサンプルを開き、[新しいレポート ページを追加](power-bi-report-add-page.md)します。
2. [フィールド] ウィンドウから、**[Sales]** > **[Sales Per Sq Ft]** と **[Sales]** > **[Total Sales Variance %]** を選びます。
3. [フィールド] ウィンドウから **[District]、[District]** の順に選択します。
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_pre_convert.png)
4. 散布図に変換します。 [視覚化] ウィンドウで、散布図アイコンを選びます。
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png)
5. **[District] \(地域)** を **[詳細]** から **[凡例]**にドラッグします。
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_new.png)

これで、総売上高の差異 % を Y 軸に、平方フィートあたりの売上高を X 軸にプロットした散布図ができあがりました。  データ点の色は地区を表しています。  次に、3 番目のディメンションを追加してみましょう。

## <a name="create-a-bubble-chart"></a>バブル チャートを作成する
1. [フィールド] ウィンドウから、**[Sales]** > **[This Year Sales]** > **[値]** を **[サイズ]** 領域にドラッグします。 
   
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_size.png)
2. バブルの上にマウスを置きます。  バブルのサイズは、 **[This Year Sales]**の値を反映しています。
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. 必要に応じて、[視覚化の色、ラベル、タイトル、背景などの書式を設定](service-getting-started-with-color-formatting-and-axis-properties.md)します。

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
### <a name="your-scatter-chart-has-only-one-data-point"></a>**散布図グラフにデータ ポイントが 1 つだけ表示される**
散布図に、X 軸上と Y 軸上のすべての値を集計した 1 つのデータ ポイントのみが表示されていますか?  あるいは、1 本の横線または縦線に沿ってすべての値が集計されていますか?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

**[詳細]** 領域にフィールドを追加して、値をグループ化する方法を Power BI に指示してください。 フィールドは、プロットするポイントごとに一意である必要があります。  
たとえば、行番号や ID フィールドを使用すると、このようになります。

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

または、そのようなデータがない場合は、X と Y の値を連結してポイントごとに一意の値を持つフィールドを作成します。

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

新しいフィールドを作成するには、[Power BI Desktop クエリ エディターを使ってデータセットにインデックス列を追加します](desktop-add-custom-column.md)。  その後、この列を視覚化の **[詳細]**領域に追加します。

## <a name="next-steps"></a>次の手順
 [Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)

[試してみる (無料)](https://powerbi.com/)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

