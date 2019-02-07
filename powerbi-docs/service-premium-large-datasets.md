---
title: 大規模なデータセットに対する Power BI Premium のサポート
description: Power BI Premium で最大 10 GB のデータセットがサポートされるようになりました。
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 941d4bc3d66ce8e636f730d5757b7215c978d582
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794829"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>大規模なデータセットに対する Power BI Premium のサポート

Power BI Premium は、最大 10 GB のサイズの Power BI Desktop ファイル (.pbix) のアップロードをサポートします。 アップロードが完了すると、データセットのサイズは最大 12 GB まで更新できます。 大規模なデータセットを使用するには、そのデータセットを Premium 容量に割り当てられているワークスペースに発行します。
 
## <a name="best-practices"></a>ベスト プラクティス

このセクションでは、大規模なデータセットを操作するためのベスト プラクティスについて説明します。

**大規模なモデルは、容量のリソースを大量に消費します**。 1 GB を超えるモデルには少なくとも P1 SKU をお勧めします。 大規模なモデルを、最大 A3 までの A SKU に支えられたワークスペースに発行すると機能する場合がありますが、更新した場合は機能しません。

次の表に、さまざまな .pbix のサイズに対して推奨される SKU を示します。

   |SKU  |.pbix のサイズ   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3、P4、P5    | 最大 10 GB   |

Power BI Embedded の A4 SKU は P1 SKU と、A5 は P2 と、A6 は P3 とそれぞれ同等です。 なお、大規模なモデルを A および EM SKU に発行した場合、共有された容量のサイズ制限エラーに固有ではないエラーが返される場合があります。 A および EM SKU の大規模なモデルの更新エラーは、タイムアウトを示す可能性があります。 これらのシナリオでのエラー メッセージの改善に取り組んでいます。

**.pbix ファイルは、圧縮率の高い状態のデータを表しています**。 データはメモリに読み込まれるときに数回展開される場合があります。データの更新中に、そこからさらに数回展開される場合があります。

**大規模なデータセットのスケジュールされた更新には時間がかかることがあり**、リソースを大量に消費する場合があります。 したがって、あまり多くの更新が重複しないようにスケジュールしてください。 また、この容量では、スケジュールされた更新ジョブのタイムアウトがすべてのデータセットに対して倍の 4 時間になっていることにも注意してください。 より高速で信頼性が高く、消費リソースが少ないので、[増分更新](service-premium-incremental-refresh.md)をお勧めします。

前回のデータセットの使用から時間が経っている場合、モデルが Premium 容量のメモリに読み込まれるため、**大規模なデータセットの最初のレポートの読み込みに時間がかかる場合があります**。 読み込みに時間がかかるレポートの読み込みバーには、読み込みの進行状況が表示されます。

**Premium 容量からワークスペースを削除すると**、モデルおよび関連するすべてのレポートとダッシュボードが機能しなくなります。

**Premium 容量ではクエリごとのメモリと時間の制約値は大幅に高くなりますが**、フィルターとスライサーを使用して、必要なビジュアルだけを表示することを強くお勧めします。

**次の手順**

[Microsoft Power BI Premium とは何ですか?](service-premium.md)
[Power BI Premium リリース ノート](service-premium-release-notes.md)
[Microsoft Power BI Premium のホワイトペーパー](https://aka.ms/pbipremiumwhitepaper)
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。
