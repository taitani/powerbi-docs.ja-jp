---
title: Power BI で Microsoft Azure Consumption Insights に接続する
description: Power BI 用 Microsoft Azure Consumption Insights
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222122"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Power BI で Microsoft Azure Consumption Insights に接続する
Power BI コンテンツ パックを使用すると Power BI で Microsoft Azure の消費データを調べて監視できます。 データでは、1 日に 1 回自動的に更新します。

[Power BI 用 Microsoft Azure Consumption Insights コンテンツ パック](https://app.powerbi.com/getdata/services/azureconsumption)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. 選択**Microsoft Azure Consumption Insights** \> **今すぐ入手**します。 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. インポートするデータの月数と Azure Enterprise 登録番号を指定します。 [これらのパラメーターの見つけ方](#FindingParams)について詳しくは、後述します。
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. 接続するためのアクセス キーを指定します。 Azure EA ポータルで、登録キーが表示されます。 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. インポート処理が自動的に開始します。 完了すると、新しいダッシュ ボード、レポート、およびモデルがナビゲーション ウィンドウに表示されます。 インポートされたデータを表示するダッシュボードを選択します。
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](consumer/end-user-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](consumer/end-user-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新がスケジュールされて、中には、更新スケジュールを変更またはを使用してオンデマンドでこれを更新してみてください**今すぐ更新**

## <a name="whats-included"></a>含まれるもの
Microsoft Azure Consumption Insights コンテンツ パックには、月単位の接続時に指定した月の範囲のデータのレポートが含まれています。 範囲は、更新、データセットに含まれる日付が更新されるように、移動ウィンドウ、です。

## <a name="system-requirements"></a>システム要件
コンテンツ パックには、Azure portal 内の Enterprise 機能へのアクセスが必要です。 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>パラメーターの見つけ方
Power BI レポートを EA ダイレクト、パートナー、および間接のお客様の課金情報を表示できます。 接続のフローの各値を見つける方法の詳細は以下を参照が必要です。

**月数**

* インポートするには今日のデータの月数 (1 ~ 36) の数。

**登録番号**

* 参照して、Azure Enterprise 登録番号、 [Azure Enterprise Portal](https://ea.azure.com/)の下のホーム画面**登録の詳細**します。
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**アクセス キー**

* Azure Enterprise portal の アクセス キーを検索できます**使用量のダウンロード** > **API アクセス キー**します。
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**追加のヘルプ**

* Azure Enterprise Power BI パックを追加のヘルプの設定には、Azure Enterprise Portal にサインインし、API のヘルプ ファイルを表示**ヘルプ**します。 追加」の手順を検索することもできます。**レポート** -> **使用量のダウンロード** -> **API アクセス キー**します。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI でデータを取得する](service-get-data.md)

