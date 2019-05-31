---
title: データセットからレポートを作成する
description: データセットから Power BI レポートを作成します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 6b69c2b1fa811d395a26403de852c44af33491c7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770237"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>データセットをインポートすることで、Power BI サービスでレポートを作成します。
[Power BI のレポート](consumer/end-user-reports.md)を読んで、次は自分のレポートを作成しようと思われるでしょう。 レポートを作成するさまざまな方法はあります。 この記事で、Excel データセットから Power BI サービスで基本的なレポートの作成から始めます。 レポートの作成の基本を理解するとチェック アウト、[次のステップ](#next-steps)詳細については、最後に詳細レポートに関するトピック。  

## <a name="prerequisites"></a>前提条件
- [Power BI サービスにサインアップ](service-self-service-signup-for-power-bi.md)します。 Power BI Desktop を使用してレポートを作成するには、次を参照してください。 [Desktop のレポート ビュー](desktop-report-view.md)します。 
- [小売りの分析のサンプル Excel データセットをダウンロード](http://go.microsoft.com/fwlink/?LinkId=529778)またはローカルでの OneDrive for Business に保存します。

## <a name="import-the-dataset"></a>データセットをインポートする
この方法でのレポート作成は、データセットと空白のレポート キャンバスから始まります。 小売りの分析のサンプル Excel データセット内に沿ったをフォローできます。

1. いますします、Power BI サービス ワークスペースにレポートを作成、ため既存のワークスペースを選択したり、1 つ作成します。
   
   ![アプリ ワークスペースのリスト](media/service-report-create-new/power-bi-workspaces2.png)
2. 左側のナビゲーション ウィンドウの下部にある、次のように選択します。**データを取得する**します。
   
   ![データを取得](media/service-report-create-new/power-bi-get-data3.png)
3. **[ファイル]** を選択し、小売りの分析のサンプルを保存した場所に移動します。
   
    ![[ファイル] の選択](media/service-report-create-new/power-bi-select-files.png)
4. この演習では、 **[インポート]** を選択します。
   
   ![[インポート] の選択](media/service-report-create-new/power-bi-import.png)
5. データセットをインポートしたら、 **[データセットの表示]** を選択します。
   
   ![[データセットの表示] の選択](media/service-report-create-new/power-bi-view-dataset.png)
6. データセットを表示すると、実際にはレポート エディターが開きます。  空白のキャンバスとレポート編集ツールが表示されます。
   
   ![レポート エディター](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> レポート編集キャンバスに詳しくない場合は、復習[レポート エディターのツアー](service-the-report-editor-take-a-tour.md)続行する前にします >。 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>レポートに放射状ゲージを追加する
データセットがインポートされたので、質問への回答を始めましょう。  最高マーケティング責任者 (CMO) は、今年の売上目標にどれだけ近づいているかを知りたいと考えています。 ゲージは、このような種類の情報を表示するために[適した視覚化の選択肢](visuals/power-bi-report-visualizations.md)です。

1. [フィールド] ウィンドウで、 **[Sales (売上)]**  >  **[This Year Sales (今年の売上)]**  >  **[値]** を選びます。
   
    ![レポート エディターでの縦棒グラフ](media/service-report-create-new/power-bi-report-step1.png)
2. ゲージのテンプレート ![ゲージ アイコン](media/service-report-create-new/powerbi-gauge-icon.png) を **[視覚化]** ウィンドウから選択して、ビジュアルをゲージに変換します。
   
    ![レポート エディターのゲージ ビジュアル](media/service-report-create-new/power-bi-report-step2.png)
3. **\[Sales] \(売上)**  >  **\[This Year Sales] \(今年の売上)**  >  **[目標]** を **[目標値]** にドラッグします。 目標に非常に近づいているようです。
   
    ![ゲージ ビジュアルとターゲット値としての目標](media/service-report-create-new/power-bi-report-step3.png)
4. 良いレポートを保存するようになりましたでしょう。
   
   ![[ファイル] メニュー](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>面グラフとスライサーをレポートに追加する
CMO に対して、その他いくつかの質問に応える必要があります。 CMO は、昨年と比較して今年の売上がどうであるかを知りたいと考えています。 また、地区ごとの調査結果を見たいと言っています。

1. まず、キャンバスに空き領域を作りましょう。 ゲージを選択し、右上隅に移動します。 次に、四隅のいずれかをつかんでドラッグし、サイズを小さくします。
2. ゲージの選択を解除します。 [フィールド] ウィンドウで、 **[Sales (売上)]**  >  **[This Year Sales (今年の売上)]**  >  **[値]** を選択し、 **[Sales (売上)]**  >  **[Last Year Sales (昨年の売上)]** を選択します。
   
    ![レポート エディターとゲージと横棒グラフ](media/service-report-create-new/power-bi-report-step4.png)
3. 面グラフのテンプレート ![グラフ アイコン](media/service-report-create-new/power-bi-areachart-icon.png) を **[視覚化]** ウィンドウから選択し、ビジュアルを面グラフに変換します。
4. **[Time (時間)]**  >  **[Period (期間)]** を選択して、[Period (期間)] を **[軸]** に追加します。
   
    ![面グラフがアクティブなレポート エディター](media/service-report-create-new/power-bi-report-step5.png)
5. 視覚化を期間で並べ替えるには、省略記号を選んで、 **[Sort by Period]\(期間別に並べ替え\)** を選びます。
6. 次にスライサーを追加しましょう。 キャンバスの空いている領域を選択して、スライサー ![スライサー アイコン](media/service-report-create-new/power-bi-slicer-icon.png) テンプレートを選択します。 キャンバスに空のスライサーがあるようになりました。
   
    ![レポート キャンバス](media/service-report-create-new/power-bi-report-step6.png)    
7. [フィールド] ウィンドウから **[District (地区)]**  >  **[District (地区)]** の順に選択します。 スライサーを移動し、サイズを変更します。
   
    ![レポート エディター、District の追加](media/service-report-create-new/power-bi-report-step7.png)  
8. スライサーを使用して地区ごとのパターンや洞察を探します。
   
   ![スライサー使用のビデオ](media/service-report-create-new/power-bi-slicer-video2.gif)  

データの調査と視覚エフェクトの追加を続けます。 特に興味深い分析情報が見つかったら、[ダッシュボードにピン留め](service-dashboard-pin-tile-from-report.md)します。

## <a name="next-steps"></a>次の手順

* [視覚化をダッシュボードにピン留めする](service-dashboard-pin-tile-from-report.md)方法の詳細   
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

