---
title: "Power BI でのドーナツ グラフ (チュートリアル)"
description: "チュートリアル: Power BI でのドーナツ グラフ"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: dca772fd2a1b8f40fa61f1abc41145e8ff6e5a8a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Power BI でのドーナツ グラフ (チュートリアル)
ドーナツ グラフは、全体に対する部分の関係が示される点で円グラフと似ています。 唯一の違いは、中央が空白で、ラベルまたはアイコン用の領域を確保できることです。

## <a name="create-a-doughnut-chart"></a>ドーナツ グラフの作成
以下の手順では、小売りの分析のサンプルを使って、今年の売上をカテゴリ別に表示するドーナツ グラフを作成します。 作業を進めるために、Power BI サービス (app.powerbi.com) または Power BI Desktop の[サンプルをダウンロード](sample-datasets.md)します。

1. [空のレポート ページ](power-bi-report-add-page.md)を開始し、**[SalesStage]** \> **[Sales Stage]** フィールドを選びます。 Power BI サービスを使っている場合は、[編集ビュー](service-interact-with-a-report-in-editing-view.md)でレポートを開いていることを確認します。

2. [フィールド] ウィンドウで、**[Sales]** \> **[Last Year Sales]** を選びます。  
   
3. [視覚化] ウィンドウで、ドーナツ グラフのアイコン ![ドーナツ グラフ アイコン]() を選んで、横棒グラフをドーナツ グラフに変換します。 **[Last Year Sales]** が **[値]** 領域にない場合は、そこにドラッグします。
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. **[Item]** \> **[Category]** を選び、それを **[凡例]** 領域に追加します。 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. 必要に応じて、[グラフのテキストの色とサイズを調整](power-bi-visualization-customize-title-background-and-legend.md)します。 

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
* ドーナツ グラフの各値の合計は、100% になる必要があります。
* カテゴリが多すぎると、読みにくく分かりにくくなります。
* ドーナツ グラフは、個々のセクションを互いに比較するのではなく、特定のセクションを全体と比較するために最もよく使用されます。 

## <a name="next-steps"></a>次の手順
[Power BI のレポート](service-reports.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI レポートでの視覚化](power-bi-report-visualizations.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

