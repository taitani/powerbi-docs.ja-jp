---
title: 'データセットから新しいレポートを作成 '
description: データセットから新しい Power BI レポートを作成します。
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 377ea4acc1a6fb41101571ac3ed0be2f3e50889b
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "34246159"
---
# <a name="create-a-new-report-in-power-bi-service-by-importing-a-dataset"></a>データセットをインポートすることで Power BI サービス内で新しいレポートを作成する
[Power BI のレポート](service-reports.md)を読んで、次は自分のレポートを作成しようと思われるでしょう。 レポートを作成するには、さまざまな方法があります。この記事ではまず、Power BI サービスを使用して Excel データセットからごく基本的なレポートを作成します。 レポート作成の基本を理解した後、その下にある「**次の手順**」で、より高度なレポートに関するトピックを示します。  

> **ヒント**: 既存のレポートをコピーしてレポートを作成するには、「[Copy a report](power-bi-report-copy.md)」 (レポートをコピーする) を参照してください。
> 
### <a name="prerequisites"></a>前提条件
- Power BI サービス (Power BI Desktop を使用したレポート作成については、[Desktop のレポート ビュー](desktop-report-view.md)に関するページをご覧ください)  
- 小売りの分析のサンプルのデータセット

## <a name="import-the-dataset"></a>データセットをインポートする
この方法でのレポート作成は、データセットと空白のレポート キャンバスから始まります。 作業を進めるには、[小売の分析のサンプル Excel データセットをダウンロード](http://go.microsoft.com/fwlink/?LinkId=529778)し、OneDrive for Business (推奨) またはローカルに保存します。

1. Power BI サービスのワークスペースでレポートを作成するので、既存のワークスペースを選択するか、新しいワークスペースを作成します。
   
   ![アプリ ワークスペースのリスト](media/service-report-create-new/power-bi-workspaces2.png)
2. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![データの取得](media/service-report-create-new/power-bi-get-data3.png)
3. **[ファイル]** を選択し、小売りの分析のサンプルを保存した場所に移動します。
   
    ![[ファイル] の選択](media/service-report-create-new/power-bi-select-files.png)
4. この演習では、**[インポート]** を選択します。
   
   ![[インポート] の選択](media/service-report-create-new/power-bi-import.png)
5. データセットをインポートしたら、**[データセットの表示]** を選択します。
   
   ![[データセットの表示] の選択](media/service-report-create-new/power-bi-view-dataset.png)
6. データセットを表示すると、実際にはレポート エディターが開きます。  空白のキャンバスとレポート編集ツールが表示されます。
   
   ![レポート エディター](media/service-report-create-new/power-bi-blank-report.png)

> **ヒント**: レポート編集キャンバスに慣れていない場合や、使い方を思い出す必要がある場合は、作業を進める前に[レポート エディターのツアー](service-the-report-editor-take-a-tour.md)を実行してください。
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>レポートに放射状ゲージを追加する
データセットがインポートされたので、質問への回答を始めましょう。  最高マーケティング責任者 (CMO) は、今年の売上目標にどれだけ近づいているかを知りたいと考えています。 ゲージは、このような種類の情報を表示するために[適した視覚化の選択肢](power-bi-report-visualizations.md)です。

1. [フィールド] ウィンドウで、**[Sales (売上)]** > **[This Year Sales (今年の売上)]** > **[値]** を選びます。
   
    ![レポート エディターでの縦棒グラフ](media/service-report-create-new/power-bi-report-step1.png)
2. ゲージのテンプレート ![ゲージ アイコン](media/service-report-create-new/powerbi-gauge-icon.png) を **[視覚化]** ウィンドウから選択して、ビジュアルをゲージに変換します。
   
    ![レポート エディターのゲージ ビジュアル](media/service-report-create-new/power-bi-report-step2.png)
3. **\[Sales] \(売上)** > **\[This Year Sales] \(今年の売上)** > **[目標]** を **[目標値]** にドラッグします。 目標に非常に近づいているようです。
   
    ![ゲージ ビジュアルとターゲット値としての目標](media/service-report-create-new/power-bi-report-step3.png)
4. このあたりで[レポートを保存](service-report-save.md)するとよいでしょう。
   
   ![[ファイル] メニュー](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>面グラフとスライサーをレポートに追加する
CMO に対して、その他いくつかの質問に応える必要があります。 CMO は、昨年と比較して今年の売上がどうであるかを知りたいと考えています。 また、地区ごとの調査結果を見たいと言っています。

1. まず、キャンバスに空き領域を作りましょう。 ゲージを選択し、右上隅に移動します。 次に、四隅のいずれかをつかんでドラッグし、サイズを小さくします。
2. ゲージの選択を解除します。 [フィールド] ウィンドウで、**[Sales (売上)]** > **[This Year Sales (今年の売上)]** > **[値]** を選択し、**[Sales (売上)]** > **[Last Year Sales (昨年の売上)]** を選択します。
   
    ![レポート エディターとゲージと横棒グラフ](media/service-report-create-new/power-bi-report-step4.png)
3. 面グラフのテンプレート ![グラフ アイコン](media/service-report-create-new/power-bi-areachart-icon.png) を **[視覚化]** ウィンドウから選択し、ビジュアルを面グラフに変換します。
4. **[Time (時間)]** > **[Period (期間)]** を選択して、[Period (期間)] を **[軸]** に追加します。
   
    ![面グラフがアクティブなレポート エディター](media/service-report-create-new/power-bi-report-step5.png)
5. 視覚化を期間で並べ替えるには、省略記号を選んで、**[Sort by Period]\(期間別に並べ替え\)** を選びます。
6. 次にスライサーを追加しましょう。 キャンバスの空いている領域を選択して、スライサー ![スライサー アイコン](media/service-report-create-new/power-bi-slicer-icon.png)    テンプレートを選択します。 これにより、キャンバスに空のスライサーが追加されます。
   
    ![レポート キャンバス](media/service-report-create-new/power-bi-report-step6.png)    
7. [フィールド] ウィンドウから **[District (地区)]** > **[District (地区)]** の順に選択します。 スライサーを移動し、サイズを変更します。
   
    ![レポート エディター、District の追加](media/service-report-create-new/power-bi-report-step7.png)  
8. スライサーを使用して地区ごとのパターンや洞察を探します。
   
   ![スライサー使用のビデオ](media/service-report-create-new/power-bi-slicer-video2.gif)  

データの調査と視覚エフェクトの追加を続けます。 特に興味深い分析情報が見つかったら、[ダッシュボードにピン留め](service-dashboard-pin-tile-from-report.md)します。

## <a name="next-steps"></a>次の手順
* [レポートに新しいページを追加する](power-bi-report-add-page.md)  
* [視覚化をダッシュボードにピン留めする](service-dashboard-pin-tile-from-report.md)方法の詳細   
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

