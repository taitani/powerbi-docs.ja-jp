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
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Power BI のスライサー (チュートリアル)
営業担当副社長は、部署全体および各地域の営業マネージャーそれぞれのメトリックスのいくつかを管理したいと考えています。 この場合、各マネージャーに対して別々のレポートを作成することや、スライサーを使用することができます。 スライサーを使用すると、レポートの他の視覚化に表示されるデータセットの一部を絞り込むことができます。 スライサーは一種のフィルターです。

このチュートリアルでは、無料の[小売りの分析のサンプル](sample-retail-analysis.md)を使って、スライサーを作成して書式設定し、それを使ってレポートをフィルター処理する手順について説明します。 スライサーを書式設定して使用する方法がわかります。 

![スライサー](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>スライサーを使用する場合
スライサーは、次のような場合に最適です。

* レポート キャンバスによく使うフィルターまたは重要なフィルターを表示してアクセスしやすくする。
* ドロップダウン リストを開くことなく、現在のフィルターされた状態を簡単に表示する。 
* データ テーブルで不要な非表示の列でフィルター処理する。
* 重要なビジュアルの隣にスライサーを配置することにより、レポートを絞り込む。

Power BI のスライサーには次の制限があります。

- スライスは入力フィールドをサポートしません。
- スライサーはダッシュボードに固定表示することはできません。
- スライサーはドリルダウンでサポートされていません。
- スライサーは、ビジュアル レベル フィルターをサポートしていません。

## <a name="create-a-slicer"></a>スライサーの作成

このチュートリアルでは、リスト スライサーを使います。 数値データ型および日付/時刻データ型には、範囲スライサーを作成できます。 範囲スライサーの作成と使用については、「[Power BI Desktop で数値範囲スライサーを使用する](desktop-slicer-numeric-range.md)」または次のビデオをご覧ください。
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Power BI Desktop または Power BI の[編集ビュー](service-interact-with-a-report-in-editing-view.md)で[小売りの分析のサンプル](sample-retail-analysis.md)を開いて、[新しいレポート ページを追加](power-bi-report-add-page.md)します。
2. [フィールド] ウィンドウの [District] で**[District Manager]** を選択して、新しい視覚エフェクトを作成します。
    
    ![新しいグラフ](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. [視覚化] ウィンドウで **[スライサー]** アイコン ![スライサー アイコン](media/power-bi-visualization-slicers/slicer-icon.png) を選択して、新しい視覚エフェクトをスライサーに変換します。 
    
    ![スライサーに変換する](media/power-bi-visualization-slicers/2-slicer.png)

[スライサー] アイコンを選択して新しいスライサーを作成してから、データ フィールドを選択するか、[フィールド] ボックスにドラッグして、作成することもできます。

>[!TIP]
>データ値でリスト スライサーの項目を並べ替えることができます。 アルファベットの逆順でスライサーの項目を並べ替えるには、スライサーの右上隅にある省略記号 [...] を選択し、**[Sort by District Manager]\(並べ替え: District Manager\)** を選択します。 既定の設定はアルファベットの昇順ですが、昇順と降順が切り替わります。 

## <a name="format-the-slicer"></a>スライサーの書式設定
District Manager スライサーにビジュアルの書式設定を適用します。
1. [視覚化] ウィンドウでスライサーを選択し、[書式] アイコン ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) を選択して書式設定コントロールを表示します。 
    
    ![書式設定](media/power-bi-visualization-slicers/3-format.png)
    
2. 各カテゴリの横にあるドロップダウン矢印をクリックしてオプションを表示し、編集します。 

### <a name="general-options"></a>[全般] オプション
1. **[輪郭の色]** で赤を選び、**[輪郭の太さ]** を "2" に変更します。 ヘッダーと項目の輪郭または下線 (有効になっている場合) の色と太さが設定されます。 
2. [方向] の既定値は [縦] で、項目の前に選択ボックスがある縦のリスト スライサーが作成されます。 項目が横に並んだスライサーを作成するには、**[横]** を選択します。 横方向を選ぶと、スライサーのサイズと形状および項目の書式に応じて、テキスト、ボタン、タイルのさまざまな配置を生成できます。 
    
    ![横](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. **[レスポンシブ]** レイアウトを [オン] にすると、横方向のスライサー項目のサイズと配置が、スライサーのサイズと形状に合わせて変更されます。 非常に小さいサイズでは、スライサーはフィルター アイコンになります。 
    
    ![レスポンシブ](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >レスポンシブ レイアウトの変更により、ユーザーが設定した特定の見出しと項目の書式設定が上書きされることがあります。 
    
4. 異なる項目のサイズと配置 (横並びのボタンなど) を作成するには、**[X 方向の位置]**、**[X 方向の位置]**、**[幅]**、**[高さ]** でスライサーの位置とサイズを数値で指定するか、キャンバス上で直接スライサーを移動およびサイズ変更します。 

    ![横並びのボタン](media/power-bi-visualization-slicers/6-buttons.png)

横方向およびレスポンシブの書式設定については、「[Power BI でサイズを変更することが可能なレスポンシブ スライサーの作成](power-bi-slicer-filter-responsive.md)」をご覧ください。

### <a name="selection-controls-options"></a>[選択範囲のコントロール] のオプション
1. [Show Select All]\([すべて選択] オプションを表示する\) は既定ではオフになっています。 すべての項目の選択と選択解除を切り替える [すべて選択] 項目をスライサーに追加するには、**[オン]** にします。 すべての項目を選択してから 1 つの項目をクリックして選択を解除すると、"is-not" タイプのフィルターを使用できます。 
    
    ![すべて選択](media/power-bi-visualization-slicers/7-select-all.png)
    
2. [単一選択] は既定ではオンになっています。 各項目をクリックするとその項目が選択され、Ctrl キーを押しながらクリックすると複数の項目を選択できます。 Ctrl キーを押さなくても複数の項目を選択できるようにするには、[単一選択] を **[オフ]** にします。 各項目を再度クリックすると選択が解除されます。 

### <a name="header-options"></a>[ヘッダー] のオプション
[ヘッダー] は既定ではオンになっており、スライサーの上部にデータ フィールドの名前が表示されます。 
1. ヘッダー テキストの書式を設定し、**[フォントの色]** を赤、**[テキスト サイズ]** を 14 pt、**[フォント ファミリ]** を Arial Black にします。 
2. [アウトライン] で **[下端のみ]** を選択し、[全般] オプションで設定したサイズと色で下線を生成します。 

### <a name="item-options"></a>[項目] のオプション
1. 項目のテキストと背景の書式を設定し、**[フォントの色]** を黒、**[背景]** を薄い赤、**[テキスト サイズ]** を 10 pt、**[フォント ファミリ]** を Arial にします。 
2. [アウトライン] で **[フレーム]** を選択し、[全般] オプションで設定したサイズと色で各項目を境界線で囲みます。 
    
    ![書式設定済み](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- 横方向の場合、選択されていない項目は指定したテキスト色と背景色で表示され、選択された項目はシステムの既定値 (通常は黒い背景と白いテキスト) を使用します。 
    >- 縦方向の場合、項目は常に指定した色で表示され、選択ボックスはオンの場合は常に黒で表示されます。 

### <a name="other-formatting-options"></a>その他の書式設定オプション
その他の書式設定オプションは既定ではオフです。 **オン**にすると次のようになります。 
- **[タイトル]**: スライサーの上部に (ヘッダーとは別に) タイトルを追加して書式設定します。 
- **[背景]**: スライサー全体に背景色を追加し、透過性を設定します。
- **[縦横比を固定する]**: スライサーのサイズを変更するときに形状を維持します。
- **[罫線]**: スライサーの周囲に 1 ピクセルの枠線を追加し、その色を設定します (このスライサーの枠線は、[全般] の [アウトライン] の設定とは別であり影響を受けません)。 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>他のページでスライサーを同期して使用する
Power BI の 2018 年 2 月更新以降では、スライサーを同期し、レポートの任意のページまたはすべてのページで使用できます。 
1. District Manager スライサーを選択し、Power BI Desktop の [表示] メニューの **[スライサーの同期]** を選択するか、Power BI サービスの **[スライサー ウィンドウの同期]** を選択します。 [スライサーの同期] ウィンドウが表示されます。 
    
    ![スライサーを同期する](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. 最初の列では **[Overview]** とスライサーを同期する他のページを選択するか、**[すべてに追加]** をクリックしてすべてのレポート ページにスライサーを同期します。  
3. 次の列では **[Overview]** とスライサーを表示する他のページを選択します。 
4. **[Overview]** ページに切り替えて、スライサーおよび他のページ ビジュアルへの影響を確認します。 
    - 他の項目を選択および選択解除し、ページの他のビジュアルがそれに応じて変化することを確認します。 任意のページでの項目の選択が、同期されているすべてのページに反映されます。
    - [Overview] ページでスライサーのサイズ、形状、位置、書式を変更します。 他の同期されているページのスライサーの書式は変更されません。 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>スライサーによって影響を受けるページ ビジュアルを制御する
既定では、レポート ページ上のスライサーは、そのページの他のすべての視覚エフェクトに影響します。 一部のページ視覚エフェクトが影響を受けないようにするには、**[ビジュアル対話]** を使用します。

1. **[Overview]** ページでスライサーを選択して次のようにします。
    - Power BI Desktop では、[ビジュアル ツール] の [書式] をクリックして **[相互作用を編集]** を選択します。
    - Power BI サービスでは、メニュー バーの **[ビジュアル対話]** を選択して **[相互作用を編集]** をオンにします。 
    
    フィルター コントロールは、ページの他のビジュアルすべての上に表示されます。 ![フィルター コントロール](media/power-bi-visualization-slicers/filter-controls.png)
    
2. スライサーによるビジュアルのフィルター処理を停止するには、ビジュアルの上にある **[なし]** アイコンを選択します。 スライサーによるビジュアルのフィルター処理を再び開始するには、**[フィルター]** アイコンを選択します。 

相互作用の編集については、「[Power BI レポートでの視覚化の相互作用](service-reports-visual-interactions.md)」をご覧ください。

## <a name="next-steps"></a>次の手順
[試してみる (無料)](https://powerbi.com/)

Power BI を改善する方法について、ご意見がありましたら、 [コメントを送信](https://ideas.powerbi.com/forums/265200-power-bi-ideas)してください。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

[視覚化をレポートに追加する](power-bi-report-add-visualizations-i.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

