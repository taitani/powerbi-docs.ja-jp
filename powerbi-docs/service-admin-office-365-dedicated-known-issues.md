---
title: Office 365 Dedicated カスタマー - 既知の問題
description: Office 365 Dedicated カスタマーのサポート - 既知の問題。 このトピックでは、Office 365 Dedicated カスタマーに固有の問題について説明します。 これらの問題には、グループ機能の制限と、iPhone アプリでのバニティ ドメインの使用についての制限が含まれています。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: cedb3e1572fbf20a32abe4f28b38030539502124
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="office-365-dedicated-customers---known-issues"></a>Office 365 Dedicated カスタマー - 既知の問題
Power BI は Office 365 Dedicated のカスタマーにもサポートされるようになりました。  O365 Dedicated のカスタマーは、そのテナントのアカウントでサインインすれば、Power BI を使用できます。 現在 2 つの既知の問題があります。

## <a name="groups"></a>グループ
[グループ] のコンテキスト メニューで **[メンバー]** または **[カレンダー]** を選択すると、メール アプリにリダイレクトされます。  **[ファイル]** と **[会話]** は正常に動作します。

![](media/service-admin-office-365-dedicated-known-issues/group-menu.png)

## <a name="iphone-app---sign-in-with-vanity-domain-leads-to-error"></a>iPhone アプリ - バニティ ドメインを使用してサインインするとエラーが発生する
iPhone アプリでサインインするときに、バニティ ドメインでログインすると、エラーが発生する場合があります。

*サインイン エラー*  
"*予期しない内部エラーが発生しました。もう一度お試しください。*

この問題を回避するには、カスタム ドメインではなく、Power BI サービス内のユーザー アイコンをクリックすると一覧表示されるメール アドレスを使ってサインインしてください。

![](media/service-admin-office-365-dedicated-known-issues/sign-in-address.png)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

