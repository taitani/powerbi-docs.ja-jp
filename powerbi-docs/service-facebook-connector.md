---
title: "サード パーティのサービス: Power BI Desktop の Facebook コネクタ"
description: "サード パーティのサービス: Power BI Desktop の Facebook コネクタ"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.author: davidi
ms.openlocfilehash: 4e8600aac79683a53b7c2075b3d81e91b3354901
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2017
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Power BI Desktop の Facebook コネクタ
**Power BI Desktop** の Facebook コネクタは、Facebook Graph API に依存します。 そのため、機能と可用性は、時間の経過と共に変わる場合があります。

「[Power BI Desktop の Facebook コネクタに関するチュートリアル](desktop-tutorial-facebook-analytics.md)」を参照してください。

Facebook では 2015 年 4 月 30 日に<sup></sup> Graph API v1.0 の有効期限が切れました。 Power BI は Facebook コネクタのバックグラウンドで Graph API を使用し、これによりデータに接続でき、分析できます。

2015 年 4 月 30 日より前に作成されたクエリは、<sup></sup>すでに機能しなくなっていたり、返すデータが少なくなったりしています。 2015 年 4 月 30 日以降、<sup></sup>Power BI では、Facebook API のすべての呼び出しで v2.2 を利用しています。 クエリが 2015 年 4 月 30 日より前に作成され、それ以降に使用されていない場合は、もう一度認証して、要求される新しいアクセス許可のセットを承認しなければならない可能性があります。

すべての変更に調和するように更新プログラムをリリースすることを試みていますが、API は、生成するクエリの結果に影響を与えるように変更される可能性があります。 特定のクエリがサポートされなくなる可能性もあります。 このような依存関係があることから、このコネクタの使用中にはクエリの結果は保証できません。

Facebook API の変更の詳細については、[こちら](https://developers.facebook.com/docs/apps/changelog#v2_0)をクリックしてください。

