---
title: Power BI の複合グラフ
description: 複合グラフに関するこのチュートリアルでは、複合グラフを使用する状況と、Power BI サービスおよび Power BI Desktop.で複合グラフを作成する方法について説明します。
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e461480f53f4a97aeb4282e64a8a03eb8e1418d1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187741"
---
# <a name="combo-chart-in-power-bi"></a>Power BI の複合グラフ
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

<a name="create"></a> 独自の複合グラフを作成するには、Power BI サービスにサインインして、 **[データの取得] \> [サンプル] \> [小売りの分析のサンプル] > [接続] > [ダッシュボードへ移動]** を選択します。

1. [小売りの分析のサンプル] ダッシュボードで、 **\[Total Stores] \(総店舗数)** タイルを選び、[小売りの分析のサンプル] レポートを開きます。
2. **[レポートの編集]** を選び、編集ビューでレポートを開きます。
3. 新しいレポートのページを追加します。
4. 今年の売上と粗利益を月単位で表示する縦棒グラフを作成します。

    a.  [フィールド] ウィンドウで、 **\[Sales] \(売上)** \> **\[This Year Sales] \(今年の売上)**  >  **[値]** を選択します。

    b.  **[Sales]** \> **[Gross Margin This Year]** を **[値]** にドラッグします。

    c. **[Time]** \> **[Fiscal Month]** の順に選択して、 **[軸]** に追加します。

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. 視覚エフェクトの右上隅にある省略記号 (...) を選び、 **[並べ替え] > [FiscalMonth]** を選択します。 並べ替え順序を変更するには、省略記号をもう一度選び、 **[昇順で並べ替え]** または **[降順で並べ替え]** を選択します。

6. 縦棒グラフを複合グラフに変換します。 次の 2 つの複合グラフを使用できます: **[折れ線グラフおよび積み上げ縦棒グラフ]** と **[折れ線グラフおよび集合縦棒グラフ]** 。 縦棒グラフを選んだ状態で **[視覚化]** ウィンドウから **[折れ線グラフおよび集合縦棒グラフ]** を選びます。

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. **[フィールド]** ウィンドウで、 **[Sales]** \> **[Last Year Sales]** を **[線の値]** バケットにドラッグします。

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   複合グラフは次のようになります。

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>2 つの軸を持つ複合グラフを作成する
このタスクでは、粗利と売上を比較します。

1. 追跡する新しい折れ線グラフを作成する**Gross Margin 最後の年 %** によって**FiscalMonth**します。 省略記号を選択して、**月ごと**に**昇順**で並べ替えます。  
1 月の粗利 (%) は 35% で、4 月には最高値の 45% になり、7 月に下がって 8 月に再びピークに達しました。 前年と本年は同じ売上パターンになるでしょうか?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. **[This Year Sales] > [Value]** と **[Last Year Sales]** を折れ線グラフに追加します。 **[Gross Margin Last Year %]\(前年の粗利 (%)\)** の目盛が **[Sales]\(売上\)** の目盛よりかなり小さいため、比較が困難です。      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. ビジュアルの読みやすく分かりやすくするため、折れ線グラフを「折れ線グラフおよび積み上げ縦棒グラフ」に変換します。

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. **[Gross Margin% Last Year]** (前年の粗利 (%)) を **[各棒の値]** から **[線の値]** にドラッグします。 Power BI によって 2 つの軸が作成されるため、各データ セットを異なる縮尺でプロットできます。つまり、左側の測定単位はドル売上高で、右側の測定単位は割合です。 質問に対する回答は "はい" であり、同様のパターンとなります。

   ![](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>タイトルを各軸に追加する
1. ペイント ローラー アイコン ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) を選び、[書式設定] ウィンドウを開きます。
2. 下矢印を選んで、 **Y 軸** のオプションを展開します。
3. **Y 軸 (棒)** 設定**位置**に**左**設定**タイトル**に**で**、 **スタイル**に**タイトルのみを表示する**、および**表示単位**として**何百万人も**します。

   ![](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. **Y 軸 (棒)** 、表示されるまで下にスクロール**セカンダリを表示**します。 Y 軸のオプションは多数あるため、両方のスクロール バーを使用する必要があります。 Show セカンダリ セクションには、複合グラフの折れ線グラフの部分の書式設定オプションが表示されます。

   ![](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. **[Y 軸 (折れ線)]** で、 **[位置]** は **[右]** にし、 **[タイトル]** を **[オン]** にして、 **[スタイル]** を **[タイトルのみを表示]** に設定します。

   複合グラフに 2 つの軸とそれぞれのタイトルが表示されるようになります。

   ![](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. 必要に応じて、グラフの表示および読みやすさが向上するように、テキストのフォント、サイズ、色を変更し、その他の書式設定オプションも設定します。

ここからは次のことができます。

* [複合グラフをダッシュボード タイルとして追加](../service-dashboard-tiles.md)します。
* [レポートを保存](../service-report-save.md)します。
* [障碍を持つユーザーのためにレポートをより使いやすくします](../desktop-accessibility.md)。

## <a name="cross-highlighting-and-cross-filtering"></a>クロスハイライトとクロス フィルター処理

複合グラフ内の縦棒または折れ線を強調表示すると、レポートのページ上の他の視覚化がクロスハイライトおよびクロス フィルター処理されます。逆の場合も同様です。 [[ビジュアル対話]](../service-reports-visual-interactions.md) を使用すれば、この既定の動作を変更できます。

## <a name="next-steps"></a>次の手順

[Power BI のドーナツ グラフ](power-bi-visualization-doughnut-charts.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)
