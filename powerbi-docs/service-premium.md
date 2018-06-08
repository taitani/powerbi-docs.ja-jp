---
title: Power BI Premium とは
description: Power BI Premium は、組織やチームの専用の容量であり、より信頼できるパフォーマンスとより大きなデータ ボリュームを提供します。ユーザーごとのライセンスを購入する必要はありません。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: 980aa830e38e49613b54ad473ef23eb7eac78ed2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722795"
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium とは
Power BI Premium には、組織やチームが Power BI サービスを実行するための専用のリソースが用意されており、より信頼できるパフォーマンスやより大きなデータ ボリュームが提供されます。 また、Premium ではコンテンツを広範囲に配布でき、ビューアーのユーザーごとのライセンスを購入する必要はありません。

Premium 容量にワークスペースを割り当てることで、Power BI Premium を活用できます。 *Premium 容量*は組織の専用のリソースです。 Premium 容量に割り当てられていないワークスペースの場合、これらは共有された容量にあります。

*共有された容量*は、他の顧客と共有されている計算リソースでワークロードが実行される場合に、Power BI で使用されるエクスペリエンスです。 共有された容量では、すべてのユーザー エクスペリエンスの品質を確保するために個々のユーザーにより多くの制限が設けられます。

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>容量レベル
Power BI 内には 2 種類の容量があります。 共有された容量と Power BI Premium 容量です。 これらの違いを以下に示します。

|  | 共有された容量 | Power BI Premium 容量 |
| --- | --- | --- |
| **更新間隔** |8/日 |制限なし |
| **専用ハードウェアでの分離** |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能") |
| ***すべてのユーザー*****へのエンタープライズ配布** | | |
| アプリ |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能")<sup>1</sup> |
| 埋め込み API とコントロール |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能")<sup>2</sup> |
| **Power BI レポートのオンプレミスでの発行** |![](media/service-premium/not-available.png "利用不可") |![](media/service-premium/available.png "利用可能") |

*<sup>1</sup> アプリの無料ユーザーの使用量には、Web およびモバイルでのコンテンツ表示、Q&A、クイック分析情報、Cortana、CSV へのエクスポート、Excel および PowerPoint の使用が含まれます。Pro ライセンスは一覧にないその他の操作に必要です。共有データセットのレポート作成や Excel の分析機能などです。詳細については、[Power BI 無料版と Power BI Pro の機能比較](service-free-vs-pro.md)ページを参照してください。*  
*<sup>2</sup> Power BI Premium は GA 後にさらに機能が拡張されます。*

### <a name="premium-capacity"></a>Premium 容量
Power BI Premium 容量の使用を開始するには、ワークスペースを容量に割り当てる必要があります。 ワークスペースを Premium 容量に割り当てる方法の詳細については、「[Power BI Premium の管理](service-admin-premium-manage.md)」を参照してください。

ワークスペースが Premium 容量でバックアップされている場合、Power BI Premium には以下の利点があります。

* スケジュールされた更新: これまでは、インポートしたモデルで更新をスケジュールする場合、8x/日に制限されていました。 Premium ワークスペースでは、データセットに対するこの制限は解除されます。 これは、DirectQuery のスケジュールされたキャッシュの更新設定には適用されません。 Premium 容量および共有された容量でも同じです。
* 専用ハードウェアでの分離 - 共有された容量の性質上、レポートとダッシュボードのパフォーマンスは、保護の有無に関係なく、容量の他のワークロードのリソース需要に影響を受ける可能性があります。 逆に、Premium では、関係のないワークロードから分離することで、ワークロードのより一貫性のある信頼できるパフォーマンスが提供されます。

アプリが Premium 容量でバックアップされている (つまり、Premium に現在割り当てられているアプリ ワークスペースから発行された) 場合、発行されたアプリは、割り当てられているライセンスに関係なく、組織内のすべてのユーザーが使用できます。 これは、Power BI の無料ユーザーでも、発行されたアプリを使用できることを意味します。

### <a name="shared-capacity"></a>共有された容量
既定では、ワークスペースは共有された容量にあります。 これには、個人用の*マイワークスペース*とアプリ ワークスペースが含まれます。 共有された容量は、他の顧客と共有されている計算リソースでワークロードが実行される場合に、Power BI で使用されるエクスペリエンスです。

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium 容量ノード
Power BI Premium は、さまざまな v コア容量を含むノード構成で使用できます。 特定の SKU オファリングとコストの詳細については、[Power BI の料金に関するページ](https://powerbi.microsoft.com/pricing/)を参照してください。 [コスト計算ツール](https://powerbi.microsoft.com/calculator/)も利用できます。 埋め込み分析の容量計画については、「[Planning a Power BI Enterprise Deployment whitepaper](https://aka.ms/pbienterprisedeploy)」 (Power BI のエンタープライズ展開の計画に関するホワイト ペーパー) を参照してください。

* P ノードは、埋め込み展開またはサービス展開で使用できます。
* EM ノードは、埋め込み展開でのみ使用できます。
* EM1 および EM2 

>[!NOTE]
>この表のリンクが正しく動作するのは、Office 365 の全体管理者の場合のみです。その他のユーザーの場合、404 エラーが表示されます。 

| 容量ノード | 合計 v コア数<br/>*(バックエンド + フロントエンド)* | バックエンド v コア数 | フロントエンド v コア数 | DirectQuery/ライブ接続の制限 | ピーク時の最大のページ レンダリング数 | 使用できるかどうか |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 v コア |0.5 v コア、2.5 GB の RAM |0.5 v コア |1 秒あたり 3.75 |150-300 |入手可能 |
| [EM2 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 v コア |1 v コア、5 GB の RAM |1 v コア |1 秒あたり 7.5 |301-600 |入手可能 |
| [EM3 (月極め)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 v コア |2 v コア、10 GB の RAM |2 v コア | |601-1,200 |入手可能 |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 v コア |4 v コア、25 GB の RAM |4 v コア |1 秒あたり 30 |1,201-2,400 |使用可能 ([月極め](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)も使用可能) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 v コア |8 v コア、50 GB の RAM |8 v コア |1 秒あたり 60 |2,401-4,800 |入手可能 |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 v コア |16 v コア、100 GB の RAM |16 v コア |1 秒あたり 120 |4,801-9600 |入手可能 |

* フロントエンド v コアは、Web サービス、ダッシュボードとレポート ドキュメントの管理、アクセス権の管理、スケジューリング、API、アップロードとダウンロード、および一般にユーザー エクスペリエンスに関連するすべてについて責任があります。
* バックエンド v コアは、手間のかかる作業、つまり、クエリ処理、キャッシュ管理、R サーバーの実行、データ更新、自然言語処理、リアルタイム フィード、およびサーバー側のレポートとイメージのレンダリングについて責任があります。 また、バックエンド v コアでは、一定量のメモリが予約されています。 十分なメモリを確保することは、特に、大きなデータ モデルまたは大量のアクティブ データセットを処理する場合に重要になります。

## <a name="power-bi-report-server"></a>Power BI Report Server
Power BI Premium には、オンプレミスでの Power BI Report Server の実行権限が含まれます。 詳細については、「[Power BI Report Server の概要](report-server/get-started.md)」を参照してください。

## <a name="next-steps"></a>次の手順
[Power BI Premium のよく寄せられる質問](service-premium-faq.md)  
[Power BI Premium リリース ノート](service-premium-release-notes.md)  
[Power BI Premium の購入方法](service-admin-premium-purchase.md)  
[Power BI Premium の管理](service-admin-premium-manage.md)  
[Microsoft Power BI Premium ホワイト ペーパー](https://aka.ms/pbipremiumwhitepaper)  
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)  
[組織内の Power BI を管理する](service-admin-administering-power-bi-in-your-organization.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

