---
title: Power BI Q & A でビジュアルを作成します。
description: Q & A、小売りの分析のサンプルを使用して、Power BI サービスでビジュアルを作成する方法を学習します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 580b387f8c763b0457bd32a71bfbccd90d4040a3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625236"
---
# <a name="create-a-visual-with-power-bi-qa"></a>Power BI Q & A でビジュアルを作成します。

自然言語を使用して質問するのが、データから回答を得る最も速い方法である場合があります。  この記事で、同じ視覚エフェクトを作成する 2 つの方法に注目します。 最初に、Q & A で質問を入力し、次に、レポートでビルドします。 レポートでは、ビジュアルを作成する Power BI サービスを使用しますが、プロセスは、Power BI Desktop を使用してほぼ同じです。

![Power BI の塗り分けグラフ](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-visual.png)

作業を進めるには、編集できるレポートが必要なので、Power BI で使用可能なサンプルの 1 つを使います。

## <a name="create-a-visual-with-qa"></a>Q & A でビジュアルを作成します。

すれば Q & A を使用してこの折れ線グラフを作成する方法でしょうか。

1. Power BI ワークスペースから、 **[データの取得]** \> **[サンプル]** \> **[小売りの分析のサンプル]**  >  **[接続]** を選択します。

1. 小売りの分析のサンプル ダッシュ ボードを開き、Q & A ボックスにカーソルを置きます**データについて質問する**します。

    ![Q & A ボックスにカーソルを置きます](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-cursor-in-qna-box.png)

2. Q & A ボックスでは、この質問のようなものを入力します。
   
    **今年の売上と昨年の売上、月別の面グラフで**
   
    質問を入力していくと、Q&A が回答を表示するために最適な視覚化を選択し、質問を変更するにつれ視覚化が動的に変化します。 また、Q&A は、候補機能、オートコンプリート、スペルの修正によって質問の形式を整えるようにユーザーを助けます。 Q & A は、小規模な言い回し変更をお勧めします:"今年の売上と昨年の売上を*時間月*面グラフ"。  

    ![Q & A の表現を修正しました。](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-corrected-create-filled-chart.png)

4. 提案を受け入れるように文を選択します。 
   
   質問の入力が完了したら、ダッシュ ボードに表示される同じグラフになります。
   
   ![Q & A 入力面グラフ](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-filled-chart.png)

4. グラフをダッシュボードにピン留めするには、ピン アイコンを選択します。 ![ピン留めアイコン](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) をタップします。

## <a name="create-a-visual-in-the-report-editor"></a>レポート エディターでビジュアルを作成する

1. 小売りの分析のサンプル ダッシュボードに戻ります。
   
2. ダッシュ ボードには、同じの面グラフ タイルには「Last Year Sales と今年の売上」が含まれています  このタイルを選択します。 Q & A で作成したタイルを選択しないでください。 これを選択すると、Q & A に開きます この視覚エフェクトを含むページが開きますので、レポートでは、元の面グラフ タイルが作成されました。

    ![小売りの分析のサンプルのダッシュボード](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. **[レポートの編集]** を選択して、レポートを編集ビューで開きます。  レポートの所有者でない場合は、編集ビューでレポートを開くオプションはありません。
   
    ![レポートの編集ボタン](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. 面グラフを選択して、 **[フィールド]** ウィンドウで設定を確認します。  レポートの作成者は、これら 3 つの値を選択してこのグラフを作成する (**Last Year Sales**と**This Year Sales > 値**から、 **Sales**テーブル、および**FiscalMonth**から、**時間**テーブル) し、それらの**軸**と**値**wells です。
   
    ![視覚化ウィンドウ](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

    最終的な同じビジュアルが表示されます。 この方法を作成することはありませんでした複雑すぎるようです。 簡単に Q & A で作成することでした。

## <a name="next-steps"></a>次の手順

- [ダッシュ ボードとレポートで Q & A を使用します。](power-bi-tutorial-q-and-a.md)  
- [Q & A のコンシューマー](consumer/end-user-q-and-a.md)
- [データを Power BI Q&A に適合させる方法](service-prepare-data-for-q-and-a.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

