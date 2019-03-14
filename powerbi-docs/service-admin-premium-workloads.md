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
ms.date: 03/11/2019
LocalizationGroup: Premium
ms.openlocfilehash: 0baab138ee98d2ec96bc9f47e6e727525a57ed3e
ms.sourcegitcommit: f176ba9d52d50d93f264eca21bb3fd987dbf934b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57757248"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium 容量でワークロードを構成する

この記事では、Power BI Premium 容量に対するワークロードの構成と有効化について説明します。 既定では、容量は、Power BI のクエリの実行に関連付けられているワークロードのみをサポートします。 クエリのワークロードは、Premium 容量の SKU によって決定されるリソース用に最適化され、そのリソースによって制限されます。 Premium 容量では、容量リソースを使用できる追加のワークロードもサポートされます。

## <a name="configure-workloads"></a>ワークロードを構成する

AI、[データフロー](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)、および[ページ分割されたレポート](paginated-reports-save-to-power-bi-service.md)に対する追加のワークロードの有効化と構成を行うことができます。 これらのワークロードの既定のメモリの値は、SKU で使用可能な容量ノードに基づきます。 最大メモリの設定は、累積ではありません。 指定された最大値までのメモリは、AI とデータフローには動的に割り当てられますが、ページ分割されたレポートには静的に割り当てられます。 

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


## <a name="next-steps"></a>次の手順

[Power BI Premium 容量のリソースの管理と最適化](service-premium-understand-how-it-works.md)   
[データフローを使用した Power BI でのセルフサービスのデータ準備](service-dataflows-overview.md)   
[Power BI Premium のページ分割されたレポートとは](paginated-reports-report-builder-power-bi.md)   

他にわからないことがある場合は、 [Power BI コミュニティに質問する](http://community.powerbi.com/)