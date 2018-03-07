---
title: "Azure AD B2B で外部ゲスト ユーザーに Power BI コンテンツを配布する"
description: "Power BI と Azure Active Directory Business-to-Business(Azure AD B2B) との統合により、組織外のゲスト ユーザーに Power BI コンテンツを安全に配布できるようになりました。"
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
ms.date: 12/07/2017
ms.author: maghan
LocalizationGroup: Administration
ms.openlocfilehash: 09bd3064c7a694355255cb3cca29ade02986d42e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Azure AD B2B で外部ゲスト ユーザーに Power BI コンテンツを配布する

Power BI と Azure Active Directory Business-to-Business(Azure AD B2B) との統合により、内部データに対する制御を引き続き維持しながら、組織外のゲスト ユーザーに Power BI コンテンツを安全に配布できるようになりました。

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> 現在、この機能は Power BI モバイル アプリでは使用できません。 モバイル デバイスでは、ブラウザーで Azure AD B2B を使用して共有されている Power BI コンテンツを表示できます。 

## <a name="invite-guest-users"></a>ゲスト ユーザーを招待する

Power BI テナントにゲスト ユーザーを招待するには、計画的な招待とアドホック招待という 2 つの方法があります。 招待状は、組織に初めて外部ユーザーを招待する場合にのみ必要です。

### <a name="planned-invites"></a>計画的な招待

計画的な招待は、Azure AD の Microsoft Azure Portal または PowerShell を使用して行います。 この方法は、招待する必要のあるユーザーがわかっている場合に使用します。 

**Azure AD Portal でゲスト ユーザーを作成するには、テナント管理者であることが必要です。**

1. [Azure Portal](https://portal.azure.com) に移動し、**[Azure Active Directory]** を選択します。

2. **[ユーザーとグループ]** > **[すべてのユーザー]** > **[新しいゲスト ユーザー]** の順に移動します。

    ![Azure AD Portal - 新しいゲスト ユーザー](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. **メール アドレス**と**個人的なメッセージ**を入力します。

    ![Azure AD Portal - 新しいゲスト ユーザーの招待メッセージ](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. **[招待]** を選びます。

複数のゲスト ユーザーを招待するには、PowerShell を使用します。 詳細については、「[Azure Active Directory B2B コラボレーション コードと PowerShell サンプル](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples)」を参照してください。

ゲスト ユーザーは、受信した招待メール内で **[開始]** を選択する必要があります。 その操作により、ゲスト ユーザーはテナントに追加されます。

![ゲスト ユーザー宛ての招待メール](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>アドホック招待

招待を随時実行するには、アプリを発行するときに該当するアプリのアクセス リストに外部ユーザーを追加します。

![アプリのアクセス リストに追加された外部ユーザー](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

ゲスト ユーザーには、アプリがそのゲスト ユーザーと共有されたことを示す電子メールが届きます。

![ゲスト ユーザーと共有されたアプリに関する電子メール](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

ゲスト ユーザーは、自分の所属する組織の電子メール アドレスでサインインする必要があります。 サインイン後、ゲスト ユーザーは招待を受け入れるよう求められます。 サインイン後、ゲスト ユーザーはアプリのコンテンツにリダイレクトされます。 アプリに戻るには、リンクをブックマークするか、電子メールを保存します。

## <a name="licensing"></a>ライセンス

ゲスト ユーザーは、共有されているアプリを表示するために、適切なライセンスが必要になります。 それを実現するために、次の 3 つのオプションがあります。

### <a name="use-power-bi-premium"></a>Power BI Premium を使用する

Power BI Premium 容量にアプリ ワークスペースを割り当てると、ゲスト ユーザーは Power BI Pro ライセンスなしでアプリを使用できるようになります。 Power BI Premium では、高いリフレッシュ レート、専用の容量、大規模なモデル サイズなど他の機能をアプリで活用することもできます。

![Power BI Premium を使用する](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>ゲスト ユーザーに Power BI Pro ライセンスを割り当てる

テナント内で Power BI Pro ライセンスをゲスト ユーザーに割り当てると、そのターゲット ユーザーはコンテンツを表示できるようになります。

> [!NOTE]
> テナントからの Power BI Pro ライセンスがゲスト ユーザーに適用されるのは、ゲスト ユーザーがテナント内のコンテンツにアクセスする場合にのみです。

![テナントから Pro ライセンスを割り当てる](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>ゲスト ユーザーが独自の Power BI Pro ライセンスを使用する

ゲスト ユーザーは、そのテナント内で Power BI Pro ライセンスに既に割り当てられています。

![ゲスト ユーザーが独自のライセンスを使用する](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="limitations"></a>制限事項

* 外部の B2B ゲストは、コンテンツのみの消費量に制限されます。 外部の B2B ゲストは、アプリ、ダッシュボード、レポートの表示、データのエクスポート、ダッシュボードとレポートの電子メール サブスクリプションの作成ができます。 ワークスペースにアクセスしたり、独自のコンテンツを公開することはできません。
* 現在、この機能は Power BI モバイル アプリでは使用できません。 モバイル デバイスでは、ブラウザーで Azure AD B2B を使用して共有されている Power BI コンテンツを表示できます。
* ソブリン クラウド (政府機関) 内では、Power BI でゲスト ユーザーの使用はサポートされません。

## <a name="next-steps"></a>次の手順

行レベルのセキュリティのしくみなど、詳細については、[ホワイト ペーパー](https://aka.ms/powerbi-b2b-whitepaper)を参照してください。

Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)」を参照してください。