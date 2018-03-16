---
title: "レポートから Power BI ダッシュボードにタイルをピン留め"
description: "レポートから Power BI ダッシュボードにタイルをピン留めします。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lJKgWnvl6bQ
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 8fbc2ecafb34339a68b4ca5ecd0fa063082644a2
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2018
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-a-report"></a>レポートから Power BI ダッシュボードにタイルをピン留め
## <a name="pinning-tiles-from-a-report"></a>レポートからタイルをピン留め
新しい[ダッシュボード タイル](service-dashboard-tiles.md)を追加する方法の 1 つは、[Power BI レポート](service-reports.md)から追加することです。 実際、レポートから多数の新しいタイルを追加できます。  各タイルは、クリックするとレポートに戻るリンクです。

レポート ページ全体をダッシュボードにピン留めできます。  これは、 *ライブ* タイルのピン留めとも呼ばれています。  ダッシュボードでタイルと対話でき、個々の視覚化タイルとは異なり、レポートに加えられる変更はダッシュボードと同期されているため、*ライブ*と呼ばれます。 詳しくは以下をご覧ください。

他のユーザーと共有したレポートから、または Power BI Desktop から、タイルをピン留めすることはできません。 

> **ヒント**: 一部の視覚エフェクトでは、背景画像が使われています。 背景画像が大きすぎる場合、ピン留めが動作しない可能性があります。  画像のサイズを小さくするか、画像の圧縮を使ってみてください。  
> 
> 

## <a name="pin-a-tile-from-a-report"></a>レポートからタイルをピン留めする
Amanda が Power BI レポートからビジュアルとイメージを固定することでダッシュ ボードを作成している様子をご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

それでは、Power BI サンプル レポートの 1 つを使用して、独自のダッシュ ボードを作成していきましょう。

1. ピン留めする視覚化にポインターを合わせ、ピン ![](media/service-dashboard-pin-tile-from-report/pbi_pintile_small.png) アイコンを選びます。 Power BI で **[ダッシュボードにピン留め]** 画面が開きます。
   
     ![[ダッシュボードにピン留め] ウィンドウ](media/service-dashboard-pin-tile-from-report/pbi_themes2.png)
2. 既存のダッシュボードと新規のダッシュボードのどちらにピン留めするかを決定します。
   
   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。 共有してもらったダッシュボードはドロップダウンに表示されません。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力します。
3. 場合によっては、ピン留めする項目には既に *テーマ* が適用されている場合があります。  たとえば、Excel ブックからピン留めされたビジュアルの場合です。 その場合、タイルに適用するテーマを選びます。
4. **[Pin]**(ピン留め) を選択します。
   
   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。
   
   ![成功メッセージ](media/service-dashboard-pin-tile-from-report/pinsuccess.png)
5. ナビゲーション ウィンドウから、新しいタイルを持つダッシュボードを選びます。 タイルを選んで、レポートに戻ります。 または、[タイルの表示と動作を編集](service-dashboard-edit-tile.md)します。

## <a name="pin-an-entire-report-page"></a>レポート ページ全体をピン留めする
別のオプションとして、レポート ページ全体をダッシュボードにピン留めすることもできます。 これは、複数の視覚化を一度にピン留めする簡単な方法です。  さらに、ページ全体をピン留めする場合、タイルは *ライブ* であり、ダッシュボードで直接それらのタイルと対話できます。 レポート エディターで視覚化に加えるすべての変更 (フィルターの追加、またはチャートで使用されるフィールドの変更など) は、ダッシュボード タイルにも反映されます。  

詳細については、「[レポート ページ全体をピン留めする](service-dashboard-pin-live-tile-from-report.md)」をご覧ください。

## <a name="next-steps"></a>次の手順
[Power BI のダッシュボード](service-dashboards.md)

[Power BI のダッシュボードのタイル](service-dashboard-tiles.md)

[Power BI のレポート](service-reports.md)

[Power BI でのデータの更新](refresh-data.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

