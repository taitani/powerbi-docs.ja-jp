---
title: Power BI Pro ライセンスの割り当て
description: Power BI Pro ライセンスの割り当て
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
ms.date: 03/22/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: cc22bfa635bb9d91624e6d4a5cdfe301d6478af6
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2018
---
# <a name="assigning-power-bi-pro-licenses"></a>Power BI Pro ライセンスの割り当て

管理者は、ユーザーに Power BI Pro ライセンスを割り当てる際に、さまざまな管理ポータルと PowerShell コマンドレットから選択することができます。 Power BI ライセンスの管理は、Azure Active Directory (Azure AD) でバックアップされています。

* Azure サブスクリプションの所有者は、[Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0) で Azure Active Directory ブレードを使用することができます。 

* グローバル管理者とユーザー アカウント管理者は、[Office 365 管理センター](https://portal.office.com/AdminPortal/Home#/homepage)を使用できます。

## <a name="managing-power-bi-pro-licenses-in-the-azure-portal"></a>Azure Portal での Power BI Pro ライセンスの管理

Power BI では、基本サービスとして Azure AD を使用します。 Azure AD には、ユーザーのアカウントとグループが格納され、購入済みの製品に関する情報など、他の設定も格納されます。

### <a name="assigning-licenses-to-individual-user-accounts"></a>個々のユーザー アカウントへのライセンスの割り当て

Azure サブスクリプションの所有者である場合は、以下の手順に従って、個々のユーザー アカウントに Pro ライセンスを割り当てます。

1. [Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0) に移動します。 

2. 左側のナビゲーション バーで、Azure Active Directory をクリックします。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-01.png)

3. Azure Active Directory ブレードで、[ライセンス] をクリックします。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-02.png)

4. [ライセンス] ブレードで、[すべての製品] をクリックしてから、[Power BI Pro] をクリックしてライセンス ユーザーのリストを表示します。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-03.png)

5. [割り当て] をクリックして、Power BI Pro ライセンスを追加のユーザー アカウントに追加します。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-04.png)

> [!NOTE]
> ライセンスのほとんどの側面を管理できますが、Azure Portal で Power BI Pro ライセンスを購入することはできません。 Power BI Pro サブスクリプションを購入するには、Office 365 管理センターを使用します。 詳しくは、「[Power BI Pro を購入する](https://docs.microsoft.com/en-us/power-bi/service-admin-purchasing-power-bi-pro)」をご覧ください。
>

## <a name="managing-power-bi-pro-licenses-in-the-office-365-admin-center"></a>Office 365 管理センターでの Power BI Pro ライセンスの管理

グローバル管理者である場合は、Office 365 管理センターで、Power BI Pro サブスクリプションを購入し、組織用の関連するライセンスを管理します。

Office 365 管理者である場合は、以下の手順に従って、個々のユーザー アカウントに Pro ライセンスを割り当てます。

1. Office 365 管理センターに移動します。

2. 左側のナビゲーション ウィンドウで、[ユーザー] を展開し、[アクティブ ユーザー] をクリックします。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-05.png)

3. 1 つまたは複数のユーザーを選択してから、製品ライセンスの [編集] をクリックします。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-06.png)

4. Power BI Pro で、設定をオンに切り替えてから [保存] をクリックします。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-07.png)

5. 選択したアカウントの [状態] で、Power BI Pro ライセンスが正常に割り当てられていることを確認します。

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-08.png)

> [!NOTE]
> サブスクリプションのライセンスがない場合は、左側のナビゲーション ウィンドウで [課金] を展開し、[サブスクリプション] をクリックして追加します。 [サブスクリプション] ページで、Power BI Pro のサブスクリプションを選択してから [ライセンスの追加/削除] をクリックします。
>

## <a name="next-steps"></a>次の手順
[組織内の Power BI Pro](service-admin-power-bi-pro-in-your-organization.md)
</br>
[Extended Pro Trial のアクティブ化](service-extended-pro-trial.md)
</br>
[個々のユーザーに対する Power BI サービス契約](https://powerbi.microsoft.com/terms-of-service/)
</br>
[Power BI Premium に関するお知らせ](https://aka.ms/pbipremium-announcement)
</br>
[サインインした Power BI ユーザーを見つける](service-admin-access-usage.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。