---
title: Power BI で Circuit ID に接続する
description: Power BI 用 Circuit ID
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 0cc0125f35dc90a03eeaeed0d5e69c0a5c3115ae
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34241161"
---
# <a name="connect-to-circuit-id-with-power-bi"></a>Power BI で Circuit ID に接続する
Circuit ID からの通信データの分析は、Power BI を使えば簡単に行えます。 Power BI は、データを取得し、そのデータに基づいて既定のダッシュボードと関連レポートを作成します。 接続すると、データの探索や、必要に応じたダッシュボードのカスタマイズを行えます。 データは毎日自動的に更新されます。

Power BI 用 [Circuit ID コンテンツ パック](https://app.powerbi.com/getdata/services/circuitid)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-circuit-id/getdata.png)
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
    ![](media/service-connect-to-circuit-id/services.png)
3. **[Circuit ID]** \> **[接続]** の順に選択します。
   
    ![](media/service-connect-to-circuit-id/circuitid.png)
4. [認証方式] で、[Basic] を選択し、ユーザー名とパスワードを入力します。 続いて、[サインイン] をクリックします。
   
    ![](media/service-connect-to-circuit-id/circuitid_login.png)
5. Power BI によるデータのインポート後、新しいダッシュ ボード、レポート、データセットが左側のナビゲーション ウィンドウに表示されます。 新しい項目には黄色のアスタリスクでマークが付けられます。
   
    ![](media/service-connect-to-circuit-id/circuitid_dashboard_chrome.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI のデータの取得](service-get-data.md)

