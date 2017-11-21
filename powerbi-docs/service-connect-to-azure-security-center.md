---
title: "Power BI で Azure Security Center に接続する"
description: "Power BI 用 Azure Security Center"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: d052bc054e55eabfab53ad3b1ac9229f0a750785
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Power BI で Azure Security Center に接続する
Azure のセキュリティ データを Power BI に接続して、Azure のワークロードのセキュリティに関する洞察を得ます。 Power BI によって Azure セキュリティ センターのデータの一番上に自動的にダッシュボードとレポートが作成され、データを分析および探索できます。

Power BI 用 [Azure Security Center コンテンツ パック](https://app.powerbi.com/getdata/services/azure-security-center)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. **[サービス]** ボックスで、 **[取得]**を選択します。
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. **[Azure Security Center]** \> **[取得]** を選択します。
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. サブスクリプション ID を指定します。 [これらのパラメーターの見つけ方](#FindingParams)について詳しくは、後述します。
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. **[認証方法]** として**[oAuth2]** を選択し、**[サイン イン]** をクリックします。 ダイアログが表示されたら、Azure の資格情報を入力します。
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. 承諾後、インポート処理が自動的に開始されます。 完了すると、ナビゲーション ウィンドウに、新しいダッシュ ボード、レポート、モデルが表示されます。 インポートされたデータを表示するダッシュボードを選択します。
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](service-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="whats-included"></a>含まれるもの
コンテンツ パックには、リソースのセキュリティの統計、アラート分析、および防止分析に関する情報が含まれます。

## <a name="system-requirements"></a>システム要件
このコンテンツ パックでは、Azure セキュリティ センターが有効になっているサブスクリプション ID へのアクセスする必要があります。 詳細については、Azure Portal の [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2) を参照してください。

また、コンテンツ パックのユーザーは、(個人アカウントではなく) 組織のアカウントで接続する必要があります。

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>パラメーターの見つけ方
サブスクリプション ID を確認するには、2 つの簡単な方法があります。

1. https://portal.azure.com から &gt; [参照] -&gt; [サブスクリプション] -&gt; [サブスクリプション ID]
2. https://manage.windowsazure.com から -&gt; [設定] -&gt; [サブスクリプション ID]

サブスクリプション ID は数字や文字の長いセットで、上記の手順 \#4 の例のようになります。 

## <a name="troubleshooting"></a>トラブルシューティング
アカウントのサイズによっては、データの読み込みに時間がかかる場合があります。 ログイン中にエラーが発生した場合は、パラメーターと、アカウントで Azure セキュリティ センターが有効になっていることを確認してください。

コンテンツ パックは読み込まれるものの、データが表示されない場合は、組織のアカウントで接続していることを確認してください。 個人アカウントは Azure Security Center でサポートされていますが、ユーザーが組織以外のアカウントで接続した場合、API (およびコンテンツ パック) で予期した値が返されません。 組織のアカウントにアクセスできるようにして、もう一度接続を試してください。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI でデータを取得する](service-get-data.md)

