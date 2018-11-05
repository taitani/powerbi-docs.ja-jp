---
title: レポートでのビジュアルの相互作用の概要 (レポート ユーザーの場合)
description: レポート ページでビジュアルがどのように相互作用するかについて説明する Power BI エンド ユーザー向けドキュメント。
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/28/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c87f99b768f52fe7f6b565c47ed7e434b167a046
ms.sourcegitcommit: dc8b8a2cf2dcc96ccb46159802ebd9342a7fa840
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49112063"
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI レポートでの視覚化の相互作用
Power BI の優れた機能の 1 つは、レポート ページ上のすべてのビジュアルが相互接続される方法です。 ビジュアルのいずれかのデータ ポイントを選択すると、そのデータを含むページ上の他のすべてのビジュアルが選択に基づいて変化します。 

![ビジュアルの相互作用のビデオ](media/end-user-interactions/interactions.gif)

既定では、レポート ページ上の 1 つのビジュアルを使用して、そのページ上の他のビジュアルに対してクロスフィルター処理、クロス強調表示、ドリルを行うことができます。 たとえば、マップの視覚化で州を選択した時に、その州の縦棒グラフを強調表示し、その 1 つの州に当てはまるデータのみを表示するように折れ線グラフをフィルター処理できます。

「[フィルター処理と強調表示について](../power-bi-reports-filters-and-highlighting.md)」を参照してください。 また、視覚エフェクトが[詳細表示](../power-bi-visualization-drill-down.md)に対応している場合、既定では、ある視覚エフェクトに詳細表示を適用してもレポート ページの他の視覚エフェクトは変更されません。 

ページ上のビジュアルがどのように相互作用するかは、レポート *デザイナー*によって設定されます。 デザイナーには、視覚的な相互作用のオンとオフを切り替えるオプションと、既定のクロスフィルター処理、クロス強調表示、およびドリルの動作を変更するオプションがあります。
  
> [!NOTE]
> *クロスフィルター処理* と *クロス強調表示* という用語は、ここで説明する動作を、**[フィルター]** ウィンドウを使って視覚化のフィルター処理と強調表示を行う場合の動作と区別するために使っています。  

### <a name="next-steps"></a>次の手順
[レポート フィルターの使用方法](../power-bi-how-to-report-filter.md)
