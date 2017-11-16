---
title: "Power BI レポートから重要な数値のタイルを作成"
description: "Power BI レポートから重要な数値のタイルを作成"
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
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Power BI レポートから重要な数値のタイルを作成
Power BI ダッシュボードで追跡すべき最重要の項目は 1 つの数値だけという場合もあります。たとえば、総売上高、対前年比の市場シェア、営業案件の総数などがこれに該当します。 重要な数値のタイルを作成するには、[Q&A ボックスに質問を入力](power-bi-visualization-big-number.md)するか、Power BI レポートでタイルを作成します。 この記事では、レポート内でタイルを作成する方法について説明します。

1. [ダッシュボード](service-dashboards.md)を作成して、[データを取得](service-get-data.md)します。
   
   演習用データが必要な場合は、[小売りの分析のサンプルをダウンロード](sample-retail-analysis.md)してください。 
2. レポートを[編集ビュー](service-reading-view-and-editing-view.md)で開きます。
3. レポートで、空白が含まれているページを見つけ出すか、[レポートに新しいページを追加](power-bi-report-add-page.md)する。
4. [フィールド] の一覧で、表示する数値フィールドを選びます。
   
   この例では、 **[Store]** (店舗) テーブルの **[Open Store count]** (開店店舗数) を選びます。 Power BI によって、1 つの数値のみが含まれた縦棒グラフが作成されます。
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. [視覚化] ウィンドウで [カード] アイコンを選びます。
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. ダッシュボードにタイルを追加するには、カードをポイントしてピン アイコン ![](media/power-bi-visualization-big-number-report/pbi_pintile.png) を選びます。 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. タイルを既存のダッシュボードまたは新しいダッシュボードにピン留めします。 
   
   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力します。
8. **[Pin]**(ピン留め) を選択します。
   
   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. **[ダッシュボードへ移動]** を選びます。 ピン留めされた視覚化の[編集と移動](service-dashboard-edit-tile.md)をそこで行うことができます。

## <a name="next-steps"></a>次の手順
[Power BI のダッシュボードのタイル](service-dashboard-tiles.md)

[Power BI のダッシュボード](service-dashboards.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

