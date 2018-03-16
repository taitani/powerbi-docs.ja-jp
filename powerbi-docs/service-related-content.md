---
title: "Power BI サービスで関連するコンテンツを表示する"
description: "ナビゲーションが容易になり、ダッシュボード、レポート、データセットの関連するコンテンツを表示できます"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 43dffab862173779068f1180f83bc6c92bf98013
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2018
---
# <a name="view-related-content-in-power-bi-service"></a>Power BI サービスで関連するコンテンツを表示する
**[関連するコンテンツ]** ペインには、Power BI サービスのコンテンツ (ダッシュボード、レポート、データセット) がどのように相互接続されているかが示されます。  さらに、このペインからは、更新、名前の変更、詳細情報の生成など、一般的なタスクを実行できます。 関連するレポートやダッシュボードを選ぶと、Power BI ワークスペースに表示されます。   

既にお気づきのように、レポートはデータセットを基にして作成されており、レポートの視覚化はダッシュボードにピン留めされ、ダッシュボードのビジュアルはレポートにリンクしています。 しかし、マーケティング レポートの視覚化をホストしているダッシュボードをどのようにして知りますか。 そのダッシュボードをどのようにして見つけますか。 調達ダッシュボードでは複数のデータセットからの視覚化が使われていますか。 その場合、どのような名前が付けられていて、開いて編集するにはどうすればよいですか。 HR データセットはレポートやダッシュボードで使われていますか、またはリンクを壊さずに移動できますか。 このような疑問の答えは、**[関連するコンテンツ]** ペインでわかります。  このペインでは、関連するコンテンツが表示されるだけでなく、コンテンツに対する操作を実行し、関連するコンテンツ間を簡単に移動することもできます。

![関連コンテンツ](media/service-related-content/power-bi-view-related-dashboard-new.png)

> [!NOTE]
> 関連するコンテンツの機能は、ストリーミング データセットには機能しません。
> 
> 

## <a name="view-related-content-for-a-dashboard"></a>ダッシュボードの関連するコンテンツを表示する
Watch ではダッシュボードの関連するコンテンツが表示されます。 その後、ビデオで説明されている手順に従って、ご自分でやってみてください。データセットは、調達の分析のサンプルをご利用ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M#t=3m05s" frameborder="0" allowfullscreen></iframe>


**[関連するコンテンツ]** ペインを開くには、ダッシュボードに対する "*表示*" アクセス許可が少なくとも必要です。 この例では、[調達の分析のサンプル](sample-procurement.md)を使います。

**方法 1**

ワークスペースで **[ダッシュボード]** タブを選び、**[関連の表示]** アイコン ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-icon-new.png) を選びます。

![[ダッシュボード] タブ](media/service-related-content/power-bi-view-related-dash-newer.png)

<br>

**方法 2**

ダッシュボードを開き、上部のメニュー バーから   ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-new.png) を選択します。

**[関連するコンテンツ]** ペインが開きます。 ダッシュボードに視覚化がピン留めされているすべてのレポートと、それに関連付けられているデータセットが表示されます。 この例のダッシュボードには 3 つの異なるレポートからピン留めされた視覚化があり、これらのレポートは 3 つの異なるデータセットが基になっています。

![[関連するコンテンツ] ウィンドウ](media/service-related-content/power-bi-view-related-dashboard-new.png)

ここからは、関連するコンテンツに対する操作を直接実行できます。  たとえば、レポート名を選んで開きます。  表示されたレポートで、[Excel で分析](service-analyze-in-excel.md)、[名前の変更](service-rename.md)、[詳細情報の取得](service-insights.md)などのアイコンを選びます。 データセットで、[レポートの新規作成](service-report-create-new.md)、[更新](refresh-data.md)、名前の変更、[Excel で分析](service-analyze-in-excel.md)、[詳細情報の取得](service-insights.md)、データセットの **[設定]** ウィンドウの表示などのアイコンを選びます。  

## <a name="view-related-content-for-a-report"></a>レポートの関連するコンテンツを表示する
**[関連するコンテンツ]** ペインを開くには、レポートに対する "*表示*" アクセス許可が少なくとも必要です。 この例では、[調達の分析のサンプル](sample-procurement.md)を使います。

**方法 1**

ワークスペースで **[レポート]** タブを選び、**[関連の表示]** アイコン ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-icon-new.png) を選びます。

![[レポート] タブ](media/service-related-content/power-bi-view-related-report-newer.png)

<br>

**方法 2**

[[読み取りビュー]](service-reading-view-and-editing-view.md) でレポートを開き、上部のメニュー バーから ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-new.png) を選択します。

**[関連するコンテンツ]** ペインが開きます。 関連付けられたデータセットと、レポートから少なくとも 1 つのタイルがピン留めされているすべてのダッシュボードが表示されます。 この例のレポートには、2 つの異なるダッシュボードにピン留めされた視覚化があります。

![[関連するコンテンツ] ウィンドウ](media/service-related-content/power-bi-view-related-report.png)

ここからは、関連するコンテンツに対する操作を直接実行できます。  たとえば、ダッシュボード名を選んで開きます。  一覧のダッシュボードで、[ダッシュボードを他のユーザーと共有する](service-share-dashboards.md)アイコンや、ダッシュボードの **[設定]** ウィンドウを開くアイコンを選びます。 データセットで、[レポートの新規作成](service-report-create-new.md)、[更新](refresh-data.md)、名前の変更、[Excel で分析](service-analyze-in-excel.md)、[詳細情報の取得](service-insights.md)、データセットの **[設定]** ウィンドウの表示などのアイコンを選びます。  

## <a name="view-related-content-for-a-dataset"></a>データセットの関連するコンテンツを表示する
**[関連するコンテンツ]** ペインを開くには、データセットに対する "*表示*" アクセス許可が少なくとも必要です。 この例では、[調達の分析のサンプル](sample-procurement.md)を使います。

ワークスペースで **[データセット]** タブを選び、**[関連の表示]** アイコン ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-icon-new.png) を探します。

![データセット タブ](media/service-related-content/power-bi-view-related-dataset-newer.png)

アイコンを選び、**[関連するコンテンツ]** ペインを開きます。

![](media/service-related-content/power-bi-datasets.png)

ここからは、関連するコンテンツに対する操作を直接実行できます。  たとえば、ダッシュボード名またはレポート名を選んで開きます。  一覧のダッシュボードで、[ダッシュボードを他のユーザーと共有する](service-share-dashboards.md)アイコンや、ダッシュボードの **[設定]** ウィンドウを開くアイコンを選びます。 レポートで、[Excel での分析](service-analyze-in-excel.md)、[名前の変更](service-rename.md)、[詳細情報の取得](service-insights.md)などのアイコンを選びます。  

## <a name="limitations-and-troubleshooting"></a>制限事項とトラブルシューティング
* ブラウザーに十分なスペースがない場合、**[関連の表示]** のオプションは表示されませんが、[関連の表示] アイコン ![[関連の表示] アイコン](media/service-related-content/power-bi-view-related-icon-new.png) は表示されます。 アイコンを選び、**[関連するコンテンツ]** ペインを開きます。
* レポートの関連するコンテンツを開くには、[[読み取りビュー]](service-reading-view-and-editing-view.md) を表示している必要があります。
* 関連するコンテンツは、Power BI Desktop では使用できません。
* 関連するコンテンツの機能は、ストリーミング データセットには機能しません。

## <a name="next-steps"></a>次の手順
* [Power BI サービスの概要](service-get-started.md)
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

