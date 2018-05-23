---
title: Power BI Q&A の概要
description: 小売りの分析のサンプルを使用して Power BI サービスの Q&A を使い始めます
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: c567921b765f03fbaa11f2b98724cea1a1ce1905
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="get-started-with-power-bi-qa"></a>Power BI Q&A の概要
## <a name="use-power-bi-qa-with-the-retail-analysis-sample"></a>小売りの分析のサンプルで Power BI Q&A を使用する
自然言語を使用して質問するのが、データから回答を得る最も速い方法である場合があります。  このクイック スタートでは、同じ視覚エフェクトを作成するための 2 つの異なる方法として、1 つ目はレポートでビルドする方法、2 つ目は Q&A で質問する方法を説明します。 Power BI サービスを使いますが、手順は Power BI Desktop を使う場合とほぼ同様です。

作業を進めるには、編集できるレポートが必要なので、Power BI で使用可能なサンプルの 1 つを使います。

## <a name="method-1-using-the-report-editor"></a>方法 1: レポート エディターの使用
1. Power BI ワークスペースから、**[データの取得]** \> **[サンプル]** \> **[小売りの分析のサンプル]**  >  **[接続]** を選択します。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. ダッシュボードには、「Last Year Sales and This Year Sales (前年度の売上高と今年度の売上高)」の面グラフ タイルがあります。  このタイルを選択します。 
   
   * このタイルが Q&A を使用して作成された場合、タイルを選択すると Q&A が開きます。 
   * しかし、このタイルがレポートで作成された場合は、この視覚化が含まれたページにレポートが表示されます。
3. **[レポートの編集]** を選択して、レポートを編集ビューで開きます。  レポートの所有者でない場合は、編集ビューでレポートを開くオプションはありません。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. 面グラフを選択して、 **[フィールド]** ウィンドウで設定を確認します。  レポートの作成者は、これらの 3 つの値 \(**\[時間] > \[FiscalMonth]**、**\[Sales] \(売上) > \[This Year Sales] \(今年の売上高)**、**\[Sales] \(売上) > \[Last Year Sales] \(前年の売上高) > \[Value] \(値)**) を選択して、それらを **\[ビジュアル]** と **\[軸]** に編成して、このグラフを作成しました。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>方法 2: Q&A の使用
これと同じデータの折れ線グラフを Q&A を使用して作成するには、次のようにします。

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. 小売りの分析のサンプル ダッシュボードに戻ります。
2. 自然言語を使用して、質問ボックスに次のように入力します。
   
   **今年度の売上高と前年度の売上高は、月別の面グラフで表すとどうなりますか**
   
   質問を入力していくと、Q&A が回答を表示するために最適な視覚化を選択し、質問を変更するにつれ視覚化が動的に変化します。 また、Q&A は、候補機能、オートコンプリート、およびスペルの修正によって質問の形式を整えるようにユーザーを助けます。
   
   質問の入力が完了すると、結果はレポートで確認したのとまったく同じグラフになります。  しかし、この方法で作成した方が速くできます。
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. レポートの場合と同様に、Q&A 内で、[視覚化]、[フィルター]、[フィールド] ウィンドウにアクセスできます。  これらのウィンドウを開くと、ビジュアルをさらに試したり、変更したりできます。
4. グラフをダッシュボードにピン留めするには、ピン アイコン ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) を選択します。

## <a name="next-steps"></a>次の手順
[Power BI での Q&A](power-bi-q-and-a.md)

[データを Power BI Q&A に適合させる方法](service-prepare-data-for-q-and-a.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

