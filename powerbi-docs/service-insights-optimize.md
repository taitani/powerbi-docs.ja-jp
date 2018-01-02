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
ms.date: 12/06/2017
ms.author: mihart
ms.openlocfilehash: 263d85a9db996bd7979c29b9c8919fc63f97b1d0
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2017
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

