---
title: Power BI Premium でワークロードを構成する方法
description: Power BI Premium 容量でワークロードを構成する方法について説明します。
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/01/2019
LocalizationGroup: Premium
ms.openlocfilehash: fbff4b744cf4a35f2fe1d0ae46f4676cd5f1db77
ms.sourcegitcommit: 8525b6365f3e224176730f4b8e5dae83f540a4ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58795247"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium 容量でワークロードを構成する

この記事では、Power BI Premium 容量に対するワークロードの構成と有効化について説明します。 既定では、容量は、Power BI のクエリの実行に関連付けられているワークロードのみをサポートします。 **[AI (Cognitive Services)](service-cognitive-services.md)**、**[データフロー](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)**、および**[ページ分割されたレポート](paginated-reports-save-to-power-bi-service.md)** に対する追加のワークロードの有効化と構成を行うこともできます。

## <a name="default-memory-settings"></a>既定のメモリ設定

クエリのワークロードは、Premium 容量の SKU によって決定されるリソース用に最適化され、そのリソースによって制限されます。 Premium 容量では、容量のリソースを使用できる追加のワークロードもサポートされます。 これらのワークロードの既定のメモリの値は、SKU で使用可能な容量ノードに基づきます。 最大メモリの設定は、累積ではありません。 指定された最大値までのメモリは、AI とデータフローには動的に割り当てられますが、ページ分割されたレポートには静的に割り当てられます。 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>サービスとしてのソフトウェア (SaaS) シナリオにおける Microsoft Office の SKU

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI (Cognitive Services) | 20% (既定値)、TBD (最小値)| 20% (既定値)、TBD (最小値) | 20% (既定値)、TBD (最小値) | 20% (既定値)、TBD (最小値) | 20% (既定値)、TBD (最小値) |
| データフロー | N/A |20% (既定値)、12% (最小値)  | 20% (既定値)、5% (最小値)  | 20% (既定値)、3% (最小値) | 20% (既定値)、2% (最小値)  |
| ページ分割されたレポート | N/A |N/A | 20% (既定値)、10% (最小値) | 20% (既定値)、5% (最小値) | 20% (既定値)、2.5% (最小値) |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>サービスとしてのプラットフォーム (PaaS) シナリオにおける Microsoft Azure の SKU

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI (Cognitive Services) | N/A                      | 20% (既定値)、TBD (最小値)                      | 20% (既定値)、TBD (最小値)                     | 20% (既定値)、TBD (最小値) | 20% (既定値)、TBD (最小値) | 20% (既定値)、TBD (最小値) |
| データフロー         | 40% (既定値)、40% (最小値) | 24% (既定値)、24% (最小値) | 20% (既定値)、12% (最小値) | 20% (既定値)、5% (最小値)  | 20% (既定値)、3% (最小値) | 20% (既定値)、2% (最小値)   |
| ページ分割されたレポート | N/A                      | 該当なし                      | N/A                     | 20% (既定値)、10% (最小値) | 20% (既定値)、5% (最小値) | 20% (既定値)、2.5% (最小値) |
| | | | | | |

## <a name="configure-workloads"></a>ワークロードを構成する

容量の使用可能なリソースを最大化するには、使用する場合にのみワークロードを有効にします。 メモリ設定を変更するのは、既定の設定では容量のリソース要件が満たされないことが判明した場合のみにしてください。  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI 管理ポータルでワークロードを構成するには

1. **[容量の設定]** > **[Premium 容量]** で、容量を選択します。

1. **[その他のオプション]** で **[ワークロード]** を展開します。

1. 1 つ以上のワークロードを有効にして、**[最大メモリ]** の値を設定します。   

    
    ![ワークロードの有効化](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. **[適用]** をクリックします。

> [!NOTE]
> ページ分割されたレポート ワークロードを有効化した場合、レポートを表示する際に独自のコードを実行できます (コンテンツに基づくテキストの色の動的な変更など)。 Power BI Premium は、容量内に含まれる領域で、ページ分割されたレポートを実行します。 ワークロードがアクティブかどうかに関係なく、この領域に指定した最大メモリが使用されます。 Power BI レポートまたはデータフローを同じ容量内で使用する場合は、他のワークロードに悪影響を及ぼさない程度の少量のメモリをページ分割されたレポートに対して設定してください。 まれに、ページ分割されたレポート ワークロードを使用できなくなる場合があります。 その場合、管理ポータルではワークロードがエラー状態であると表示され、ユーザーに対してはレポートの表示がタイムアウトしたと表示されます。 この問題を軽減するには、ワークロードを無効にしてからもう一度有効にしてください。

### <a name="rest-api"></a>REST API

ワークロードの有効化と容量への割り当ては、[Capacities](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API を使用します。

## <a name="monitoring-workloads"></a>ワークロードの監視

[Power BI Premium 容量メトリック アプリ](service-admin-premium-monitor-capacity.md)のデータセット、データフロー、およびページ分割されたレポートのメトリックにより、容量に対して使用可能なワークロードを監視できます。 

## <a name="next-steps"></a>次の手順

[Power BI Premium 容量のリソースの管理と最適化](service-premium-understand-how-it-works.md)   
[データフローを使用した Power BI でのセルフサービスのデータ準備](service-dataflows-overview.md)   
[Power BI Premium のページ分割されたレポートとは](paginated-reports-report-builder-power-bi.md)   

他にわからないことがある場合は、 [Power BI コミュニティに質問する](http://community.powerbi.com/)