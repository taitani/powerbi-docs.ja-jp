---
title: インクルード ファイル
description: インクルード ファイル
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448361"
---
## <a name="single-sign-on"></a>シングル サインオン

Azure SQL の DirectQuery データセットをサービスに発行した後は、Azure Active Directory (Azure AD) OAuth2 を使用して、エンドユーザーのシングル サインオン (SSO) を有効にできます。

SSO を有効にするには、データセットの設定に移動し、 **[データ ソース]** タブを開いて、SSO のチェック ボックスをオンにします。

![Azure SQL DQ の構成ダイアログ ボックス](media/direct-query-sso/sso-dialog.png)

SSO オプションが有効になっている場合、データ ソースを基に作成されたレポートにユーザーがアクセスすると、Power BI によって Azure SQL Database または Data Warehouse へのクエリで、認証済みの Azure AD 資格情報が送信されます。 これにより、Power BI はデータ ソース レベルで構成されているセキュリティ設定を適用できます。

SSO オプションは、このデータ ソースを使うすべてのデータセットで有効になります。 インポートのシナリオに使われる認証方法には影響しません。

> [!Note]
> Azure Multi-Factor Authentication (MFA) はサポートされていません。 Azure SQL DirectQuery で SSO の使用を望むユーザーは、MFA から除外する必要があります。