---
title: Microsoft Power BI Premium とは何ですか?
description: Power BI Premium は、組織やチームの専用の容量であり、より信頼できるパフォーマンスとより大きなデータ ボリュームを提供します。ユーザーごとのライセンスを購入する必要はありません。
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/21/2018
LocalizationGroup: Premium
ms.openlocfilehash: 2ca75f191f27bd158b9fab67c7be6902154f8ac1
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641231"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium とは何ですか?

Microsoft Power BI Premium には、組織が Power BI サービスを実行するための専用のリソースが用意されています。 より信頼できるパフォーマンスが提供され、より大きなデータ ボリュームを利用できます。 また、Premium ではコンテンツを広範囲に配布でき、コンテンツ コンシューマーに対してユーザーごとの Pro ライセンスを購入する必要はありません。 購入については、「[Power BI Premium の購入方法](service-admin-premium-purchase.md)」を参照してください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="premium-capacity-and-shared-capacity"></a>Premium 容量と共有された容量

*Premium 容量*にワークスペースを割り当てることで、Power BI Premium を活用できます。 Premium 容量は組織の専用のリソースです。 Premium 容量に割り当てられていないワークスペースは、*共有された容量*にあります。 共有された容量では、他の顧客と共有されている計算リソースでワークロードが実行されます。

次の図は、Contoso 組織を例として使用して、Premium 容量と、共有された容量との関係を示しています。

![Power BI Premium の図](media/service-premium/premium-chart.png)

| 領域 | 説明 |
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
| **専用ハードウェアでの分離** |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能") |
| ***すべてのユーザー*****へのエンタープライズ配布** | | |
| アプリと共有 |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能")<sup>1</sup> |
| 埋め込み API とコントロール |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能")<sup>2</sup> |
| **Power BI レポートのオンプレミスでの発行** |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能") |
| | | |

*<sup>1</sup> 詳細については、[ライセンス タイプ別機能](service-features-license-type.md)に関する記事を参照してください。*  
*<sup>2</sup> Power BI Premium は今後さらに機能が拡張されます。*

Premium 容量にワークスペースを割り当てる方法の詳細については、「[Power BI Premium の管理](service-admin-premium-manage.md).」を参照してください。

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium 容量ノード

Power BI Premium は、さまざまな v コア容量を含むノード構成で使用できます。 特定の SKU オファリングとコストの詳細については、[Power BI の価格のページ](https://powerbi.microsoft.com/pricing/)を参照してください。 [コスト計算ツール](https://powerbi.microsoft.com/calculator/)も利用できます。 埋め込み分析の容量計画については、「[Planning a Power BI Enterprise Deployment whitepaper](https://aka.ms/pbienterprisedeploy)」 (Power BI のエンタープライズ展開の計画に関するホワイト ペーパー) を参照してください。 次のように要約できます。

* P ノードは、埋め込み展開またはサービス展開で使用できます。

* EM ノードは、埋め込み展開でのみ使用できます。 EM ノードでは Premium 容量にアクセスできません。たとえば、Power BI Pro ライセンスを持っていないユーザーとアプリを共有することはできません。

>[!NOTE]
>この表のリンクが正しく動作するのは、Office 365 の全体管理者ロールの場合のみです。 その他のユーザーの場合、404 エラーが表示されます。

| 容量ノード | 合計 v コア数<br/>*(バックエンド + フロントエンド)* | バックエンド v コア数 | フロントエンド v コア数 | DirectQuery/ライブ接続の制限 | ピーク時の最大のページ レンダリング数 | 使用できるかどうか |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 v コア |0.5 v コア、2.5 GB RAM |0.5 v コア |1 秒あたり 3.75 |150-300 |入手可能 |
| [EM2 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 v コア |1 v コア、5 GB RAM |1 v コア |1 秒あたり 7.5 |301-600 |入手可能 |
| [EM3 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 v コア |2 v コア、10 GB RAM |2 v コア | |601-1,200 |入手可能 |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 v コア |4 v コア、25 GB RAM |4 v コア |1 秒あたり 30 |1,201-2,400 |使用可能 ([月極め](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)も使用可能) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 v コア |8 v コア、50 GB RAM |8 v コア |1 秒あたり 60 |2,401-4,800 |入手可能 |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 v コア |16 v コア、100 GB RAM |16 v コア |1 秒あたり 120 |4,801-9600 |入手可能 |
| | | | | | | |

* フロントエンド v コアは、Web サービス、ダッシュボードとレポート ドキュメントの管理、アクセス権の管理、スケジューリング、API、アップロードとダウンロード、および一般にユーザー エクスペリエンスに関連するすべてについて責任があります。

* バックエンド v コアは、手間のかかる作業、つまり、クエリ処理、キャッシュ管理、R サーバーの実行、データ更新、自然言語処理、リアルタイム フィード、およびサーバー側のレポートとイメージのレンダリングについて責任があります。 また、バックエンド v コアでは、一定量のメモリが予約されています。 十分なメモリを確保することは、特に、大きなデータ モデルまたは大量のアクティブ データセットを処理する場合に重要になります。

## <a name="power-bi-report-server"></a>Power BI Report Server

Power BI Premium には、組織内で Power BI Report Server をオンプレミスで実行する機能も含まれます。 詳細については、「[Power BI Report Server とは](report-server/get-started.md)」を参照してください。

## <a name="next-steps"></a>次の手順

[Power BI Premium のよく寄せられる質問](service-premium-faq.md)
[Power BI Pro の購入方法](service-admin-premium-purchase.md)
[Power BI Premium の管理](service-admin-premium-manage.md)
[Microsoft Power BI Premium のホワイトペーパー](https://aka.ms/pbipremiumwhitepaper)
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)
[組織内の Power BI を管理する](service-admin-administering-power-bi-in-your-organization.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。
