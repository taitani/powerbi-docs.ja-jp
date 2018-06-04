---
title: Power BI で Smartsheet に接続する
description: Power BI 用 Smartsheet
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b30e9934c6a1779538aeb5fe82db59e018fdb880
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249461"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Power BI で Smartsheet に接続する
Smartsheet は、コラボレーションとファイル共有に簡単なプラットフォームを提供しています。 Power BI 用 Smartsheet コンテンツ パックは、Smartsheet アカウントの概要を示すデータセット、レポート、ダッシュボードを提供します。 また、[Power BI Desktop](desktop-connect-to-data.md) を使用して、ご使用のアカウントでそれぞれのシートに直接接続することもできます。 

Power BI 用 [Smartsheet コンテンツ パック](https://app.powerbi.com/groups/me/getdata/services/smartsheet)に接続します。

>[!NOTE]
>Smartsheet 管理者アカウントには追加のアクセス権があるため、Power BI コンテンツ パックの接続および読み込みで優先されます。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. **[Smartsheet] \> [取得]** の順に選びます。
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. [認証方法] として **[oAuth2]\>、[サインイン]** の順に選びます。
   
   プロンプトが表示されたら、Smartsheet 資格情報を入力し、認証プロセスに従います。
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Power BI によるデータのインポート後、新しいダッシュ ボード、レポート、データセットが左側のナビゲーション ウィンドウに表示されます。 新しい項目は、黄色のアスタリスク (\*) でマークされます。Smartsheet エントリを選びます。
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="whats-included"></a>含まれるもの
Power BI 用 Smartsheet コンテンツ パックには、ワークスペースの数、所有しているレポートやシート、レポートやシートが変更された日時など、Smartsheet アカウントの概要が含まれています。また、管理者ユーザーは、上位のシート作成者など、システムのユーザーに関する情報も表示することができます。  

使用しているアカウントのそれぞれのシートに直接接続するために、[Power BI Desktop](desktop-connect-to-data.md) の Smartsheet コネクタを使用することができます。  

## <a name="next-steps"></a>次の手順:

[Power BI の概要](service-get-started.md)

[Power BI のデータの取得](service-get-data.md)