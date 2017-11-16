---
title: "レポートから Power BI ダッシュボードを作成する"
description: "レポートから Power BI ダッシュボードを作成する"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: dac5628756898a20fe139447bc2d165ba804320c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>レポートから Power BI ダッシュボードを作成する
[Power BI のダッシュボード](service-dashboards.md)を読んで、次は自分のダッシュボードを作成しようと思われるでしょう。 ダッシュボードを作成するには、レポートから、何もない状態から、データセットから、既存のダッシュボードを複製して、それ以外の方法など、さまざまな方法があります。  このトピックとビデオでは、既存のレポートから視覚化をピン留めして新しいダッシュボードを作成する方法を示します。

> **注**: ダッシュボードは、Power BI Desktop ではなく、Power BI サービスの機能です。 Power BI モバイルでは、ダッシュボードを作成することはできませんが、[表示して共有する](mobile-apps-view-dashboard.md)ことはできます。
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>ビデオ: レポートからビジュアルとイメージをピン留めすることでダッシュボードを作成する
レポートからの視覚化をピン留めして、新しいダッシュボードを作成する手順をご覧ください。 その後、後述する手順に従い、調達の分析のサンプルを使って、自分で試してみてください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>レポートでデータセットをインポートする
Power BI サンプル データセットの 1 つをインポートし、それを使って新しいダッシュボードを作成します。 ここで使うサンプルは、2 つの PowerView を含む Excel ブックです。 Power BI は、ブックをインポートすると、データセットとレポートをワークスペースに追加します。  レポートは、PowerView シートから自動的に作成されます。

1. [このリンクを選択](http://go.microsoft.com/fwlink/?LinkId=529784)して、調達の分析のサンプルの Excel ファイルをダウンロードし、保存してください。 OneDrive for Business に保存することをお勧めします。
2. ブラウザーで Power BI サービスを開きます (app.powerbi.com)。
3. 既存のワークスペースを選択するか、新しいアプリ ワークスペースを作成します。
4. 左のナビゲーションから **[データの取得]** を選択します。
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. **[ファイル]**を選択します。
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. 調達の分析のサンプルの Excel ファイルを保存した場所に移動します。 ファイルを選び、**[接続]** を選択します。
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. この演習では、**[インポート]** を選択します。
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. 成功メッセージが表示されたら、**[x]** を選択して閉じます。
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>レポートを開いてダッシュボードにタイルをピン留めする
1. 同じワークスペースにとどまった状態で、**[レポート]** タブを選択します。新しくインポートしたレポートが、黄色のアスタリスク付きで表示されます。 レポート名を選択してレポートを開きます。
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. [読み取りビュー](service-interact-with-a-report-in-reading-view.md)でレポートが開きます。 下部に 2 つのタブがあります。割引分析と支出概要です。 各タブはレポートのページを表します。
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. 視覚化をポイントして、使用可能なオプションを表示します。 ダッシュボードに視覚化を追加するには、ピン ![](media/service-dashboard-create/power-bi-pin-icon.png) アイコンを選択します。
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. ここでは新しいダッシュボードを作成しているので、**[新しいダッシュボード]** オプションを選択して名前を指定します。 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. **[ピン留め]** を選択すると、現在のワークスペースに新しいダッシュボードが作成されます。 **[ダッシュボードにピン留めしました]** というメッセージが表示されたら、**[ダッシュボードへ移動]** を選択します。 レポートの保存を求めるメッセージが表示されたら、**[保存]** を選択します。
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. 新しいダッシュボードが開き、1 つのタイル (ピン留めしたばかりの視覚化) が表示されます。 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. レポートに戻るには、タイルを選びます。 新しいダッシュボードにさらにいくつかタイルをピン留めします。 今度は、**[ダッシュボードにピン留めする]** ウィンドウが表示されたら、**[既存のダッシュボード]** を選択します。  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

これで初めてのダッシュボードを作成できました。 作成したダッシュボードでは、さらに多くの処理を行うことができます。  下に示した**次のステップ**のいずれかを試すか、自由に遊んだり調べたりしてみてください。   

## <a name="next-steps"></a>次の手順
* [タイルのサイズを変更したり、移動したりする](service-dashboard-edit-tile.md)
* [ダッシュボードのタイルの概要](service-dashboard-tiles.md)
* [アプリを作成することによってダッシュボードを共有する](service-create-distribute-apps.md)
* [Power BI - 基本的な概念](service-basic-concepts.md)
* [Power BI のダッシュボード](service-dashboards.md)
* [優れたダッシュボードのデザインに関するヒント](service-dashboards-design-tips.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

