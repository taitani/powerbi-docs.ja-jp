---
title: アプリを Azure AD に登録する
description: チュートリアル - データセットにデータをプッシュする - アプリを Azure AD に登録する
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 660f79eab32ae7ade5cea990c6fc152bb9507297
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "34285970"
---
# <a name="step-1-register-an-app-with-azure-ad"></a>手順 1: アプリを Azure AD に登録する
この記事は、チュートリアル「[データセットにデータをプッシュする](walkthrough-push-data.md)」の一部です。

Power BI データセットにデータをプッシュする最初の手順では、Azure AD にアプリを登録します。 Azure AD でアプリを識別する **クライアント ID** を取得するために、この手順を最初に実行する必要があります。 **クライアント ID**がないと、Azure AD はアプリを認証できません。

> **注**: Power BI 用アプリを登録する前に、[Power BI にサインアップする](create-an-azure-active-directory-tenant.md)必要があります。
> 
> 

Azure AD にアプリを登録する手順は次のとおりです。

## <a name="register-an-app-in-azure-ad"></a>Azure AD にアプリを登録する
1. dev.powerbi.com/apps に移動します。
2. **[既存のアカウントでサインインする]** をクリックして、Power BI アカウントにサインインします。
3. **[アプリ名]** を入力します (例: ダッシュボードにデータをプッシュするサンプル)。
4. **[アプリの種類]** で、 **[ネイティブ アプリ]** を選びます。
5. **リダイレクト URL** (**https://login.live.com/oauth20_desktop.srf** など) を入力します。 **ネイティブ クライアント アプリ**の場合、リダイレクト URI は、認証する特定のアプリケーションに関する詳細を **Azure AD** に提供します。 クライアント アプリの標準的な URI は、 https://login.live.com/oauth20_desktop.srf です。
6. **[アクセスする API の選択]** では、 **[すべてのデータセットの読み取りと書き込み]** を選びます。 すべての Power BI アプリのアクセス許可については、「[Power BI のアクセス許可](power-bi-permissions.md)」をご覧ください。
7. **[アプリの登録]** をクリックし、生成された **クライアント ID** を保存します。 **クライアント ID** は、Azure AD 内でアプリを識別します。

**[Power BI にアプリケーションを登録する]** ページは、次のようなものです。

![](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

次の手順では、[認証アクセス トークンを取得する](walkthrough-push-data-get-token.md)方法について説明します。

[次の手順 >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>次の手順
[Power BI にサインアップする](create-an-azure-active-directory-tenant.md)  
[認証アクセス トークンを取得する](walkthrough-push-data-get-token.md)  
[チュートリアル: データセットにデータをプッシュする](walkthrough-push-data.md)  
[アプリケーションを登録する](register-app.md)  
[Power BI REST API の概要](overview-of-power-bi-rest-api.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

