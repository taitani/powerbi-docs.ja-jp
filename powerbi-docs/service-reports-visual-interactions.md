---
title: "レポート内のビジュアルの相互作用を変更します。"
description: "Microsoft Power BI レポートにビジュアルの相互作用を設定する方法を説明します。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI レポートでの視覚化の相互作用
既定では、レポート ページ上の 1 つの視覚化を使って、そのページ上の他の視覚化に処理とクロス強調表示を適用できます。
たとえば、マップの視覚化で州を選択した時に、その州の縦棒グラフを強調表示し、その 1 つの州に当てはまるデータのみを表示するように折れ線グラフをフィルター処理できます。
「[フィルター処理と強調表示について](power-bi-reports-filters-and-highlighting.md)」を参照してください。

この既定の動作を変更するには、**[ビジュアル対話]** コントロールを使います。 ビジュアル対話は、[編集ビュー](service-interact-with-a-report-in-editing-view.md)でのみ使うことができます。 他のユーザーからレポートの共有を受けている場合、ビジュアル対話にアクセスすることはできません。

> [!NOTE]
> *クロスフィルター処理* と *クロス強調表示* という用語は、ここで説明する動作を、**[フィルター]** ウィンドウを使って視覚化のフィルター処理と強調表示を行う場合の動作と区別するために使っています。  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 視覚化を選んでアクティブにします。  
2. 上部のメニュー バーで **[ビジュアルの相互作用]** を選んでオンにします。 レポート ページの他の視覚化をポイントすると、フィルター処理と強調表示のアイコンが表示されることを確認してください。
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. 選択した視覚化が他の視覚化に与える影響を決めます。  
   
   * 他の視覚化にクロスフィルターを適用する場合は、**[フィルター]** アイコン ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png) を選びます。
   * 他の視覚化にクロス強調表示を適用する場合は、**[強調表示]** アイコン ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png) を選びます。
   * 影響を受けないようにする場合は、**[影響なし]** アイコン ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png) を選びます。
4. 必要に応じて、レポート ページの他のすべての視覚化に対して繰り返します。

### <a name="next-steps"></a>次の手順
[レポート フィルターの使用方法](power-bi-how-to-report-filter.md)

[レポート内のフィルターと強調表示](power-bi-reports-filters-and-highlighting.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

