---
title: 管理ポータルを使用して Power BI Premium 容量を監視する
description: Power BI 管理ポータルを使用して、Premium 容量を監視します。
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794120"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>管理ポータルで容量を監視する

この記事では、管理ポータルの [容量の設定] 領域を使用して、容量のパフォーマンスをすばやく把握する方法について説明します。  容量に関する最も詳細なメトリックを取得するには、[Power BI Premium 容量メトリック](service-admin-premium-monitor-capacity.md) アプリを使用するのが最もよい方法です。

## <a name="capacity-metrics"></a>容量メトリック

管理者ポータルの **[容量の設定]** 領域では、容量によって過去 7 日間に置かれた負荷と使用されたリソースを示す、4 つのゲージが表示されます。 これら 4 つのタイルは 1 時間単位の時間枠に基づき、過去 7 日間で対応するメトリックが何時間 80% を超えたかを示します。 このメトリックは、エンドユーザーのエクスペリエンスが低下する可能性を示します。

![7 日間での使用状況](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **メトリック** | **説明** |
| --- | --- |
| CPU |CPU 使用率が 80% を超えた回数です。 |
| メモリ スラッシング |バックエンド コアのメモリ負荷を表します。 具体的には、これは、複数のデータセットの使用によるメモリ負荷により、データセットがメモリから締め出された回数のメトリックです。 |
| メモリ使用量 |平均メモリ使用量です (ギガバイト (GB) 単位)。 |
| DQ/秒 | 直接クエリとライブ接続の数が上限の 80% を超えた回数です。 <br>  DirectQuery の合計数と 1 秒あたりのライブ接続クエリの数は制限されています。 制限は、P1 で 30 回/秒、P2 で 60 回/秒、P3 で 120 回/秒です。  上記のスロットルは、DirectQuery とライブ接続クエリの数を加えたものです。 たとえば、15 の DirectQueries と 1 秒あたり 15 のライブ接続がある場合、スロットルに達しています<br> これは、オンプレミスおよびクラウドの接続にも等しく適用されます。 |
|  |  |

メトリックは、過去 1 週間の使用状況を反映します。  メトリックをさらに詳細に見たい場合は、概要タイルのいずれかをクリックします。  Premium 容量の各メトリックの詳細グラフが表示されます。 CPU のメトリックの詳細を次の図に示します。

![CPU の詳細使用状況グラフ](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

これらのグラフは、過去 1 週間について 1 時間ごとに集計され、Premium 容量で特定のパフォーマンス関連イベントが発生した可能性があるときを特定するのに役立ちます。

いずれかのメトリックの基になっているデータを、csv ファイルにエクスポートすることもできます。  エクスポートすると、過去 1 週間の詳細情報を 3 分間隔で見ることができます。

## <a name="next-steps"></a>次の手順

Power BI Premium 容量を監視する方法について学習したので、容量の最適化について学習します。

> [!div class="nextstepaction"]
> [Power BI Premium 容量のリソースの管理と最適化](service-premium-understand-how-it-works.md)
