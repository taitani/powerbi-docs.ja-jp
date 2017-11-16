---
title: "Power BI の読み取りビューでレポートと対話する"
description: "Power BI の読み取りビューでレポートと対話する"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Power BI の読み取りビューでレポートと対話する
## <a name="reading-view"></a>読み取りビュー
読み取りビューは[編集ビュー](service-interact-with-a-report-in-editing-view.md)ほどインタラクティブではありませんが、それでもデータを探索する多くのオプションがあります。 これは、読み取りビューでのみ開くことができる、[共有された](service-share-dashboards.md)レポートを表示するときに便利です。

読み取りビューを使用すると、データを楽しく安全に再生し、データをよく理解することができます 読み取りビューでは、ページ上のビジュアルをクロス強調表示およびクロスフィルター処理できます。  あるビジュアルで値を強調表示または選択するだけで、他のビジュアルに与える影響がすぐに表示されます。 フィルター ペインを使用して、レポート ページにフィルターを追加、フィルターを変更、または視覚エフェクトでの値の並べ替え方法を変更します。 フィルター処理や強調表示がレポートと共に保存されることはありません。

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>ページで関連する視覚エフェクトをクロス強調表示する
同じ 1 つのレポート ページにある視覚化は、相互に「つながって」います。  つまり、1 つの視覚化で 1 つ以上の値を選択すると、同じ値を使う他の視覚化がその選択内容に基づいて変更されます。

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> 1 つの視覚化で複数の要素を選択するには、Ctrl キーを押したまま選択します。
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>視覚要素の上にポインターを置くと、詳細情報が表示されます。
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>視覚化のデータの並べ替え
省略記号 (...) を選んで **[並べ替え]** メニューを開きます。 ドロップダウン矢印を選択して並べ替えの基準となるフィールドを選ぶか、AZ アイコンを選択して昇順/降順を切り替えます。 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>フィルターとの対話
レポート作成者がレポートのページにフィルターを追加してある場合、ユーザーは読み取りビューでこれらのフィルターと対話することができます。 変更はレポートには保存されません。

1. 右上隅にあるフィルター アイコンを選択します。
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. 選択したビジュアルに適用されているフィルター (ビジュアル レベル フィルター)、レポート ページ全体に適用されているフィルター (ページ レベル フィルター)、レポート全体に適用されているフィルター (レポート レベル フィルター) がすべて表示されます。
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. フィルターにポインターを置き、下矢印を選択して展開します。
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. フィルターを変更し、ビジュアルがどのように影響を受けるかを確認します。  
   
   * この例では、**[Chain]** にページ レベル フィルターがあります。 チェックマークを付け替えて、**[Lindseys]** ではなく **[Fashions Direct]** に変更します。
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * あるいは、**[Chain]** のフィルターを完全に削除します。消しゴムアイコン ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) を選択するか、両方のチェーン ストアを選択します。
   * **[District]** ページ レベル フィルターを選択し、**[高度なフィルター処理]** に切り替えます。 **FD** で始まり、数字 4 を含まない地区だけを表示するようにフィルターします。
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

詳しくは、「[レポートにフィルターを追加する](power-bi-report-add-filter.md)」および「[レポートのフィルターと強調表示について](power-bi-reports-filters-and-highlighting.md)」をご覧ください。

## <a name="zoom-in-on-individual-visuals"></a>個々のビジュアルにズームイン
ビジュアルをポイントし、**[フォーカス モード]** アイコン ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg) を選択します。 下の画像のように、フォーカス モードで視覚エフェクトを表示すると、レポート キャンバス全体を埋めるよう拡大されます。

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

その同じ視覚エフェクトを、メニュー バー、フィルター ウィンドウ、他の Chrome に影響を与えずに表示するには、上部メニュー バー ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png) の **[全画面表示]** アイコンを選択します。

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

詳細については、「[Focus mode for reports](service-focus-mode.md)」 (レポートのフォーカス モード) と「[Full Screen mode for reports](service-fullscreen-mode.md)」 (レポートの全画面表示モード) を参照してください。

## <a name="adjust-the-display-dimensions"></a>表示サイズを調整する
レポートは、さまざまなデバイスで表示され、その画面サイズや縦横比も異なります。  既定のレンダリングでは、ご使用のデバイスの表示サイズに合わない場合があります。  調整するには、**[ビュー]** を選択し、次のどれかを選びます。

* ページに合わせる: コンテンツをページに合うように拡大縮小します
* 幅に合わせる: コンテンツをページの幅に合わせて拡大縮小します
* 実際のサイズ: フル サイズでコンテンツを表示します  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  読み取りビューで選択した表示オプションの効果は一時的なので、レポートを閉じると保持されません。

  詳細については、「[チュートリアル: レポートの表示設定を変更する](power-bi-change-report-display-settings.md)」を参照してください。

## <a name="next-steps"></a>次の手順
[Power BI のレポート](service-reports.md)

[編集ビューを開く](service-reading-view-and-editing-view.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

