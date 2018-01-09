---
title: "カード視覚エフェクト (別名: 大きな数字のタイル)"
description: "Power BI でカード視覚エフェクトを作成します"
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
ms.date: 12/24/2017
ms.author: mihart
ms.openlocfilehash: 1136aae9af4481a1d55ca3d11ed300242aab187b
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="card-visualizations"></a>カード視覚エフェクト
Power BI のダッシュボードまたはレポートで追跡すべき最重要の項目が 1 つの数値だけという場合もあります。たとえば、総売上高、対前年比の市場シェア、営業案件の総数などがこれに該当します。 この種の視覚エフェクトは、"*カード*" と呼ばれます。 他のほとんどのネイティブな Power BI 視覚エフェクトと同様に、カードもレポート エディターまたは Q&A を使って作成できます。

![カード視覚エフェクト](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>レポート エディターを使ってカードを作成する
次の手順では、「Retail Analysis Sample」を使用します。 作業を進めるために、Power BI サービス (app.powerbi.com) または Power BI Desktop の[サンプルをダウンロード](sample-datasets.md)します。   

1. [空のレポート ページ](power-bi-report-add-page.md)を開始し、**[Store]** \> **[Open store count]** フィールドを選びます。 Power BI サービスを使っている場合は、[編集ビュー](service-interact-with-a-report-in-editing-view.md)でレポートを開く必要があります。

    Power BI によって、1 つの数値のみが含まれた縦棒グラフが作成されます。

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. [視覚化] ウィンドウで [カード] アイコンを選びます。

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. カードをポイントし、ピン留めアイコン ![](media/power-bi-visualization-card/pbi_pintile.png) を選んで、ダッシュボードに視覚エフェクトを追加します。

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. タイルを既存のダッシュボードまたは新しいダッシュボードにピン留めします。

   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力します。
8. **[Pin]**(ピン留め) を選択します。

   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. **[ダッシュボードへ移動]** を選びます。 ピン留めされた視覚化の[編集と移動](service-dashboard-edit-tile.md)をそこで行うことができます。


## <a name="create-a-card-from-the-qa-question-box"></a>Q&A 質問ボックスからカードを作成する
Q&A の質問ボックスは、カードを作成する最も簡単な方法です。 Q&A 質問ボックスは、Power BI サービス (app.powerbi.com) のダッシュボードまたはレポートから利用できます。 以下の手順では、Power BI サービスのダッシュボードからカードを作成する方法について説明します。 Power BI Desktop で Q&A を使ってカードを作成したい場合は、Desktop レポートの Q&A プレビューに関する[こちらの手順に従って](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA)ください。

1. [ダッシュボード](service-dashboards.md)を作成して、[データを取得](service-get-data.md)します。 この例では、[営業案件の分析のサンプル](sample-opportunity-analysis.md)を使います。

1. ダッシュボードの上部にある質問ボックスに、データに関する質問を入力します。 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**ヒント**: Power BI サービスのレポートの場合は、[編集ビュー](service-reading-view-and-editing-view.md)の上部メニュー バーから **[質問する]** を選びます。 Power BI Desktop のレポートの場合は、レポートの空いている領域をダブルクリックして質問ボックスを開きます。

3. たとえば、質問ボックスに「number of opportunities」(営業案件の数) と入力します。

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   質問ボックスでは、役立つ提案や説明が示された後、最終的に合計数が表示されます。  
4. 右上隅にあるピン留めアイコン ![](media/power-bi-visualization-card/pbi_pintile.png) を選んで、カードをダッシュボードに追加します。

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. 既存のダッシュボードまたは新しいダッシュボードに、カードをタイルとしてピン留めします。

   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。 現在のワークスペース内のダッシュボードのみを選択できます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力すると、現在のワークスペースに追加されます。
6. **[Pin]**(ピン留め) を選択します。

   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. **[ダッシュボードへ移動]** を選択して新しいタイルを表示します。 ここでは、ダッシュボード上のタイルに対して、[名前の変更、サイズ変更、ハイパーリンクの追加、位置変更など](service-dashboard-edit-tile.md)を行うことができます。

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
- 質問ボックスがまったく表示されない場合は、システム管理者またはテナント管理者に問い合わせてください。    
- Desktop を使っていて、レポートの空き領域をダブルクリックしても Q&A が開かない場合は、Q&A を有効にする必要がある場合があります。  **[ファイル] > [オプションと設定] > [オプション] > [プレビュー機能] > [Q&A]** の順に選んでから、Desktop を再起動します。


## <a name="next-steps"></a>次の手順
[Power BI のダッシュボードのタイル](service-dashboard-tiles.md)

[Power BI のダッシュボード](service-dashboards.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
