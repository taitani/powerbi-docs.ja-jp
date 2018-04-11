---
title: Power BI で Bing に接続する
description: Power BI 用 Bing
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 263951fa9516b35509220e4621a03567029ca590
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-bing-with-power-bi"></a>Power BI で Bing に接続する
Bing コンテンツ パックを使用すると、任意の用語について、インターネット検索の利用状況に関する分析結果を表示できます。

Power BI 用 [Bing コンテンツ パック](https://app.powerbi.com/groups/me/getdata/services/bing) に接続します。

>[!NOTE]
>Bing タイルは約 5 分ごとに自動更新され、選択可能な唯一のタイルであるニュース タイルには、対応するニュース記事が表示されます。 

>[!NOTE]
>Bing コンテンツ パックから取得されるタイルは、モバイル アプリケーションでは表示されません。 現在、この問題の解決に取り組んでいます。

1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-bing/getdata.png)
2. **[サービス]** ボックスで、 **[取得]**を選択します。
   
    ![](media/service-connect-to-bing/services.png)
3. **[Bing]** > **[取得]** の順に選択します。
   
    ![](media/service-connect-to-bing/bing.png)
4. [パラメーター] ダイアログ ボックスで、追跡する検索用語を入力して、[追加] をクリックします。
   
    ![](media/service-connect-to-bing/params.png)    
5. 左側のダッシュボード一覧に、Bing という名前の新しいエントリと、指定した検索用語が表示されます。 このダッシュボードに関連付けられているデータセットやレポートはありません。 タイルの読み込みにはしばらく時間がかかることがありますが、読み込みが完了すると、下図のようなレイアウトが表示されます。
   
    ![](media/service-connect-to-bing/dashboard.png)

読み込みが完了すると、データの調査を開始できます。このダッシュボードから自身のアカウントの他のダッシュボードに、タイルをピン留めすることもできます。

