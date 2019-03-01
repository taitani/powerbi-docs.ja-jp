---
title: Microsoft Power BI Premium とは何ですか?
description: Power BI Premium は、組織やチームの専用の容量であり、より信頼できるパフォーマンスとより大きなデータ ボリュームを提供します。ユーザーごとのライセンスを購入する必要はありません。
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/15/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: a048f589b19acd1a7c38a5b81cf781d1e76b7b5b
ms.sourcegitcommit: 187d20180d9bae5a2ec53748cede9e7301e0343e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56725342"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium とは何ですか?

Microsoft Power BI Premium には、組織が Power BI サービスを実行するための専用のリソースが用意されています。 より信頼できるパフォーマンスが提供され、より大きなデータ ボリュームを利用できます。 また、Premium ではコンテンツを広範囲に配布でき、コンテンツ コンシューマーに対してユーザーごとの Pro ライセンスを購入する必要はありません。  

## <a name="premium-capacity-and-shared-capacity"></a>Premium 容量と共有された容量

*Premium 容量*にワークスペースを割り当てることで、Power BI Premium を活用できます。 Premium 容量は組織の専用のリソースです。 Premium 容量に割り当てられていないワークスペースは、*共有された容量*にあります。 共有された容量では、他の顧客と共有されている計算リソースでワークロードが実行されます。

次の図は、Contoso 組織を例として使用して、Premium 容量と、共有された容量との関係を示しています。

![Power BI Premium の図](media/service-premium/premium-chart.png)

| 面 | 説明 |
| --- | --- |
| **(1)** Premium 容量内の項目 | <ul><li>アプリ ワークスペースへのアクセス (メンバーまたは管理者として) およびアプリの発行には、Power BI Pro ライセンスが必要です。<li>アプリの共有には Pro ライセンスが必要ですが、アプリの利用では必要ありません。<li>割り当てられているライセンスに関係なく、すべてのダッシュボードの受信者が、データ アラートを設定できます。<li>埋め込み用の REST API では、ユーザー アカウントではなく、Pro ライセンスが付与されたサービス アカウントを使用します。</ul> |
| **(2)** 共有された容量のマイ ワークスペース | <ul><li>アプリの共有にも利用にも、Pro ライセンスが必要です。</ul> |
| **(3)** 共有された容量のアプリ ワークスペース | <ul><li>すべてのアプリ使用に Pro ライセンスが必要です。</ul>|
| | |

共有された容量では、すべてのユーザー エクスペリエンスの品質を確保するため、Power BI によって個々のユーザーにより多くの制限が設けられます。 既定では、ワークスペースは共有された容量に含まれています。これには個人用の*マイ ワークスペース*やアプリ ワークスペースも含まれています。

次の表に、共有された容量と Premium 容量の違いの概要を示します。

|  | 共有された容量 | Power BI Premium 容量 |
| --- | --- | --- |
| **更新間隔** |8/日 |48/日 |
| 専用ハードウェアでの分離 |![利用不可](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| "*すべてのユーザー*" へのエンタープライズ配布 | | |
| アプリと共有 |![利用不可](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| 埋め込み API とコントロール |![利用不可](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Power BI レポートのオンプレミスでの発行 |![利用不可](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Power BI Premium は今後さらに機能が拡張されます。



### <a name="premium-capacity-nodes"></a>Premium 容量ノード

Power BI Premium は、さまざまな v コア容量を含むノード構成で使用できます。 特定の SKU オファリングとコストの詳細については、[Power BI の価格のページ](https://powerbi.microsoft.com/pricing/)を参照してください。 [コスト計算ツール](https://powerbi.microsoft.com/calculator/)も利用できます。 埋め込み分析の容量計画については、「[Planning a Power BI Enterprise Deployment whitepaper](https://aka.ms/pbienterprisedeploy)」 (Power BI のエンタープライズ展開の計画に関するホワイト ペーパー) を参照してください。 次のように要約できます。

* P ノードは、埋め込み展開またはサービス展開で使用できます。

* EM ノードは、埋め込み展開でのみ使用できます。 EM ノードは、power BI Pro ライセンスを持っていないユーザーにアプリを共有するなど、プレミアム機能にアクセスできません。

| 容量ノード | 合計 v コア数<br/>*(バックエンド + フロントエンド)*  | バックエンド V コア数 <sup>[1](#fn1)</sup> | フロントエンド V コア数 <sup>[2](#fn2)</sup> | DirectQuery/ライブ接続の制限 | 最大同時更新 |  使用できるかどうか
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (月極め) |1 v コア |0.5 v コア、2.5 GB RAM |0.5 v コア |1 秒あたり 3.75 |  1 | 利用可能 |
| EM2 (月極め) |2 v コア |1 v コア、5 GB RAM |1 v コア |1 秒あたり 7.5 |  2 | 利用可能 |
| EM3 (月極め) |4 v コア |2 v コア、10 GB RAM |2 v コア | | 3 |  利用可能 |
| P1 |8 v コア |4 v コア、25 GB RAM |4 v コア |1 秒あたり 30 | 6 | 使用可能 (月極めも使用可能) |
| P2 |16 v コア |8 v コア、50 GB RAM |8 v コア |1 秒あたり 60 | 12 | 利用可能 |
| P3 |32 v コア |16 v コア、100 GB RAM |16 v コア |1 秒あたり 120 | 24 | 利用可能 |
| | | | | | | |

<a name="fn1">1</a>:フロントエンド v コアは、Web サービスについて責任があります。 たとえば、ダッシュボードとレポート ドキュメントの管理、アクセス権の管理、スケジューリング、API、アップロードとダウンロード、および一般にユーザー エクスペリエンスに関連するすべてがあげられます。 

<a name="fn2">2</a>:バックエンド v コアは、手間のかかる作業、たとえば、クエリ処理、キャッシュ管理、R サーバーの実行、データ更新、自然言語処理、リアルタイム フィード、およびサーバー側のレポートとイメージのレンダリングについて責任があります。 また、バックエンド v コアでは、一定量のメモリが予約されています。 十分なメモリを確保することは、特に、大きなデータ モデルまたは大量のアクティブ データセットを処理する場合に重要になります。

## <a name="workloads-in-premium-capacity"></a>Premium の容量内のワークロード

Power BI におけるワークロードを、ユーザーに公開可能な多数のサービスのうちの 1 つとして考えてみましょう。 既定では、**Power BI Premium** と **Power BI Embedded** の容量でサポートされるのは、クラウド内で実行中の Power BI クエリに関連付けられているワークロードのみです。

現在では、2 つの追加ワークロード(**ページ分割されたレポート**および**データフロー**) に対応したプレビュー版サポートが用意されています。 これらのワークロードを Power BI 管理ポータルで、または Power BI REST API を使用して有効にします。 また、各ワークロードで使用できる最大メモリを設定するので、異なるワークロードが相互に及ぼす影響を制御できます。 詳細については、「[ワークロードを構成する](service-admin-premium-manage.md#configure-workloads)」を参照してください。

### <a name="default-memory-settings"></a>既定のメモリ設定

次の表は、使用可能なさまざまな[容量ノード](#premium-capacity-nodes)のメモリの既定値と最小値を示しています。 メモリはデータフローに動的に割り当てられていますが、ページ分割されたレポートには静的に割り当てられています。 詳細については、次のセクション「[ページ分割されたレポートに関する考慮事項](#considerations-for-paginated-reports)」を参照してください。

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>サービスとしてのソフトウェア (SaaS) シナリオにおける Microsoft Office の SKU

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| ページ分割されたレポート | N/A | 20% (既定値)、10% (最小値) | 20% (既定値)、5% (最小値) | 20% (既定値)、2.5% (最小値) |
| データフロー | 20% (既定値)、8% (最小値)  | 20% (既定値)、4% (最小値)  | 20% (既定値)、2% (最小値) | 20% (既定値)、1% (最小値)  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>サービスとしてのプラットフォーム (PaaS) シナリオにおける Microsoft Azure の SKU

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| ページ分割されたレポート | N/A                      | 該当なし                      | N/A                     | 20% (既定値)、10% (最小値) | 20% (既定値)、5% (最小値) | 20% (既定値)、2.5% (最小値) |
| データフロー         | 27% (既定値)、27% (最小値) | 20% (既定値)、16% (最小値) | 20% (既定値)、8% (最小値) | 20% (既定値)、4% (最小値)  | 20% (既定値)、2% (最小値) | 20% (既定値)、1% (最小値)   |

### <a name="considerations-for-paginated-reports"></a>ページ分割されたレポートに関する考慮事項

ページ分割されたレポート ワークロードを使用した場合、レポートを表示する際に独自のコードを実行できることに注意してください (コンテンツに基づくテキストの色の動的な変更など)。 この事実をふまえて、容量内に含まれている領域でページ分割されたレポートを実行することによって Power BI Premium 容量を保護します。 ワークロードがアクティブかどうかに関係なく、指定した最大メモリをこの領域に割り当てます。 Power BI レポートまたはデータフローを同じ容量内で使用する場合は、他のワークロードに悪影響を及ぼさない程度の少量のメモリをページ分割されたレポートに対して設定してください。

まれに、ページ分割されたレポート ワークロードを使用できなくなる場合があります。 その場合、管理ポータルではワークロードがエラー状態であると表示され、ユーザーに対してはレポートの表示がタイムアウトしたと表示されます。 この問題を軽減するには、ワークロードを無効にしてからもう一度有効にしてください。

## <a name="power-bi-report-server"></a>Power BI Report Server

Power BI Premium には、組織内で Power BI Report Server をオンプレミスで実行する機能も含まれます。 詳細については、「[Power BI Report Server とは](report-server/get-started.md)」を参照してください。

## <a name="next-steps"></a>次の手順

[Power BI Premium のよく寄せられる質問](service-premium-faq.md)
[Power BI Pro の購入方法](service-admin-premium-purchase.md)
[Power BI Premium の管理](service-admin-premium-manage.md)
[Microsoft Power BI Premium のホワイトペーパー](https://aka.ms/pbipremiumwhitepaper)
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。
