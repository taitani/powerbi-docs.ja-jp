---
title: Power BI Premium でのクエリのキャッシュ
description: Power BI Premium でのクエリのキャッシュ
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/03/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: fbfd8c98743144e0c9604aca4174d6ef32916e77
ms.sourcegitcommit: de0b72915183a8a784d3227838bd704c1c209422
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "58914278"
---
# <a name="query-caching-in-power-bi-premium"></a>Power BI Premium でのクエリのキャッシュ

Power BI Premium を使用する組織は、*クエリ キャッシュ*を活用して、データセットに関連付けられたレポートを高速化できます。 クエリ キャッシュにより、Premium 容量はそのローカル キャッシュ サービスを使用してクエリ結果を維持するよう指示され、基になるデータ ソースによってそれらの結果が計算されることが回避されます。

> [!IMPORTANT]
> クエリ キャッシュは Power BI Premium でのみ利用できます。 Azure Analysis Services または SQL Server Analysis Services を利用する LiveConnect データセットに適用することはできません。

キャッシュされたクエリ結果は、ユーザーおよびデータセットのコンテキストに固有であり、常にセキュリティ規則を順守します。 現時点では、このサービスでは、表示した最初のページに対してのみクエリ キャッシュが行われます。 つまり、レポートと対話する際には、クエリはキャッシュされません。 キャッシュには、個人のブックマークと永続的フィルターが反映されます。 同じクエリを利用する[ダッシュボードのタイル](service-dashboard-tiles.md)も、クエリがキャッシュされることでメリットを得られます。 パフォーマンスは、データセットが頻繁にアクセスされてあまり更新する必要がない場合に、特に大きなメリットを得られます。 クエリ キャッシュにより、全体的なクエリ数を減少させることで、Premium 容量に対する負荷を軽減することもできます。

クエリ キャッシュの動作は、Power BI サービスのデータセット用の **[設定]** ページで制御します。 このページには次の 3 つの設定があります。

- **Capacity Default** \(容量の既定値\): データセットは Premium 容量の設定を継承します。 既定の容量は、Power BI Premium 容量の管理者によって制御されます。

- **オフ**: このデータセットにはクエリ キャッシュを使用しません。

- **オン**: このデータセットにはクエリ キャッシュを使用します。

![[クエリ キャッシュ] ダイアログ ボックス](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> キャッシュの設定を **[オン]** から **[オフ]** に変更すると、以前に保存されたデータセットのクエリ結果が容量のキャッシュから削除されます。 キャッシュは明示的にオフにするか、または管理者が容量の既定値を **[オフ]** に設定していた場合は規定値に戻すことで、オフにすることができます。 キャッシュをオフにすると、レポートで次回このデータセットに対してクエリを実行する際に、わずかな遅延が生じる可能性があります。 遅延は、保存された結果を活用しないでオンデマンドで実行される、こうしたレポート クエリが原因で発生します。 また、クエリを処理するには、まず必須のデータセットをメモリに読み込まなければならない場合があります。


