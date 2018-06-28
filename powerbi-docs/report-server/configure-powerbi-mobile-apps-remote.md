---
title: リモートでレポート サーバーへの Power BI iOS モバイル アプリのアクセスを構成する
description: レポート サーバー用にリモートで iOS モバイル アプリを構成する方法を説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722180"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>リモートでレポート サーバーへの Power BI iOS モバイル アプリのアクセスを構成する

この記事では、組織の MDM ツールを使用して、レポート サーバーへの Power BI iOS モバイル アプリのアクセスを構成する方法について説明します。 これを設定するために、IT 管理者は、アプリにプッシュする必要な情報でアプリ構成ポリシーを作成します。 

 レポート サーバー接続が既に構成されているため、Power BI iOS モバイル アプリのユーザーは組織のレポート サーバーにより簡単に接続できます。 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>MDM ツールでアプリ構成ポリシーを作成する 

管理者として、Microsoft Intune でアプリ構成ポリシーを作成するために従う手順を以下に示します。 他の MDM ツールでは、アプリ構成ポリシーの作成の手順とエクスペリエンスが異なる場合があります。 

1. MDM ツールを接続します。 
2. 新しいアプリ構成ポリシーを作成して名前を付けます。 
3. このアプリ構成ポリシーを配布するユーザーを選択します。 
4. キーと値のペアを作成します。 

次の表でペアについて詳しく説明します。

|キー  |種類  |説明  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | 文字列 | レポート サーバー URL </br> 先頭は http/https である必要があります |
| com.microsoft.powerbi.mobile.ServerUsername | 文字列 | (省略可能) </br> サーバーの接続に使用するユーザー名。 </br> 存在しない場合、アプリで、ユーザーに接続用のユーザー名の入力を求めるメッセージが表示されます。| 
| com.microsoft.powerbi.mobile.ServerDisplayName | 文字列 | (省略可能) </br> 既定値は "Report server" です </br> サーバーを表すためにアプリで使用されるフレンドリ名 | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | ブール値 | 既定値は True です </br> "True" に設定すると、モバイル デバイスに既に存在するレポート サーバー定義がオーバーライドされます (既に構成されている既存のサーバーは削除されます)。 </br> また、オーバーライドを True に設定すると、ユーザーはその構成を削除できなくなります。 </br> "False" に設定すると、既存の設定はそのままで、プッシュされた値が追加されます。 </br> モバイル アプリで同じサーバー URL が既に構成されている場合、アプリではその構成がそのまま保持され、ユーザーに対して同じサーバーの再認証が求められることはありません。 |

Intune を使用して構成ポリシーを設定する例を以下に示します。

![Intune の構成設定](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>レポート サーバーに接続しているエンドユーザー

アプリ構成ポリシーが発行された後で、そのポリシーに対して定義されている配布リストに属するデバイスとユーザーが Power BI iOS モバイル アプリを起動する場合のエクスペリエンスは次のとおりです。 

1. レポート サーバーでモバイル アプリが構成されていることを示すメッセージを確認し、**[サインイン]** をタップします。

    ![レポート サーバーにサインインする](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  **[サーバーに接続]** ページには、レポート サーバーの詳細が既に入力されています。 **[接続]** をタップします。

    ![入力されているレポート サーバーの詳細](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. 認証するためのパスワードを入力してから **[サインイン]** をタップします。 

    ![入力されているレポート サーバーの詳細](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

これで、レポート サーバーに格納されている KPI および Power BI レポートを表示して操作できるようになりました。

## <a name="next-steps"></a>次の手順
[管理者の概要](admin-handbook-overview.md)  
[Power BI レポート サーバーのインストール](install-report-server.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

