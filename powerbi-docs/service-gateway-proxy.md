---
title: "オンプレミス データ ゲートウェイのプロキシ設定を構成する"
description: "オンプレミス データ ゲートウェイのプロキシ設定の構成について説明します。"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 6fb6250f8cd82c7057abe3f9cf9792dc733ea4b6
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイのプロキシ設定を構成する
職場ではプロキシを介してインターネットにアクセスしている場合がありますが、 これは、オンプレミス データ ゲートウェイがサービスに接続できない原因となることがあります。

## <a name="does-your-network-use-a-proxy"></a>ネットワークでプロキシが使用されているかどうかを確認する
ネットワークでプロキシが使用されているかどうかを確認する方法については、superuser.com の次の投稿をご覧ください。

[How do I know what proxy server I'm using? (使用しているプロキシ サーバーを確認する方法)(SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>構成ファイルの場所と既定の構成
プロキシ情報は、.NET 構成ファイル内で構成されます。 構成ファイルの場所とファイル名は、使用しているゲートウェイによって異なります。

### <a name="on-premises-data-gateway"></a>オンプレミス データ ゲートウェイ
オンプレミス データ ゲートウェイに関連する主要な構成ファイルは 2 つあります。

**構成**

1 つは、実際にゲートウェイを構成する構成画面用のファイルです。 ゲートウェイの構成に問題がある場合は、このファイルを確認します。

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows サービス**

2 つ目は、実際に Power BI サービスと対話して要求を処理する Windows サービス用のファイルです。

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
> [!NOTE]
> Power BI には、**オンプレミス データ ゲートウェイ (個人用モード)** と呼ばれる、新しいバージョンの Personal Gateway があります。 この記事のこのセクションでは、**Power BI Gateway - Personal** と呼ばれる以前のバージョンのパーソナル ゲートウェイについて説明します。このゲートウェイは、2017 年 7 月 31 日に廃止され、以降動作しなくなります。 新しいバージョンのインストール方法など、新しいパーソナル ゲートウェイの詳細については、「[**オンプレミス データ ゲートウェイ (個人用モード)**](service-gateway-personal-mode.md)」を参照してください。
> 
> 

パーソナル ゲートウェイをインストールする方法は 2 種類あります。 1 つは Windows サービス (管理者) としてインストールする方法で、もう 1 つはユーザー モード アプリケーションとしてインストールする方法です。 これはインストール時に決定されます。 構成ファイルの場所はゲートウェイのインストール方法に応じて異なるため、 2 つの場所の両方を確認してください。

**構成**

1 つは、実際にゲートウェイを構成する構成画面用のファイルです。 ゲートウェイの構成に問題がある場合は、このファイルを確認します。

*Windows サービス*の場合、次の場所になります。

    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\GWConfig.exe.config
    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

*ユーザー モード アプリケーション*の場合、次の場所になります。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\GWConfig.exe.config
    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

**Windows サービス**

2 つ目は、実際に Power BI サービスと対話して要求を処理する Windows サービス用のファイルです。

*Windows サービス*の場合、次の場所になります。

    C:\Program Files\Power BI Personal Gateway\1.0\Gateway\diawp.exe.config

*ユーザー モード アプリケーション*の場合、次の場所になります。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Gateway\diawp.exe.config

## <a name="configuring-proxy-settings"></a>プロキシ設定の構成
既定のプロキシ構成は、以下のようになります。

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

既定の構成は、Windows 認証で機能します。 プロキシで別の認証方法を使用している場合は、設定を変更する必要があります。 認証方法が不明な場合は、ネットワーク管理者にお問い合わせください。

.NET 構成ファイルのプロキシ要素の構成について詳しくは、「[defaultProxy 要素 (ネットワーク設定)](https://msdn.microsoft.com/library/kd3cf2ex.aspx)」をご覧ください。

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>ドメイン ユーザーへのゲートウェイ サービス アカウントの変更
既定の資格情報を使用するようにプロキシ設定を構成すると、前に説明したように、プロキシで認証の問題が発生することがあります。 これは、既定のサービス アカウントがサービス SID であり、認証済みのドメイン ユーザーではないためです。 ゲートウェイのサービス アカウントを変更して、プロキシで適切に認証が行われるようにすることができます。

> [!NOTE]
> パスワードをリセットする必要がないように、管理されたサービス アカウントを使用することをおすすめします。 Active Directory 内で[管理されたサービス アカウント](https://technet.microsoft.com/library/dd548356.aspx)を作成する方法を参照してください。
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>オンプレミスのデータ ゲートウェイ サービス アカウントを変更する
1. **オンプレミスのデータ ゲートウェイ サービス**の Windows サービス アカウントを変更します。
   
    このサービスの既定のアカウントは *NT SERVICE\PBIEgwService* です。 これを Active Directory ドメイン内のドメイン ユーザー アカウントに変更します。 または、パスワードを変更する必要がないように、管理されたサービス アカウントを使用します。
   
    Windows サービスのプロパティ内の **[ログオン]** タブでアカウントを変更します。
2. **オンプレミスのデータ ゲートウェイ サービス**を再起動します。
   
    管理コマンド プロンプトから、次のコマンドを実行します。
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. **オンプレミスのデータ ゲートウェイ構成ウィザード**を開始します。 Windows の [スタート] ボタンを選択し、[*オンプレミス データ ゲートウェイ*] を探します。
4. Power BI にサインインします。
5. 回復キーを使用してゲートウェイを復元します。
   
    これにより、新しいサービス アカウントで格納されているデータ ソースの資格情報の暗号化を解除できるようになります。

## <a name="next-steps"></a>次の手順
[オンプレミス データ ゲートウェイ (個人用モード)](service-gateway-personal-mode.md)
[ファイアウォール情報](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

