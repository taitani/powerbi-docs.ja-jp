---
title: Power BI で Microsoft Azure エンタープライズに接続する
description: Power BI 用 Microsoft Azure エンタープライズ
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
ms.openlocfilehash: 60bcad86af5fcaa09d6b2fb16b581ec7c37264ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Power BI で Microsoft Azure エンタープライズに接続する
Power BI コンテンツ パックを使用すると Power BI で Microsoft Azure Enterprise のデータを調べて監視できます。 データは、1 日 1 回自動的に更新されることになります。

Power BI 用 [Microsoft Azure Enterprise コンテンツ パック](https://app.powerbi.com/getdata/services/azure-enterprise)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. **[Microsoft Azure Enterprise]** \> **[取得]** の順に選択します。
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Azure 環境の URL、インポートするデータの月数、Azure Enterprise 登録番号を指定します。 Azure 環境の URL は `https://ea.azure.com` または `https://ea.windowsazure.cn` です。 [これらのパラメーターの見つけ方](#FindingParams)について詳しくは、後述します。
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. 接続するためのアクセス キーを指定します。 登録のキーは、Azure EA ポータルでわかります。
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. インポート処理が自動的に開始されます。 完了すると、ナビゲーション ウィンドウに、新しいダッシュ ボード、レポート、モデルが表示されます。 インポートされたデータを表示するダッシュボードを選択します。
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="whats-included"></a>含まれるもの
Azure Enterprise コンテンツ パックには、接続フローで指定した月の範囲の月単位のレポート データが含まれています。 この範囲の期間は移動するので、データセットが更新されると、含まれる日付も更新されます。

## <a name="system-requirements"></a>システム要件
コンテンツ パックは、Azure Portal 内のエンタープライズ機能にアクセスする必要があります。

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>パラメーターの見つけ方
課金情報を見ることができる EA の直接のお客様、パートナー、間接のお客様は、Power BI レポートを利用できます。 接続フローで期待される各値の詳細については以下を参照してください。

**Azure 環境の URL**

* この値は通常 https://ea.azure.com ですが、サインインした後で URL を調べて確認できます。
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**月数**

* これは、インポートするデータの (当日からの) 月数を表す 1 ～ 36 の値です。

**登録番号**

* これは、Azure Enterprise の登録番号です。この番号は [Azure Enterprise Portal](https://ea.azure.com/) のホーム画面の \[Enrollment Detail] \(登録の詳細) で確認できます。
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**アクセス キー**

* キーは、Azure Enterprise ポータルの [利用状況のダウンロード] の [API アクセス キー] でわかります。
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**追加のヘルプ**

* Azure Enterprise Power BI パックを設定する追加のヘルプを表示するには、Azure Enterprise Portal にログインし、[ヘルプ] で API ヘルプ ファイルを表示し、[レポート]-> [利用状況のダウンロード]-> [API アクセス キー] と選択して詳細な説明を参照します。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI でデータを取得する](service-get-data.md)

