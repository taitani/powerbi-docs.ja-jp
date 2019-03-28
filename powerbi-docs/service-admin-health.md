---
title: Office 365 で Power BI サービスの正常性を追跡する
description: Microsoft 365 管理センターでサービスの現在および過去の正常性を表示する方法を説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 4ab0fe4e3398a37da34af02282a847f316f3f727
ms.sourcegitcommit: 20ae9e9ffab6328f575833be691073de2061a64d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "58383155"
---
# <a name="track-power-bi-service-health-in-office-365"></a>Office 365 で Power BI サービスの正常性を追跡する

Microsoft 365 管理センターでは Power BI 管理者向けの重要なツールが提供されており、その中にはサービスの正常性に関する現在および過去の情報が含まれます。 この情報にアクセスするには、次のどちらかのロールを割り当てられている必要があります:Power BI サービス管理者または Office 365 全体管理者。 ロールについて詳しくは、「[Power BI に関連する管理者ロール](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi)」をご覧ください。

1. [Microsoft 365 管理センター](https://portal.office.com/adminportal)にサインインします。

1. **[サービス正常性]** タイルを選びます。

    ![[サービス正常性] タイル](media/service-admin-health/service-health-tile.png)

1. 現在の一覧で **[N アドバイザリ]** または **[N インシデント]** を選んで、結果を確認します。 次の図では、3 件のアクティブなアドバイザリのうちの 1 つが示されています。

    ![アクティブなアドバイザリ](media/service-admin-health/active-advisories.png)

1. 詳しい情報を見るには、項目の **[詳細の表示]** を選びます。 次の図では、最新の状態の更新など、追加の詳細が表示されています。

    ![アドバイザリの詳細](media/service-admin-health/advisory-details.png)

    下にスクロールして他の情報を確認し、完了したらウィンドウを閉じます。

1. すべてのサービスの履歴情報を表示するには、メイン リストの右上で **[履歴の表示]** を選びます。 次に、**[過去 7 日間]** または **[過去 30 日間]** を選びます。 現在のサービス正常性に戻るには、**[現在の状態の表示]** を選びます。