---
title: Power BI Desktop での Azure Consumption Insights データへの接続 (Beda)
description: Power BI Desktop を使用して、Azure に簡単に接続し、使用状況を把握できます
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1e82ec988389790a3d96cb6f98f0db5d1a385fda
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="connect-to-azure-consumption-insights-in-power-bi-desktop-beta"></a>Power BI Desktop での Azure Consumption Insights への接続 (Beda)
**Azure Consumption Insights** コネクタを使用すれば、**Power BI Desktop** で Azure に接続して、組織における Azure サービスの使用状況に関する詳細なデータと情報を得ることができます。 また、メジャー、カスタム列、およびビジュアルを作成して、組織での Azure の使用状況についてレポートを作成し、共有することができます。 このリリースの **Azure Consumption Insights** コネクタはベータ版であり、変更される可能性があります。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01.png)

この記事では、**Azure Consumption Insights** コネクタを使用して接続し、必要なデータを取得する方法と、Azure Enterprise Connector の使用からの移行方法について説明します。また、**ACI** (Azure Consumption Insights) API で使用可能な*使用状況の詳細列* のマッピングについても説明します。

## <a name="connect-to-azure-consumption-insights"></a>Azure Consumption Insights への接続
**Azure Consumption Insights** コネクタを使用して正常に接続するには、Azure Portal 内の Enterprise 機能にアクセスする必要があります。

**Azure Consumption Insights** コネクタを使用して接続するには、**Power BI Desktop** の **[ホーム]** リボンから **[データの取得]** を選択します。 左側のカテゴリから **[オンライン サービス]** を選択すると、**[Microsoft Azure Consumption Insights (Beta)]** が表示されます。 **[接続]** を選択します。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

表示されるダイアログ ボックスで、*登録番号* を入力します。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

* 登録番号は、次の画像に示されている場所で、[Azure Enterprise Portal](https://ea.azure.com) から取得できます。
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)
  
  このバージョンのコネクタでサポートされるのは、https://ea.azure.com からのエンタープライズ登録のみです。現在、中国での登録はサポートされていません。

次に、接続するための*アクセス キー*を指定します。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

* 登録用のアクセス キーは [Azure Enterprise Portal](https://ea.azure.com) で確認できます。
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

*アクセス キー*を指定して **[接続]** を選択すると、**[ナビゲーター]** ウィンドウが開き、使用可能な 4 つのテーブル (*Summary*、*Usage*、*PriceSheet*、および *MarketPlace*) が表示されます。 テーブルの横にあるチェック ボックスをオンにすれば、プレビューを表示できます。 1 つ以上のテーブルを選択するには、名前の横のチェック ボックスをオンにしてから **[読み込み]** を選択します。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04.png)

> [!NOTE]
> *Summary* と *PriceSheet* テーブルを使用できるのは、登録レベルの API キーの場合のみです。 また、これらのテーブル内のデータには、既定で *Usage* と *PriceSheet* の現在の月のデータが含まれます。 *Summary* と *MarketPlace* テーブルは現在の月に制限されません。
> 
> 

**[読み込み]** を選択すると、**Power BI Desktop** にデータが読み込まれます。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

選択したデータが読み込まれると、選択したテーブルとフィールドが **[フィールド]** ウィンドウに表示されます。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>Azure Consumption Insights の使用
**Azure Consumption Insights** コネクタを使用するには、Azure Portal 内の Enterprise 機能にアクセスする必要があります。

**Azure Consumption Insights** コネクタを使用して正常にデータを読み込んだら、**クエリ エディター**を使用して独自のカスタム メジャーと列を作成することができます。また、**Power BI サービス**で共有できるビジュアル、レポート、およびダッシュボードを作成できます。

Azure には、空のクエリを使用して取得できる、サンプルのカスタム クエリ コレクションも含まれています。 これを使用するには、**Power BI Desktop** の **[ホーム]** リボンで、**[データの取得]** のドロップダウンの矢印を選択してから **[空のクエリ]** を選択します。 また、**クエリ エディター**の左側の **[クエリ]** ウィンドウで右クリックし、表示されるメニューから **[新しいクエリ]、[空のクエリ]** の順に選択することもできます。

**数式バー**に次のように入力します。

    = MicrosoftAzureConsumptionInsights.Contents

次の画像のように、サンプルのコレクションが表示されます。

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

レポートを操作する場合やクエリを作成する場合は、次のようにします。

* 現在の日付を起点として月数を定義するには、*numberOfMonth* を使用します。
  * 現在の日付を起点として、インポートする月数を表す 1 から 36 までの値を使用します。 インポートの制約と Power BI のクエリで許容されるデータ量のしきい値を回避するため、12 か月を超えるデータを取得しないようにしてください。
* 過去の期間の月数を定義するには、*startBillingDataWindow* と *endBillingDataWindow* を使用します。
* *numberOfMonth* は、*startBillingDataWindow* や *endBillingDataWindow* と併用*しない*でください。

## <a name="migrating-from-the-azure-enterprise-connector"></a>Azure Enterprise Connector からの移行
一部の顧客は *Azure Enterprise Connector (Beta)* を使用してビジュアルを作成しています。このベータ版は最終的には廃止され、**Azure Consumption Insights** コネクタと置き換えられます。 **Azure Consumption Insights** コネクタでは、以下のような機能および拡張機能が提供されます。

* *残高集計*および *Marketplace での購入*で使用可能な追加のデータ ソース
* *startBillingDataWindow* や *endBillingDataWindow* などの、新しい拡張パラメーター
* パフォーマンスと応答性の向上

顧客が新しい **Azure Consumption Insights** コネクタに移行し、カスタム ダッシュボードまたはレポートを作成する際に行った作業を保持できるように、以下の手順では新しいコネクタへの移動方法を示します。

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>手順 1: 新しいコネクタを使用して Azure に接続する
最初の手順では、**Azure Consumption Insights** コネクタを使用して接続します (詳細については、この記事の前半で説明しました)。 この手順では、**Power BI Desktop** の **[ホーム]** リボンから **[データの取得]、[空のクエリ]** の順に選択します。

### <a name="step-2-use-the-advanced-editor-to-create-a-query"></a>手順 2: 詳細エディターを使用してクエリを作成する
**クエリ エディター**で、**[ホーム]** リボンの **[クエリ]** セクションから **[詳細エディター]** を選択します。 表示された **[詳細エディター]** ウィンドウで、次のクエリを入力します。

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

もちろん、*enrollmentNumber* の値は、[Azure Enterprise Portal](https://ea.azure.com) から取得できる、自分の登録番号に置き換える必要があります。 *numberOfMonth* パラメーターは、現在のデータを起点とした過去のデータの月数を示します。 現在の月にはゼロ (0) を使用します。

**[詳細エディター]** ウィンドウで **[完了]** を選択すると、プレビューが更新され、テーブルの指定された月の範囲からのデータが表示されます。 **[閉じて適用]** を選択して戻ります。

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>手順 3: メジャーとカスタム列を新しいレポートに移動する
次に、新しい詳細テーブルに、作成したカスタム列またはメジャーを移動する必要があります。 この手順を以下に示します。

1. メモ帳 (または他のテキスト エディター) を開きます。
2. 移動するメジャーを選択し、*[数値]* フィールドからテキストをコピーして、メモ帳に配置します。
   
   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. *Query1* を元の詳細テーブルの名前に変更します。
4. テーブルを右クリックし、**[新しいメジャー]** を選択して、テーブルに新しいメジャーとカスタム列を作成します。次に格納されているメジャーと列を切り取って貼り付けます (すべてのメジャーと列に対して繰り返します)。

### <a name="step-4-re-link-tables-that-had-relationships"></a>手順 4: リレーションシップを持つテーブルを再リンクする
多くのダッシュボードには、日付テーブルやカスタム プロジェクトで使用されるテーブルなど、検索またはフィルタリングに使用されるテーブルが追加されています。 これらのリレーションシップを再確立することで、未解決のほとんどの問題が解決されます。 その方法を次に示します。

- **Power BI Desktop** の **[モデリング]** タブで、**[リレーションシップの管理]** を選択し、モデル内のリレーションシップを管理できるウィンドウを表示します。 必要に応じて、テーブルを再リンクします。
   
    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>手順 5: ビジュアルを確認し、必要に応じてフィールドの書式設定を調整する
これで、元のビジュアル、テーブル、およびドリルダウンのほとんどは予期したとおりに動作するはずです。 ただし、すべて予期したとおり適切に動作するように、書式設定するには微調整がいくつか必要な場合があります。 ダッシュボードとビジュアルをそれぞれ調べて、予期したとおりに動作することを確認するには少し時間がかかります。

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>Azure Consumption Insights (ACI) API を使用して使用量データを取得する
Azure では [**Azure Consumption Insights (ACI) API**](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/) も提供されます。 ACI API を使用して、Azure の使用量情報の収集、レポート作成、および視覚化に関する独自のカスタム ソリューションを作成することができます。

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>ポータル、コネクタ、および API 間での名前と使用状況の詳細のマッピング
Azure Portal の詳細の列と名前は、API とコネクタのものと似ていますが、必ずしも同じであるわけではありません。 明確にするために、以下の表で API、コネクタ、および Azure Portal に表示される列のマッピングを示します。 また、列が古いものであるかどうかも示します。 これらの用語の詳細と定義については、「[企業ユーザー向けの Reporting API - 使用状況の詳細](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail)」を参照してください。

| ACI コネクタ / ContentPack ColumnName | ACI API の列名 | EA の列名 | 古い / 旧バージョンとの互換性のために存在する |
| --- | --- | --- | --- |
| AccountName |accountName |Account Name |いいえ |
| AccountId |accountId | |はい |
| AcccountOwnerId |accountOwnerEmail |AccountOwnerId |いいえ |
| AdditionalInfo |additionalInfo |AdditionalInfo |いいえ |
| AdditionalInfold | | |はい |
| Consumed Quantity |consumedQuantity |Consumed Quantity |いいえ |
| Consumed Service |consumedService |Consumed Service |いいえ |
| ConsumedServiceId |consumedServiceId | |はい |
| Cost |cost |ExtendedCost |いいえ |
| Cost Center |costCenter |Cost Center |いいえ |
| Date |date |Date |いいえ |
| 日 | |日 |いいえ |
| DepartmentName |departmentName |Department Name |いいえ |
| DepartmentID |departmentId | |はい |
| Instance ID | | |はい |
| InstanceId |instanceId |Instance ID |いいえ |
| 場所 | | |はい |
| Meter Category |meterCategory |Meter Category |いいえ |
| Meter ID | | |はい |
| Meter Name |meterName |Meter Name |いいえ |
| Meter Region |meterRegion |Meter Region |いいえ |
| Meter Sub-Category |meterSubCategory |Meter Sub-Category |いいえ |
| MeterId |meterId |Meter ID |いいえ |
| Month | |Month |いいえ |
| 製品 |product |製品 |いいえ |
| ProductId |productId | |はい |
| Resource Group |resourceGroup |Resource Group |いいえ |
| Resource Location |resourceLocation |Resource Location |いいえ |
| ResourceGroupId | | |はい |
| ResourceLocationId |resourceLocationId | |はい |
| ResourceRate |resourceRate |ResourceRate |いいえ |
| ServiceAdministratorId |serviceAdministratorId |ServiceAdministratorId |いいえ |
| ServiceInfo1 |serviceInfo1 |ServiceInfo1 |いいえ |
| ServiceInfo1Id | | |はい |
| ServiceInfo2 |serviceInfo2 |ServiceInfo2 |いいえ |
| ServiceInfo2Id | | |はい |
| Store Service Identifier |storeServiceIdentifier |Store Service Identifier |いいえ |
| StoreServiceIdentifierId | | |はい |
| Subscription Name |subscriptionName |Subscription Name |いいえ |
| タグ |tags |タグ |いいえ |
| TagsId | | |はい |
| Unit Of Measure |unitOfMeasure |Unit Of Measure |いいえ |
| Year | |Year |いいえ |
| SubscriptionId |subscriptionId |SubscriptionId |はい |
| SubscriptionGuid |subscriptionGuid |SubscriptionGuid |いいえ |

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

