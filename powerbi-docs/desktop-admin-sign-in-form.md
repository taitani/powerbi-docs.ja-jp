---
title: 管理者が Power BI Desktop のサインイン フォームを管理する方法
description: Power BI Desktop を開いたときの最初のサインイン フォームを管理する方法について説明します。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
ms.openlocfilehash: 98bf9579ae7ee551634eed765138c0e78156464c
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>管理者が Power BI Desktop のサインイン フォームを管理する方法
Power BI Desktop を初めて起動したときは、サインイン フォームが表示されます。 情報を入力するか、Power BI にサインインして続行できます。 管理者は、レジストリ キーを使ってこのフォームを管理できます。 

![Power BI Desktop の初回サインイン フォーム](media/desktop-admin-sign-in-form/sign-in-form.png)

管理者は、次のレジストリ キーを使って、サインイン フォームを無効にすることができます。 グローバル ポリシーを使って、これを組織全体に適用することもできます。

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

値を 0 にすると、ダイアログ ボックスは無効になります。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

