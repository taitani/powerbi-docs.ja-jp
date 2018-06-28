---
title: 管理者が Power BI Desktop のサインイン フォームを管理する方法
description: Power BI Desktop を開いたときの最初のサインイン フォームを管理する方法について説明します。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/02/2018
ms.author: davidi
ms.openlocfilehash: f35553acd65aeea2c1bf02b04fcbd665af4b99ea
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "34721089"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>管理者が Power BI Desktop のサインイン フォームを管理する方法
Power BI Desktop を初めて起動したときは、サインイン フォームが表示されます。 情報を入力するか、Power BI にサインインして続行できます。 管理者は、レジストリ キーを使ってこのフォームを管理します。 

![Power BI Desktop の初回サインイン フォーム](media/desktop-admin-sign-in-form/sign-in-form.png)

管理者は、次のレジストリ キーを使って、サインイン フォームを無効にします。 グローバル ポリシーを使って、これを組織全体に適用することもできます。

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

値を 0 にすると、ダイアログ ボックスは無効になります。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

