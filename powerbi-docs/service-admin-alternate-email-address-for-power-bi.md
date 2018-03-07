---
title: "代替メール アドレスの使用"
description: "代替メール アドレスの使用"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c97f60e39d68060c8eb3396bac4eb7725dab9c86
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="using-an-alternate-email-address"></a>代替メール アドレスの使用
既定では、Power BI へのサインアップに使用するメール アドレスを使用して、Power BI のアクティビティに関する更新情報をユーザーに送信します。  たとえば、他のユーザーから送信される共有の招待は、このアドレスに配信されます。

最初に Power BI にサインアップしたときに使用したメール アドレスとは別の代替メール アドレスに、これらのメールを配信させることができます。

## <a name="updating-through-office-365-personal-info-page"></a>Office 365 の個人情報ページからの更新
1. [Office 365 の個人情報ページ](https://portal.office.com/account/#personalinfo)に移動します。  プロンプトが表示されたら、Power BI で使用しているメール アドレスとパスワードを使ってサインインします。
2. [連絡先の詳細] セクションにある [編集] リンクをクリックします。  
   
   > [!NOTE]
   > [編集] リンクが表示されない場合、お使いのメール アドレスは Office 365 管理者によって管理されているため、管理者に連絡を取ってメール アドレスを更新する必要があります。
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. [代替メール] フィールドに、Power BI の更新情報の宛先メール アドレスを入力します。

> [!NOTE]
> この設定を変更しても、サービスの更新情報、ニュースレター、およびその他のプロモーション用通信の送信に使用されるメール アドレスは変わりません。  これらのメールは常に、最初に Power BI に登録したときに使用したメール アドレスに送信されます。
> 
> 

## <a name="updating-with-powershell"></a>PowerShell での更新
もう 1 つの方法として、Azure Active Directory の PowerShell を使って代替メール アドレスを更新することもできます。 それには [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) コマンドを使います。

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

詳しくは、「[Azure Active Directory PowerShell Version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)」(Azure Active Directory PowerShell バージョン 2) をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

