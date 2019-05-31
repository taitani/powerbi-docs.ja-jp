---
title: サード パーティのサービス:Power BI Desktop の Facebook コネクタ
description: サード パーティのサービス:Power BI Desktop の Facebook コネクタ
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6b02717c49a1207dfec39ebb1529e7e9b222fa62
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65512857"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Power BI Desktop の Facebook コネクタ
**Power BI Desktop** の Facebook コネクタは、Facebook Graph API に依存します。 そのため、機能と可用性は、時間の経過と共に変わる場合があります。

「[Power BI Desktop の Facebook コネクタに関するチュートリアル](desktop-tutorial-facebook-analytics.md)」を参照してください。

Facebook では、2015 年 4 月 30日で Graph API v1.0 の期限切れです。 Power BI は Facebook コネクタのバックグラウンドで Graph API を使用し、これによりデータに接続でき、分析できます。

2015 年 4 月 30日する前に作成されたクエリは職場または返すデータが少なく不要になった可能性があります。 30 の 2015 年 4 月後は、Power BI は、Facebook api のすべての呼び出しで v2.8 を活用します。 クエリが 2015 年 4 月 30 日より前に作成され、それ以降に使用されていない場合は、もう一度認証して、要求される新しいアクセス許可のセットを承認しなければならない可能性があります。

すべての変更に調和するように更新プログラムをリリースすることを試みていますが、API は、生成するクエリの結果に影響を与えるように変更される可能性があります。 特定のクエリがサポートされなくなる可能性もあります。 このコネクタを使用する場合、この依存関係のため、クエリの結果は保証できません。

Facebook API の変更の詳細については、[こちら](https://developers.facebook.com/docs/apps/changelog#v2_0)をクリックしてください。

