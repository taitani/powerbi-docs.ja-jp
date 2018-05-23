---
title: Power BI と Azure で同じアカウントを使用する
description: Power BI と Azure で同じアカウントのログインを使用する方法
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 375a251e7515ad33396cc4cf5ebb0ee715ab0330
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Power BI と Azure で同じアカウントを使用する
Power BI と Azure を両方とも使っているユーザーであれば、両方のサービスに同じログインを使用して、パスワードを 2 回入力する手間を省きたいと思われることでしょう。

Power BI では、職場か学校のメール アドレスに関連付けられている組織アカウントを使ってサインインします。  Azure では、Microsoft アカウントまたは組織アカウントのいずれかを使用してサインインします。

Azure と Power BI の両方に同じログインを使用したい場合は、必ず組織アカウントを使用して Azure にサインインしてください。

**既に Microsoft アカウントを使用して Azure にサインインしている場合**

Azure の共同管理者として、組織アカウントを追加できます。  次にその方法を示します。

1. [Azure の管理ポータル](http://manage.windowsazure.com/)にサインインします。 複数の Azure ディレクトリでユーザーになっている場合は、 **[サブスクリプション]** をクリックし、フィルター処理を行って編集するディレクトリとサブスクリプションのみを表示します。
2. ナビゲーション ウィンドウで、 **[設定]**、 **[管理者]**、 **[追加]** の順にクリックします。
3. 組織アカウントに関連付けられているメール アドレスを入力します。
4. 組織アカウントでアクセスしたいサブスクリプションを選択して、チェック マークをクリックします。

次回 Azure の管理ポータルにサインインするときに、組織のメール アドレスを使用します。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

