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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Power BI でのドーナツ グラフ (チュートリアル)
ドーナツ グラフは、全体に対する部分の関係が示される点で円グラフと似ています。 唯一の違いは、中央が空白で、ラベルまたはアイコン用の領域を確保できることです。

## <a name="create-a-doughnut-chart"></a>ドーナツ グラフの作成
先に進むには、Power BI にサインインして、**[データの取得]** \> **[サンプル]** \> **[Retail Analysis Sample]** \> **[接続]** を選びます。 

1. ダッシュボードで、**[Total Stores]** タイルを選び、"Retail Analysis Sample" レポートを開きます。
2. **[レポートの編集]** を選び、編集ビューでレポートを開きます。
3. [新しいレポートのページを追加](power-bi-report-add-page.md)します。
4. 今年度の売上がカテゴリ別に表示されるドーナツ グラフを作成します。
   
   * **[フィールド]** ウィンドウで、**\[Sales] \(売上)** > \>**\[Last Year Sales] \(前年度の売上)** を選びます。
   * ドーナツ グラフに変換します。 [Last Year Sales] が **[値]** 領域にない場合は、そこにドラッグします。
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * **[Item]** \> **[Category]** を選び、それを **[凡例]** 領域に追加します。 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

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

