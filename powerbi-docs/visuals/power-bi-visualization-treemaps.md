---
title: Power BI のツリーマップ
description: Power BI のツリーマップ
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: dd7360761cc78aed9b01eb99165de9f0b4b91ffe
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274768"
---
# <a name="treemaps-in-power-bi"></a>Power BI のツリーマップ
ツリーマップでは、入れ子になった一連の四角形で階層データが表示されます。  階層の各レベルは、色付きの四角形 (「ブランチ (枝)」) で表され、ブランチには他の四角形 (「リーフ (葉)」) が含まれます。  各四角形内の面積は、測定される値に基づいて割り当てられます。 各四角形は大きさの順に左上 (最大) から右下 (最小) に向かって配置されます。

![](media/power-bi-visualization-treemaps/pbi-nancy_viz_treemap.png)

たとえば、売上を分析する場合、最上位レベルの四角形 (*ブランチ* ともいう) を次の衣料カテゴリにすることができます:**Urban (都市部向け)**、**Rural (地方向け)**、**Youth (若者向け)**、**Mix (組み合わせ)**。  カテゴリの四角形は、そのカテゴリ内の衣料メーカー用のより小さい四角形 (*リーフ*ともいう) に分割されます。 また、これらのより小さい四角形は売上数に基づいてサイズが決まり、網掛け表示されます。  

上の **Urban** ブランチでは、`Maximus` の衣料の売上が多く、`Natura` と `Fama` の売上はそれよりも少なく、`Leo` の売上は非常に少なくなっています。  そのため、このツリーマップの **Urban** ブランチは次のようになります。
* 左上隅にある `Maximus` の四角形が最も大きい
* `Natura` と `Fama` の四角形はそれよりもやや小さい
* 他のすべての衣料売上に関する多くの四角形がある 
* `Leo` の四角形は非常に小さい。  

また、各リーフ ノードのサイズと網掛けの比較によって、その他の衣料カテゴリ全体の売上品目数を比較することができます。つまり、四角形が大きく網掛けが濃いほど、値は大きいことになります。

## <a name="when-to-use-a-treemap"></a>ツリーマップを使用すべきケース
ツリーマップは、次のような場合に最適な選択肢です。

* 大量の階層データを表示する場合。
* 横棒グラフで多数の値を効果的に処理できない場合。
* 各部分と全体の間の割合を示す場合。
* 階層内のカテゴリの各レベルにわたってメジャーの分布のパターンを示す場合
* サイズと色分けを使用して属性を示す場合。
* パターン、外れ値、最も重要な要因、および例外を見分ける場合。

### <a name="prerequisites"></a>前提条件
 - Power BI サービスまたは Power BI Desktop
 - 小売りの分析のサンプル

## <a name="create-a-basic-treemap"></a>基本的なツリーマップの作成
ツリーマップの作成例を見たい方は、  このビデオの 2:10 にスキップし、Amanda がツリーマップを作成するところをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

または、独自のツリーマップを作成します。 次の手順では、「Retail Analysis Sample」を使用します。 先に進むには、Power BI サービスにサインインして、**[データの取得] \> [サンプル] \> [小売りの分析のサンプル] \> [接続] \> [ダッシュボードに移動]** の順に選択します。 レポートで視覚エフェクトを作成するには、データセットとレポートの編集アクセス許可が必要です。 Power BI のサンプルは編集できます。 しかし、他のユーザーと共有しているレポートに視覚エフェクトを追加することはできません。  

1. [Total stores]\(総店舗数\) タイルを選んで、小売りの分析のサンプル レポートを開きます。    
2. [[編集ビュー]](../service-interact-with-a-report-in-editing-view.md) を開いて、**[売上高]** > **[Last Years Sales]\(前年の売上高\)** メジャーを選びます。   
   ![](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)   
3. グラフをツリーマップに変換します。  
   ![](media/power-bi-visualization-treemaps/treemapconvertto_new.png)   
4. **[アイテム]** > **[カテゴリ]** を **[グループ]** にドラッグします。 四角形のサイズが総売上高に基づき、色でカテゴリが表されるツリーマップが Power BI によって作成されます。  つまり、カテゴリ別の総売上高の相対的な大きさを視覚的に説明する階層が作成されます。  **[Mens]\(男性向け\)** カテゴリの売上高が最高で、**[Hosiery]\(靴下・下着類\)** カテゴリの売上高が最低です。   
   ![](media/power-bi-visualization-treemaps/power-bi-complete.png)   
5. **[ストア]** > **\[Chain] \(チェーン)** を **"Details"** にドラッグしてツリーマップを完成させます。 これで、前年の売上高をカテゴリおよびチェーン別に比較できます。   
   ![](media/power-bi-visualization-treemaps/power-bi-details.png)
   
   > [!NOTE]
   > [色の彩度] と [詳細] を同時に使用することはできません。
   > 
   > 
5. **[Chain]** (チェーン) エリアにポインターを合わせると、 **[カテゴリ]** のその部分のヒントが表示されます。  たとえば、**[090-Home]** の四角形内の **[Fashions Direct]** にポインターを合わせると、Home カテゴリの Fashion Direct の部分のツールヒントが表示されます。  
   ![](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)
6. [ツリーマップをダッシュボード タイルとして追加 (ビジュアルをピン留め)](../service-dashboard-tiles.md) します。 
7. [レポートを保存](../service-report-save.md)します。

## <a name="highlighting-and-cross-filtering"></a>強調表示とクロス フィルター処理
[フィルター] ウィンドウの使用方法については、「[Power BI でのレポートへのフィルターの追加](../power-bi-report-add-filter.md)」をご覧ください。

ツリーマップ内の [カテゴリ] または [詳細] を強調表示すると、レポート ページ上の他の視覚エフェクトがクロス強調表示またはクロスフィルター処理されます。逆の場合も同様です。 先に進むには、このレポート ページにいくつかのビジュアルを追加するか、このレポートの他の空白以外のページのいずれかにツリーマップをコピーします。

1. ツリーマップ上で、カテゴリまたはカテゴリ内のチェーンのいずれかを選択します。  これにより、ページ上の他の視覚化がクロス強調表示されます。 たとえば、 **[050-Shoes]** を選択すると、前年の靴の売上高が 3,640,471 ドルで、その内 [Fashions Direct] から得られた売上高は 2,174,185 ドルであったことが表示されます。  
   ![](media/power-bi-visualization-treemaps/treemaphiliting.png)

2. **[Last Year Sales by Chain]\(チェーン別の前年売上高\)** 円グラフで、**[Fashions Direct]** スライスを選択し、ツリーマップをクロス フィルター処理します。  
   ![](media/power-bi-visualization-treemaps/treemapnoowl.gif)    

3. グラフ相互間のクロスフィルター処理とクロス強調表示を管理するには、「[Power BI レポートでの視覚エフェクトの相互作用](../service-reports-visual-interactions.md)」を参照してください。

## <a name="next-steps"></a>次の手順

[Power BI のウォーターフォール図](power-bi-visualization-waterfall-charts.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)