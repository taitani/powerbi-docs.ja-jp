---
title: サインインした Power BI ユーザーを見つける
description: テナント管理者が Power BI にサインインしたユーザーを確認するには、Azure Active Directory アクセスと使用状況レポートを使用して、ユーザーを表示します。
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Administration
ms.openlocfilehash: 78deaa2e98060e86756876e3d736fe973a5f5905
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="find-power-bi-users-that-have-signed-in"></a>サインインした Power BI ユーザーを見つける
テナント管理者が Power BI にサインインしたユーザーを確認するには、Azure Active Directory アクセスと使用状況レポートを使用して、ユーザーを表示します。

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

[新規](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)および[クラシック](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Azure Active Directory (Azure AD) ポータルのアクティビティ レポートにアクセスできます。 上のビデオでは例としてクラシック ポータルを使用していますが、この記事では、新しいポータルに焦点を当てて説明します。

> [!NOTE]
> このアクティビティ レポートには Power BI (無料) ユーザーと Pro ユーザーの両方が含まれていますが、ユーザーのライセンスではユーザーは特定されません。
> 
> 

## <a name="requirements"></a>要件
サインイン アクティビティ レポートを表示するための要件を次に示します。

* グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーのロールが付与されたユーザーが、データにアクセスできます。
* すべてのユーザー (管理者以外) が、独自のサインインでアクセスできます。
* すべてのサインイン アクティビティ レポートを表示するには、テナントに Azure AD Premium ライセンスが関連付けられている必要があります。

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Azure ポータルを使用してサインインを表示する
Azure AD ポータルを使用して、サインイン アクティビティを表示できます。

1. **Azure ポータル**を参照し、**[Azure Active Directory]** を選択します。
2. **[アクティビティ]** の **[サインイン]** を選択します。
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. **[Microsoft Power BI]** または **[Power BI Gateway]** のいずれかを選択して、アプリケーションをフィルター処理し、**[適用]** を選択します。
   
    **Microsoft Power BI** は、サービス関連のサインイン アクティビティを対象としています。一方、**Power BI Gateway** は、オンプレミス データ ゲートウェイを対象とした特定のサインインです。
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>データをエクスポートする
サインイン データをエクスポートするオプションは 2 つあります。 これを行うには、csv ファイルをダウンロードするか、PowerShell を使用します。

### <a name="download-csv"></a>csv のダウンロード
アクティビティ画面で、ツールバーの **[ダウンロード]** を選択できます。 これにより、フィルター処理されているデータの csv ファイルがダウンロードされます。

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
PowerShell を使用して、サインイン データをエクスポートできます。 Azure AD ドキュメント内で[サンプル](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)を使用できます。

> [!NOTE]
> PowerShell サンプルを動作させるには、必ず [Azure AD レポート API にアクセスするための前提条件](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites)に従う必要があります。
> 
> 

## <a name="data-retention"></a>データのリテンション期間
サインイン関連のデータは、最大 30 日間使用できます。 詳しくは、「[Azure Active Directory レポートの保持ポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)」を参照してください。

## <a name="next-steps"></a>次の手順
[Azure Active Directory ポータルのサインイン アクティビティ レポート (新しいポータル)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[アクセスおよび使用状況レポートの表示 (クラシック ポータル)](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[サインイン サンプルの PowerShell スクリプト](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Azure Active Directory レポートの保持ポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[組織内での監査の使用](service-admin-auditing.md)  
[Extended Pro Trial のアクティブ化](service-extended-pro-trial.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

