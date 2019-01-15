---
title: 代替メール アドレスの使用
description: 代替メール アドレスの使用
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5998f4b63a168c3056a5464844d008bd657ef7c9
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294268"
---
# <a name="using-an-alternate-email-address"></a>代替メール アドレスの使用

Power BI にサインアップするときには、メール アドレスを入力します。 既定では、Power BI はこのアドレスを使用して、サービスのアクティビティに関する更新を送信します。 たとえば、他のユーザーから送信される共有の招待は、このアドレスに配信されます。

場合によっては、サインアップ時のものとは異なるメール アドレスにメールを配信してほしいことがありあります。 この記事では、PowerShell および Office 365 で代替アドレスを指定する方法について説明します。 また、Azure Active Directory (Azure AD) においてメール アドレスが解決される方法についても説明します。

> [!NOTE]
> 代替アドレスを指定しても、サービス更新、ニュースレター、その他のプロモーション通信に Power BI で使用されるメール アドレスに影響はありません。  これらの通信は常に、Power BI へのサインアップ時に使用したメール アドレスに送信されます。

## <a name="use-office-365"></a>Office 365 を使用する

Office 365 で代替アドレスを指定するには、次の手順のようにします。

1. [Office 365 の個人情報ページ](https://portal.office.com/account/#personalinfo)を開きます。 プロンプトが表示されたら、Power BI で使用しているメール アドレスとパスワードを使ってサインインします。

1. 左側のメニューで、**[個人情報]** を選択します。

1. **[連絡先の詳細]** セクションで、**[編集]** を選択します。

    詳細を編集できない場合は、メール アドレスが Office 365 管理者によって管理されていることを意味します。 メール アドレスの更新を管理者に依頼してください。

    ![連絡先の詳細](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. **[連絡用メール アドレス]** フィールドに、Power BI の更新情報の宛先メール アドレスを入力します。

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell で代替アドレスを指定するには、[Set-AzureADUser](/powershell/module/azuread/set-azureaduser/) コマンドを使用します。

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Azure AD でのメール アドレスの解決

Power BI 用に Azure AD 埋め込みトークンをキャプチャするときは、3 種類のメールを使うことができます。

* ユーザーの Azure AD アカウントに関連付けられている主なメール アドレス

* UserPrincipalName (UPN) メール アドレス

* "*その他のメール アドレス*" 配列属性

Power BI では、次の順序で使用するメール アドレスが選択されます。

1. Azure AD テナントのユーザー オブジェクトにメール属性が存在する場合、Power BI はそのメール属性をメール アドレスに使います。

1. UPN メールが **\*.onmicrosoft.com** ドメイン メール アドレス ("\@" 記号の後の情報) では "*ない*" 場合、Power BI はそのメール属性をメール アドレスに使います。

1. Azure AD ユーザー オブジェクトに "*他のメール アドレス*" 配列属性が存在する場合、そのリストの最初のメール (この属性にはメールのリストが存在する可能性があるため) が使われます。

1. 上記のどの条件も存在しない場合は、UPN アドレスが使われます。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

