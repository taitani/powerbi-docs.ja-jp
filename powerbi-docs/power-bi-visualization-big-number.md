---
title: "Q&A から重要な数値のタイルを作成"
description: "質問をして Power BI ダッシュボードに重要な数値のタイルを作成"
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 559484c341ec017890a4075a393d5ce211843b5f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-qa"></a>Q&A から重要な数値のタイルを作成
Power BI ダッシュボードで追跡すべき最重要の項目は 1 つの数値だけという場合もあります。たとえば、総売上高、対前年比の市場シェア、営業案件の総数などがこれに該当します。 [Power BI レポートで重要な数値のタイルを作成](power-bi-visualization-big-number-report.md)するか、Q&A ボックスに質問を入力してタイルを作成します。 この記事では、Q&A 内でタイルを作成する方法について説明します。

![](media/power-bi-visualization-big-number/pbi_opptuntiescard.png)

質問ボックスは、このような数値タイルを作成する最も簡単な方法です。

1. [ダッシュボード](service-dashboards.md)を作成して、[データを取得](service-get-data.md)します。 この例では、[営業案件の分析のサンプル](sample-opportunity-analysis.md)を使います。
2. ダッシュボードの上部にある質問ボックスに、データに関する質問を入力します。 この例では、営業案件の分析のサンプルを使います。
   
   ![](media/power-bi-visualization-big-number/power-bi-q-and-a-box.png)
3. たとえば、質問ボックスに「number of opportunities」(営業案件の数) と入力します。
   
   ![](media/power-bi-visualization-big-number/power-bi-ask.png)
   
   質問ボックスに **[Showing opportunity count]** (営業案件数を表示) という候補が表示され、合計数が表示されます。  
4. 右上隅のピン アイコン ![](media/power-bi-visualization-big-number/pbi_pintile.png) を選んで、数値タイルをダッシュボードに追加します。 
   
   ![](media/power-bi-visualization-big-number/power-bi-pin.png)
5. タイルを既存のダッシュボードまたは新しいダッシュボードにピン留めします。 
   
   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。 現在のワークスペース内のダッシュボードのみを選択できます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力すると、現在のワークスペースに追加されます。
6. **[Pin]**(ピン留め) を選択します。
   
   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。  
   
   ![](media/power-bi-visualization-big-number/power-bi-success.png)
7. **[ダッシュボードへ移動]** を選択して新しいタイルを表示します。 ここでは、ダッシュボード上のタイルに対して、[名前の変更、サイズ変更、ハイパーリンクの追加、位置変更など](service-dashboard-edit-tile.md)を行うことができます。 
   
   ![](media/power-bi-visualization-big-number/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
質問ボックスがまったく表示されない場合は、システム管理者またはテナント管理者に問い合わせてください。

## <a name="next-steps"></a>次の手順
[Power BI のダッシュボードのタイル](service-dashboard-tiles.md)  
[Power BI のダッシュボード](service-dashboards.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

