---
title: ゲートウェイのパフォーマンス監視 (パブリック プレビュー)
description: この記事では、オンプレミス データ ゲートウェイのアクティビティのパフォーマンスの監視についての情報を提供します。
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535369"
---
# <a name="gateway-performance-monitoring-public-preview"></a>ゲートウェイのパフォーマンス監視 (パブリック プレビュー)

パフォーマンスを監視するには、手動で Windows パフォーマンス モニター ツールからパフォーマンス カウンターの監視のゲートウェイ管理者がこれまで依存しています。 追加のクエリのログ記録を提供できおよび[ゲートウェイのパフォーマンスの PBI のテンプレート ファイル](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit)結果を視覚化します。 この機能は、ゲートウェイの使用状況に関する新しい洞察を提供する、低速で実行するクエリをトラブルシューティングすることができます。

> [!NOTE]
> この機能は、標準モードで、オンプレミス データ ゲートウェイとパーソナル モードではなく、現在使用できません。

## <a name="enable-performance-logging"></a>パフォーマンスのログ記録を有効にします。

この機能を有効にするには、次の変更を行う、 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*ファイルで、"\Program Files\On-オンプレミス データ ゲートウェイ"フォルダー。

1. Update **QueryExecutionReportOn**に_True_ゲートウェイを使用して実行されるクエリの追加のログ記録を有効にします。 このオプションを有効にするには、クエリ実行のレポートとクエリ実行の集計レポート ファイルの両方が作成されます。

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Update **SystemCounterReportOn**に_True_メモリと CPU のシステム カウンターの追加のログ記録を有効にします。 このオプションを有効にするには、システム カウンターの集計レポート ファイルが作成されます。

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. 必要に応じて更新できる構成ファイルには、その他の値があります。

    - **ReportFilePath**:次の 3 つのログ ファイルの格納場所のパスを決定します。 既定では、このパスは、"\Users\PBIEgwService\AppData\Local\Microsoft\On-premises データ gateway\Report"または"Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On、オンプレミス データ gateway\Report"、OS のバージョンに応じてのいずれか。 以外のゲートウェイのサービス アカウントを使用するかどうかは_PBIEgwService_パスのこの部分をサービス アカウントの名前に置き換えます。
    - **ReportFileCount**:保持するには、各種類のログ ファイルの数を決定します。 既定値は、10 です。
    - **ReportFileSizeInBytes**:維持するために、ファイルのサイズを決定します。 既定値は、104857600 です。
    - **QuerExecutionAggregationTimeInMinutes**:クエリ実行の情報の集計を分単位の数を決定します。 既定値は、5 です。
    - **SystemCounterAggregationTimeInMinutes**:システムのカウンターを集計する時間を分単位を決定します。 既定値は、5 です。

1. 構成ファイルに変更を加えた後にこれらの構成値を有効にするゲートウェイを再起動します。 内の指定した場所で生成されるレポート ファイルが表示されるようになりました始めます**ReportFilePath**します。

    > [!NOTE]
    > 最大 10 分かかることができ、時間の設定の**QuerExecutionAggregationTimeInMinutes**ファイル、フォルダーに表示を開始するまでは、構成ファイルにします。

## <a name="understand-performance-logs"></a>パフォーマンス ログを理解します。

この機能を有効にすると、次の 3 つの新しいログ ファイルを作成します。

- クエリの実行レポート
- クエリ実行の集計レポート
- システムのカウンタの集計レポート

クエリ実行のレポートには、詳細なクエリ実行の情報が含まれています。 次の属性をキャプチャしました。

|属性 |説明 |
| ---- | ---- |
|**GatewayObjectId** |ゲートウェイの一意識別子。 |
|**RequestId** |ゲートウェイ要求の一意の識別子。 複数のクエリで同じ可能性があります。 |
|**データ ソース** |データ ソースの種類とデータ ソースの両方が含まれています。 |
|**QueryTrackingId** |クエリの一意の識別子。 |  
|**QueryExecutionEndTimeUTC** |クエリの実行が完了した時刻。 |
|**QueryExecutionDuration**(ミリ秒) |クエリの実行の期間です。 |
|**QueryType** |渡されたクエリは、Power BI の更新または DirectQuery または PowerApps と Microsoft Flow からのクエリ、クエリでのインスタンスに入力します。 |
|**DataProcessingEndTimeUTC** |データのスプール、データの取得、圧縮、データ処理、および完了するように同様のアクティビティの処理時間します。 |
|**DataProcessingDuration**(ミリ秒) |スプール、データの取得、圧縮、データの処理などのデータ処理アクティビティの期間です。 |
|**成功** |クエリが成功または失敗したかどうかを示します。 |
|**エラー メッセージ** |クエリが失敗した場合は、エラー メッセージを示します。 |
| | |

クエリ実行の集計レポートには、によって、時間間隔に集計クエリの情報が含まれています**GatewayObjectId**、 **DataSource**、**成功**、および **。QueryType**します。 既定値は、5 分間ですが、以下に示すように調整することができます。 次の属性をキャプチャしました。

|属性 |説明 |
| ---- | ---- |
|**GatewayObjectId** |ゲートウェイの一意識別子。 |
|**AggregationStartTimeUTC** |対象のクエリの属性が集計された時間枠の開始。 |
|**AggregationEndTimeUTC** |クエリの属性が集計された時間枠の終了。 |
|**データ ソース** |データ ソースの種類とデータ ソースの両方が含まれています。 |
|**成功** |クエリが成功または失敗したかどうかを示します。 |
|**AverageQueryExecutionDuration**(ms) |集計の時間帯のクエリ実行時間を平均します。 |
|**MaxQueryExecutionDuration**(ミリ秒) |集計の時間帯の最大のクエリ実行時間。 |
|**MinQueryExecutionDuration**(ms) |集計の時間帯の最小のクエリ実行時間。 |
|**QueryType** |渡されたクエリは、Power BI の更新または DirectQuery または PowerApps と Microsoft Flow からのクエリ、クエリでのインスタンスに入力します。 |
|**AverageDataProcessingDuration**(ms) |集計の時間帯のデータ処理のスプール、データの取得、圧縮、データ処理、同様のアクティビティの平均時間。 |
|**MaxDataProcessingDuration**(ミリ秒) |集計の時間帯のスプール、データの取得、圧縮、データの処理などのデータ処理の最大時間。 |
|**MinDataProcessingDuration**(ミリ秒) |集計の時間帯のスプール、データの取得、圧縮、データの処理などのデータ処理の最小時間。 |
|**カウント** |クエリの数。 |
| | |

システムのカウンタの集計レポートには、時間間隔に集計システム カウンターの値が含まれています。 既定値は、5 分間ですが、以下に示すように調整することができます。 次の属性をキャプチャしました。

|属性 |説明 |
| ---- | ---- |
|**GatewayObjectId** |ゲートウェイの一意識別子。 |
|**AggregationStartTimeUTC** |システムのカウンターが集計された時間枠の開始。 |
|**AggregationEndTimeUTC** |システムのカウンターが集計された時間枠の終了。 |
|**CounterName** |システム カウンター、ゲートウェイ、マッシュ アップ、メモリと CPU 使用率など、全体的なマシンで、ゲートウェイをホストします。 |
|**最大** |集計の時間帯のシステム カウンターの最大値。 |
|**最小値** |集計の時間帯のシステム カウンターの最小値。 |
|**平均** |集計の時間帯のシステム カウンターの平均値。 |
| | |

## <a name="visualize-gateway-performance"></a>ゲートウェイのパフォーマンスを視覚化します。

次に、ログ ファイル内にあるデータを視覚化できます。

1. ダウンロード、[ゲートウェイ パフォーマンス PBI テンプレート](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit)し、Power BI desktop を使用して開きます。

1. フォルダーのパスがの値と一致することを確認、表示されたダイアログ ボックスで**ReportFilePath**します。

    ![フォルダーのパスのポップアップ](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. 選択**ロード**、し、テンプレート ファイルは、ログ ファイルからデータの読み込みを開始します。 すべてのビジュアルには、レポートでデータを使用して設定する必要があります。

1. 必要に応じて、PBIX としてこのファイルを保存し、自動更新について、サービスに発行します。

さらに、ニーズに合わせてこのテンプレート ファイルをカスタマイズできます。 Power BI テンプレートの詳細については、この参照してください。 [Microsoft Power BI ブログの投稿](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/)します。