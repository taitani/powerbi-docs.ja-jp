---
title: Power BI のドーナツ グラフ
description: Power BI のドーナツ グラフ
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416753"
---
# <a name="doughnut-charts-in-power-bi"></a>Power BI のドーナツ グラフ
ドーナツ グラフは、全体に対する部分の関係が示される点で円グラフと似ています。 唯一の違いは、中央が空白で、ラベルまたはアイコン用の領域を確保できることです。

## <a name="create-a-doughnut-chart"></a>ドーナツ グラフの作成
以下の手順では、小売りの分析のサンプルを使って、今年の売上をカテゴリ別に表示するドーナツ グラフを作成します。 作業を進めるために、Power BI サービスまたは Power BI Desktop の[サンプルをダウンロード](../sample-datasets.md)します。

1. [空のレポート ページ](../power-bi-report-add-page.md)で開始します。 Power BI サービスを使っている場合は、[編集ビュー](../service-interact-with-a-report-in-editing-view.md)でレポートを開いていることを確認します。

2. [フィールド] ウィンドウで、**[Sales]** \> **[Last Year Sales]** を選びます。  
   
3. [視覚化] ウィンドウで、ドーナツ グラフのアイコン ![ドーナツ グラフ アイコン](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) を選んで、横棒グラフをドーナツ グラフに変換します。 **[Last Year Sales]** が **[値]** 領域にない場合は、そこにドラッグします。
     
   ![ドーナツが選択された [視覚化] ウィンドウ](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. **[Item]** \> **[Category]** を選び、それを **[凡例]** 領域に追加します。 
     
    ![[フィールド] ウィンドウの横にあるドーナツ](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. 必要に応じて、[グラフのテキストの色とサイズを調整](power-bi-visualization-customize-title-background-and-legend.md)します。 

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
* ドーナツ グラフの各値の合計は、100% になる必要があります。
* カテゴリが多すぎると、読みにくく分かりにくくなります。
* ドーナツ グラフは、個々のセクションを互いに比較するのではなく、特定のセクションを全体と比較するために最もよく使用されます。 

## <a name="next-steps"></a>次の手順
[Power BI のじょうごグラフ](power-bi-visualization-funnel-charts.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)


