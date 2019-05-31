---
title: レポート内のビジュアルの相互作用について理解する
description: レポート ページでビジュアルがどのように相互作用するかについて説明する Power BI エンド ユーザー向けドキュメント。
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413184"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Power BI のレポート内でビジュアルがどのように相互作用するか
Power BI の優れた機能の 1 つは、レポート ページ上のすべてのビジュアルが相互接続される方法です。 ビジュアルのいずれかのデータ ポイントを選択すると、そのデータを含むページ上の他のすべてのビジュアルが選択に基づいて変化します。 

![ビジュアルの相互作用のビデオ](media/end-user-interactions/interactions.gif)

データ ポイント、レポート ページ上の 1 つの視覚化がクロス フィルター処理を選択すると、クロス強調表示の場合、既定で、ページ上の他の視覚化の詳細を表示します。 

この方法の 1 つの値のデータを識別するためには別に貢献します。 たとえば、月グラフでは、別の合計ユニット内の各列には、そのセグメントからのコントリビューションを強調表示、ドーナツ グラフでモデレート セグメントを選択し、右側の折れ線グラフはフィルターを適用しました。

![ビジュアル対話の画像](media/end-user-interactions/power-bi-interactions.png)

「[フィルター処理と強調表示について](../power-bi-reports-filters-and-highlighting.md)」を参照してください。 

ページ上のビジュアルがどのように相互作用するかは、レポート *デザイナー*によって設定されます。 デザイナーには、視覚的な相互作用のオンとオフを切り替えるオプションと、既定のクロスフィルター処理、クロス強調表示、およびドリルの動作を変更するオプションがあります。 
  
> [!NOTE]
> *クロスフィルター処理* と *クロス強調表示* という用語は、ここで説明する動作を、 **[フィルター]** ウィンドウを使って視覚化のフィルター処理と強調表示を行う場合の動作と区別するために使っています。  

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
- レポートに視覚エフェクトをサポートしている場合[ドリル](../power-bi-visualization-drill-down.md)既定では、1 つの視覚化のドリルダウン影響を与えません他の視覚化、レポート ページ上にします。     
- VisualA visualB と対話するを使用する場合は、visualB に visualA からビジュアル レベル フィルターが適用されます。

## <a name="next-steps"></a>次の手順
[レポート フィルターの使用方法](../power-bi-how-to-report-filter.md)
