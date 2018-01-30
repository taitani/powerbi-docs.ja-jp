---
title: "チュートリアル: 複合グラフ"
description: "複合グラフに関するこのチュートリアルでは、複合グラフを使用する状況と、Power BI サービスおよび Power BI Desktop.で複合グラフを作成する方法について説明します。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
ms.openlocfilehash: ac738b337e7eb1c861347b273c7f1c4571a700a2
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2018
---
# <a name="combo-chart-in-power--tutorial"></a>Power BI での複合グラフ (チュートリアル)
Power BI の複合グラフは、折れ線グラフと縦棒グラフを組み合わせた 1 つの視覚化です。 2 つのグラフを 1 つに組み合わせると、データの比較をよりすばやく行うことができます。

複合グラフには、1 つまたは 2 つの Y 軸を保持できます。

## <a name="when-to-use-a-combo-chart"></a>複合グラフを使用すべきケース
複合グラフは、次のような場合に最適な選択肢になります。

* 同じ X 軸を持つ折れ線グラフと縦棒グラフがある場合。
* 値の範囲が異なる複数のメジャーを比較する場合。
* 2 つのメジャーの間の相関関係を 1 つの視覚化で示す場合。
* あるメジャーが別のメジャーで定義されているターゲットを満たすかどうかを調べる場合
* キャンバスのスペースを節約する場合。

### <a name="prerequisites"></a>前提条件
複合グラフは、Power BI サービスでも Power BI Desktop でも利用できます。 このチュートリアルでは、Power BI サービスを使用して複合グラフを作成します。 作業を進めるために、Power BI サービスを開き、"小売りの分析" のサンプルに接続します ([以下の手順を参照](#create))。


## <a name="create-a-basic-single-axis-combo-chart"></a>基本的な 1 つの軸の複合グラフを作成する
このビデオでは、売上およびマーケティングのサンプルを使って複合グラフを作成する様子をご覧いただけます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

<a name="create"></a> 独自の複合グラフを作成するには、Power BI サービスにサインインして、**[データの取得] \> [サンプル] \> [小売りの分析のサンプル] > [接続] > [ダッシュボードへ移動]** を選択します。 

1. [小売りの分析のサンプル] ダッシュボードで、 **\[Total Stores] \(総店舗数)** タイルを選び、[小売りの分析のサンプル] レポートを開きます。
2. **[レポートの編集]** を選んで、編集ビューでレポートを開きます。
3. [新しいレポートのページを追加](power-bi-report-add-page.md)します。
4. 今年の売上と粗利益を月単位で表示する縦棒グラフを作成します。
   
    a.  [フィールド] ウィンドウで、**\[Sales] \(売上)** \> **\[This Year Sales] \(今年の売上)** > **[値]** を選択します。
   
    b.  **[Sales]** \> **[Gross Margin This Year]** を **[値]** にドラッグします。
   
    c.  **[Time]** \> **[Fiscal Month]** の順に選択して、**[軸]** に追加します。 
   
    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. 視覚化の右上隅にある省略記号 [...] を選び、**[並べ替え: FiscalMonth]** を選びます。 昇順または降順で並べ替えるために、これを 2 回選択することが必要な場合があります。

6. 縦棒グラフを複合グラフに変換します。 縦棒グラフを選んだ状態で **[視覚化]** ウィンドウから **[折れ線グラフおよび集合縦棒グラフ]** を選びます。
   
    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. **[フィールド]** ウィンドウで、**[Sales]** \> **[Last Year Sales]** を **[線の値]** バケットにドラッグします。
   
   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)
   
   複合グラフは次のようになります。
   
   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>2 つの軸を持つ複合グラフを作成する
このタスクでは、粗利と売上を比較します。

1. **前年の粗利 (%)** を**月ごと**に追跡する新しい折れ線グラフを作成します。  1 月の粗利 (%) は 35% で、4 月には最高値の 45% になり、7 月に下がって 8 月に再びピークに達しました。 前年と本年は同じ売上パターンになるでしょうか?
   
   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. **[This Year Sales] > [Value]** と **[Last Year Sales]** を折れ線グラフに追加します。 **[Gross Margin Last Year %]\(前年の粗利 (%)\)** の目盛が **[Sales]\(売上\)** の目盛よりかなり小さいため、比較が困難です。      
   
   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. ビジュアルの読みやすく分かりやすくするため、折れ線グラフを「折れ線グラフおよび積み上げ縦棒グラフ」に変換します。
   
   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. **[Gross Margin% Last Year]** (前年の粗利 (%)) を **[各棒の値]** から **[線の値]** にドラッグします。 Power BI によって 2 つの軸が作成されるため、各データ セットを異なる縮尺でプロットできます。つまり、左側の測定単位はドル売上高で、右側の測定単位は割合です。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>タイトルを各軸に追加する
1. ペイント ローラー アイコン ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) を選び、[書式設定] ウィンドウを開きます。
2. 下矢印を選んで、 **Y 軸** のオプションを展開します。
3. **[Y 軸 (棒)]** で、**[位置]** を **[左]** に、**[タイトル]** を **[オン]** に、**[スタイル]** を **[タイトルのみを表示]**に、**[表示]** を **[百万]** に、それぞれ設定します。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. **[Y 軸 (棒)]** では、下方向にスクロールし、**[セカンダリの表示]** が **[オン]** に設定されていることを確認します。 これにより、複合グラフの折れ線グラフの部分の書式を設定するためのオプションが表示されます。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. **[Y 軸 (折れ線)]** で、**[位置]** は **[右]** にし、**[タイトル]** を **[オン]** にして、**[スタイル]** を **[タイトルのみを表示]** に設定します。
   
   複合グラフに 2 つの軸とそれぞれのタイトルが表示されるようになります。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. 必要に応じて、グラフの表示および読みやすさが向上するように、テキストのフォント、サイズ、色を変更し、その他の書式設定オプションも設定します。

ここからは次のことができます。

* [複合グラフをダッシュボード タイルとして追加](service-dashboard-tiles.md)します。
* [レポートを保存](service-report-save.md)します。

## <a name="cross-highlighting-and-cross-filtering"></a>クロスハイライトとクロス フィルター処理

複合グラフ内の縦棒または折れ線を強調表示すると、レポートのページ上の他の視覚化がクロスハイライトおよびクロス フィルター処理されます。逆の場合も同様です。 [[ビジュアル対話]](visual-interactions.md) を使用すれば、この既定の動作を変更できます。

## <a name="next-steps"></a>次の手順

[Power BI レポートでの視覚化の概要](power-bi-report-visualizations.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

