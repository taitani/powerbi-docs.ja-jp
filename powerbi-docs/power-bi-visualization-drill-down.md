---
title: "Power BI での視覚化のドリルダウン"
description: "このドキュメントでは、Microsoft Power BI サービスと Power BI Desktop での視覚化のドリルダウンの方法を示します。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/18/2017
ms.author: mihart
ms.openlocfilehash: 83c63ee2bed5ae7674223cf2fc3f9241308926e9
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Power BI での視覚化のドリルダウン
## <a name="drill-down-requires-a-hierarchy"></a>ドリルダウンには階層が必要
ビジュアルに階層がある場合は、ドリルダウンしてさらに詳細な情報を表示できます。 たとえば、分野、競技、種目で構成された階層でオリンピック メダル数を表示する視覚化があるものとします。 既定では、視覚化には分野 (体操、スキー、水泳など) 別にメダル数が表示されます。しかし、この視覚化は階層構造になっているので、いずれかのビジュアル要素 (棒、線、バブルなど) を選ぶと、さらに詳細な図が表示されます。 **水泳**要素を選ぶと、競泳、飛び込み、水球のデータが表示されます。  **飛び込み**要素を選ぶと、飛び板飛び込み、高飛び込み、シンクロナイズド ダイビングの各種目に関する詳細が表示されます。

階層を追加できるのは自分が所有するレポートだけであり、他のユーザーから共有されているレポートには追加できません。
どの視覚化に階層が含まれるかわからない場合は、  視覚化をポイントして、次のようなドリル コントロールが上部の隅に表示される場合、その視覚化には階層があります。

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

日付は、他とは違う種類の階層です。 視覚化に日付フィールドを追加すると、年、四半期、月、日を含む時間階層が自動的に追加されます。 詳しくは、「[ビジュアルの階層とドリルダウンの動作](guided-learning/visualizations.yml#step-18)」または次のビデオをご覧ください。

  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Power BI Desktop を使用して階層を作成する方法についての説明は、[階層を作成および追加する方法](https://youtu.be/q8WDUAiTGeU)のビデオをご覧ください。
> 
> 

## <a name="two-methods-to-drill-down"></a>ドリルダウンの 2 つの方法
視覚化のドリルダウン (およびドリルアップ) には、2 つの異なる方法があります。  この記事では、両方について説明します。 どちらの方法でも同じことが実現されるので、お好きな方法を使用してください。

> [!NOTE]
> 先に進む前に、Power BI サービスで [Retail Analysis サンプル](sample-datasets.md)を開き、**Territory**、**City**、**PostalCode**、**Name** (グループ) 別に **Total Units This Year** (値) を表示するツリーマップを作成してください。  
> 
> 

## <a name="method-1-for-drill-down"></a>ドリルダウンの 1 つ目の方法
この方法では、視覚化自体の上部の隅に表示されるドリル アイコンを使います。

1. Power BI の[読み取りビュー](service-report-open-in-reading-view.md)または[編集ビュー](service-reading-view-and-editing-view.md)でレポートを開きます。 階層のある視覚化でなければドリルダウンできません。 
   
   階層は次のアニメーションのように表示されます。  この視覚化には、地域、都市、郵便番号、および都市名で構成された階層があります。 各地域には 1 つ以上の都市があり、各都市には 1 つ以上の郵便番号があります。リストの先頭が *Territory* なので、既定では、視覚化には地域のデータのみが表示されます。
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. ドリルダウンを有効にするには、視覚化の右上隅にある矢印アイコンを選択します。 ドリルダウンが有効になると、アイコンが暗転します。 ドリルダウンが有効になっていない場合にビジュアル要素 (棒グラフやバブル チャート) を選ぶと、レポート ページの他のグラフがクロス フィルター処理されます。    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. ***一度に 1 つのフィールド*** をドリルダウンするには、視覚化の要素の 1 つをクリックします。これは、横棒グラフでは横棒の 1 つをクリックすることであり、ツリーマップでは *葉* の 1 つをクリックすることです。 階層を上下に移動するとタイトルが変わることに注意してください。 このアニメーションでは、"Total Units This Year by Territory"、"Total Units This Year by Territory and City"、"Total Units This Year by Territory, City and PostalCode"、"Total Units This Year by Territory, City, PostalCode, and Name" の順に移動しています。 そして、ドリルダウン後に上位に戻るには、次に示すように、視覚化の左上隅にある **[ドリルアップ]** アイコン ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) を選びます。
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. ***すべてのフィールドを一度に***ドリルダウンするには、視覚化の左上隅にある二重矢印を選びます。
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. ドリルダウン後に上位に戻るには、視覚化の左上隅にある上向き矢印を選択します。
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-2-for-drill-down"></a>ドリルダウンの 2 つ目の方法
この方法では、Power BI の上部にあるメニュー バーの **[探索]** ドロップダウンを使います。

1. Power BI の[読み取りビュー](service-report-open-in-reading-view.md)または[編集ビュー](service-reading-view-and-editing-view.md)でレポートを開きます。 階層のある視覚化でなければドリルダウンできません。 
   
   階層は次の図のように表示されます。  この視覚化には、地域、都市、郵便番号、および都市名で構成された階層があります。 各地域には 1 つ以上の都市があり、各都市には 1 つ以上の郵便番号があります。リストの先頭が *Territory* なので、既定では、視覚化には地域のデータのみが表示されます。
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. ドリルダウンを有効にするには、視覚化を選んでアクティブにし、Power BI 上部のメニュー バーから **[探索]** > **[ドリルダウン]** の順に選びます。 視覚化の右上隅にあるドリルダウン アイコンの背景が黒に変わります。 ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. 有効にした後は、ツリーマップの葉の 1 つを選んで、一度に 1 フィールドだけドリルダウンします。 この例では、**NC** という名前の地域を選び、ノースカロライナ州の本年度の販売総数を都市別に表示します。
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. すべてのフィールドを一度にドリルダウンするには、**[探索]** > **[次のレベルを表示する]** の順に選びます。
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. ドリルアップして戻るには、**[探索]** > **[ドリルアップ]** を選びます。
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)
6. ビジュアルを作成するために使用されているデータを表示するには、**[データを参照]** を選択します。 データは、ビジュアルの下のウィンドウに表示されます。 このウィンドウは、ビジュアルのドリルスルーの実行中に残ります。 詳しくは、「[ビジュアルの作成に使用するデータを確認する](service-reports-show-data.md)」をご覧ください。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
* 視覚化に日付フィールドを追加しても階層が作成されない場合は、"日付" フィールドが実際には日付として保存されていない可能性があります。 データセットを所有している場合は、Power BI Desktop で *[データ]* ビューを開き、日付を含む列を選んだ後、[モデリング] タブで **[データ型]** を **[日付]** または **[日付/時刻]** に変更します。 他のユーザーからレポートを共有されている場合は、所有者に連絡して変更を頼みます。  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>次の手順
[Power BI レポートでの視覚化](power-bi-report-visualizations.md)

[Power BI レポート](service-reports.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

