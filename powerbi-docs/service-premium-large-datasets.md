---
title: 大規模なデータセットに対する Power BI Premium のサポート
description: Power BI Premium で最大 10 GB のデータセットがサポートされるようになりました。
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: fa05fd6808ebe78d5d17e2ad3d93fbcf22f7d3c9
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="power-bi-premium-support-for-large-datasets"></a>大規模なデータセットに対する Power BI Premium のサポート

Power BI Premium は、最大 10 GB のサイズの Power BI Desktop ファイル (.pbix) のアップロードをサポートします。 アップロードが完了すると、データセットのサイズは最大 12 GB まで更新できます。 大規模なデータセットを使用するには、そのデータセットを Premium 容量に割り当てられているワークスペースに発行します。
 
## <a name="best-practices"></a>ベスト プラクティス

このセクションでは、大規模なデータセットを操作するためのベスト プラクティスについて説明します。

**大規模なモデルは、容量のリソースを大量に消費する**ため、1 GB を超えるモデルには少なくとも P1 SKU をお勧めします。 次の表に、さまざまな .pbix のサイズに対して推奨される SKU を示します。


   |SKU  |.pbix のサイズ   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | 最大 10 GB   |



**.pbix ファイルは、圧縮率の高い状態のデータを表しています**。 データはメモリに読み込まれるときに数回展開される場合があります。データの更新中に、そこからさらに数回展開される場合があります。

**大規模なデータセットのスケジュールされた更新には時間がかかることがあり**、リソースを大量に消費する場合があります。 したがって、あまり多くの更新が重複しないようにスケジュールしてください。 また、この容量では、スケジュールされた更新ジョブのタイムアウトがすべてのデータセットに対して倍の 4 時間になっていることにも注意してください。

前回のデータセットの使用から時間が経っている場合、モデルが Premium 容量のメモリに読み込まれるため、**大規模なデータセットの最初のレポートの読み込みに時間がかかる場合があります**。 読み込みに時間がかかるレポートの読み込みバーには、読み込みの進行状況が表示されます。

**Premium 容量からワークスペースを削除すると**、モデルおよび関連するすべてのレポートとダッシュボードが機能しなくなります。

**Premium 容量ではクエリごとのメモリと時間の制約値は大幅に高くなりますが**、フィルターとスライサーを使用して、必要なビジュアルだけを表示することを強くお勧めします。

## <a name="next-steps"></a>次の手順
[Power BI Premium とは](service-premium.md)  
[Power BI Premium リリース ノート](service-premium-release-notes.md)  
[Microsoft Power BI Premium ホワイト ペーパー](https://aka.ms/pbipremiumwhitepaper)  
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)  
[Extended Pro Trial のアクティブ化](service-extended-pro-trial.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。
