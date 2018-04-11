---
title: Power BI と Azure で同じアカウントを使用する
description: Power BI と Azure で同じアカウントのログインを使用する方法
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: fac2faac6ddd62bbc5f8a74ba1764b10e597f58d
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2018
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Power BI と Azure で同じアカウントを使用する
Power BI と Azure を両方とも使っているユーザーであれば、両方のサービスに同じログインを使用して、パスワードを 2 回入力する手間を省きたいと思われることでしょう。

Power BI では、職場か学校のメール アドレスに関連付けられている組織アカウントを使ってサインインします。  Azure では、Microsoft アカウントまたは組織アカウントのいずれかを使用してサインインします。

Azure と Power BI の両方に同じログインを使用したい場合は、必ず組織アカウントを使用して Azure にサインインしてください。

**既に Microsoft アカウントを使用して Azure にサインインしている場合**

Azure の共同管理者として、組織アカウントを追加できます。  次にその方法を示します。

1. [Azure の管理ポータル](http://manage.windowsazure.com/)にサインインします。 複数の Azure ディレクトリでユーザーになっている場合は、 **[サブスクリプション]** をクリックし、フィルター処理を行って編集するディレクトリとサブスクリプションのみを表示します。
2. ナビゲーション ウィンドウで、 **[設定]**、 **[管理者]**、 **[追加]**の順にクリックします。
3. 組織アカウントに関連付けられているメール アドレスを入力します。
4. 組織アカウントでアクセスしたいサブスクリプションを選択して、チェック マークをクリックします。

次回 Azure の管理ポータルにサインインするときに、組織のメール アドレスを使用します。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

