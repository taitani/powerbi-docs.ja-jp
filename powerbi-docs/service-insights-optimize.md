---
title: "Power BI クイック インサイト用のデータの最適化"
description: "Power BI クイック インサイト用のデータを最適化します。 Power BI でデータの詳細情報を見つけられない場合、実行できることを説明しています。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2017
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 2936ac75684e4efe1870c556b27fcbdbc77d17ec
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2018
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Power BI クイック インサイト用のデータの最適化
クイック インサイトの結果を改善する必要がありますか。  データセット所有者の場合は、以下を試します。

* データセットの列を表示または非表示にします。 Power BI クイック インサイトでは、非表示の列は検索されません。  そのため、重複する列や不要な列を非表示にして、興味のある列を表示します。
* 名前、時刻、日付、数値などのさまざまなデータの種類を組み合わせて使用します。
* 情報が重複している列を避けます (非表示にします)。  これは、意味のあるパターンの検索から貴重な時間を奪います。  たとえば、ある列に状態名を略さずに含め、別の列に省略名を含めるなどです。
* データが統計的に有意でないことを示すエラー メッセージが表示される場合があります。  これは、ごく単純なモデルやデータが少ないモデル、日付または数値の列がないモデルの場合に発生することがあります。 インサイトを生成するには、データセットに少なくとも 1 つのディメンションと 1 つのメジャーが必要です。

### <a name="next-steps"></a>次の手順
[Power BI クイック インサイト](service-insights.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

