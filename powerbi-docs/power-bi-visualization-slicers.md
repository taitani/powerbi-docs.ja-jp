---
title: "Power BI のスライサー (チュートリアル)"
description: "チュートリアル: Power BI のスライサー"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 619f694e6e3ed167a14262994c1c978d5b4ea2e0
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Power BI サービスのスライサー (チュートリアル)
営業担当副社長は、部署全体および各地域の営業マネージャーそれぞれのメトリックスの数字を管理したいと考えています。 この場合、各マネージャーに対して別々のレポート ページを作成することや、スライサーを使用することができます。 スライサーを使用すると、ページの他の視覚化に表示されるデータセットの一部を絞り込むことができます。  スライサーは一種のフィルターです。

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>スライサーを使用する場合
スライサーは、次の状況で最適な選択です。

* レポート キャンバスによく使うフィルターまたは重要なフィルターを表示してアクセスしやすくする場合。
* ドロップダウン リストを開いてフィルターの詳細を確認することなく、現在のフィルターされた状態を簡単に表示する場合。
* 不要ですが、フィルターには使用できるように列を非表示にして、テーブルを整理し、サイズを小さくする場合。
* さらに絞り込まれたレポートを作成する場合。スライサーは浮動オブジェクトなので、ユーザーの注目を集めたいレポートの該当部分の横に配置できます。

## <a name="create-a-slicer"></a>スライサーの作成
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. [編集ビュー](service-interact-with-a-report-in-editing-view.md)で[小売りの分析のサンプル](sample-retail-analysis.md)を開き、[新しいレポート ページを追加](power-bi-report-add-page.md)します。
2. [フィールド] ウィンドウから **[District]、[District Manager]** の順に選択します。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. 視覚化をスライサーに変換します。 [視覚化] ウィンドウでスライサー アイコンを選択します。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>スライサーの書式設定
1. [視覚化] ウィンドウで、スライサーを選択した状態で、ペイント ローラ アイコン ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) を選択して書式設定のオプションを表示します。
2. **[全般]、[輪郭の色]** の順に選択します。次に、濃い青を選択し、**[太さ]** を **6** に変更します。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. **[選択コントロール]**の既定では、 **[すべて選択]** が **[オフ]** 、 **[単一選択]** が **[オン]**です。 つまり、複数の名前を同時に選択する場合は、Ctrl キーを使用する必要があります。 **[すべて選択]** を **[オン]** に、 **[単一選択]** を **[オフ]**に変更します。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * スライサーの一覧の一番上に、 **[すべて選択]** が表示されるようになります。 **[すべて選択]** をクリックすると、すべての名前が選択された状態と、名前が選択されていない状態が切り替わります。
   * Ctrl キーを使用せずに、複数の名前を選択できるようになります。
4. **[項目]**で、テキスト サイズを 14 ポイントに上げます。  同僚がこのスライサーに気づくようにしたいと考えています。
5. 最後に、 **[フォントの色]** を濃い赤に設定します。  これで、スライサーで選択されている名前と、選択されていない名前が区別されます。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. スライサーで使用できるその他のオプションを自由に試してみてください。

## <a name="use-the-slicer-in-a-report"></a>レポートでスライサーを使用する
1. レポート ページにいくつか視覚化を追加するか、[小売りの分析のサンプル レポート](sample-retail-analysis.md)を開いて、**[District Monthly Sales]** (地域別/月別の売上) タブを選択します。
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Carlos のレポート ページをスライスします。 他の視覚化は、その選択を反映して更新されます。
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. 地域マネージャーの姓のアルファベット順でスライサーを並べ替えます。  スライサーの右上にある省略記号 [...] を選択して、 **[District Manager]**(地域マネージャー) を選択します。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>スライサーがページの他のビジュアルに与える影響をコントロールする
スライサーでレポート ページの一部のビジュアルのみにフィルターを適用する場合  これを設定するには、**[ビジュアル対話]** コントロールを使用します。

**注**: **[ビジュアル対話]** が表示されない場合、![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png) の代わりにそのアイコンを探します。 いずれも表示されない場合は、レポートの[編集ビュー](service-reading-view-and-editing-view.md)であることを確認します。

1. スライサーを選択してアクティブにし、メニュー バーから **[ビジュアル対話]** を選択します。
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. フィルター コントロールは、ページの他のビジュアルすべての上に表示されます。 スライサーでビジュアルをフィルター処理する必要がある場合は、**[フィルター]** アイコンを選択します。  スライサーがビジュアルに影響を与えないよう設定する場合は、**[なし]** アイコンを選択します。
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

詳しくは、「[Power BI レポートでの視覚化の相互作用](service-reports-visual-interactions.md)」をご覧ください。

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Power BI のスライサーに関する考慮事項とトラブルシューティング
Power BI では、スライサーの使用に関する以下の制限事項があります。

1. スライスは入力フィールドをサポートしません。
2. 1 つのスライサーをレポート全体で使用することはできません。 スライサーは現在のページにのみ影響を与えます。
3. スライサーはダッシュボードに固定表示することはできません。
4. スライサーはドリルダウンでサポートされていません。    
5. スライサーは、ビジュアル レベル フィルターをサポートしていません。

Power BI を改善する方法について、ご意見がありましたら、 [コメントを送信](https://ideas.powerbi.com/forums/265200-power-bi-ideas)してください。

## <a name="next-steps"></a>次の手順
 [視覚化をレポートに追加する](power-bi-report-add-visualizations-i.md)

 [Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI - 基本的な概念](service-basic-concepts.md)

[試してみる (無料)](https://powerbi.com/)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

