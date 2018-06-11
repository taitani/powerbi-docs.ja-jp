---
title: オンプレミス データ ゲートウェイのプロキシ設定を構成する
description: オンプレミス データ ゲートウェイのプロキシ設定の構成について説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: ef554d7190709565610336169b4883d71970f822
ms.sourcegitcommit: b25ae650643b0a62f33d7c1741307137b9cec316
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34799558"
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

## <a name="configuring-proxy-settings"></a>プロキシ設定の構成
既定のプロキシ構成は、以下のようになります。

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

既定の構成は、Windows 認証で機能します。 プロキシで別の認証方法を使用している場合は、設定を変更する必要があります。 認証方法が不明な場合は、ネットワーク管理者にお問い合わせください。 基本的なプロキシ認証はお勧めしません。基本的なプロキシ認証を使用しようとすると、適切に構成されていないゲートウェイでプロキシ認証エラーが発生する場合があります。 解決するには、強力なプロキシ認証メカニズムを使用します。

既定の資格情報を使用することに加え、<proxy> 要素を追加して、プロキシ サーバー設定を詳細に定義することができます。 たとえば、bypassonlocal パラメーターを false に設定することで、ローカル リソースの場合でも、オンプレミス データ ゲートウェイで常にプロキシが使用されるように指定できます。 これは、プロキシ ログ ファイルでオンプレミス データ ゲートウェイからのすべての https 要求を追跡する場合のトラブルシューティングに役立ちます。 次のサンプル構成では、すべての要求を IP アドレス 192.168.1.10 の特定のプロキシ経由で行う必要があることを指定します。

    <system.net>
        <defaultProxy useDefaultCredentials="true">
            <proxy  
                autoDetect="false"  
                proxyaddress="http://192.168.1.10:3128"  
                bypassonlocal="false"  
                usesystemdefault="true"
            />  
        </defaultProxy>
    </system.net>

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
3. **オンプレミスのデータ ゲートウェイ構成ウィザード**を開始します。 Windows の [スタート] ボタンを選択し、*[オンプレミス データ ゲートウェイ]* を探します。
4. Power BI にサインインします。
5. 回復キーを使用してゲートウェイを復元します。
   
    これにより、新しいサービス アカウントで格納されているデータ ソースの資格情報の暗号化を解除できるようになります。
    
> [!NOTE]
> サービス コントロール パネルを使用して直接サービス アカウントを変更する場合、ACL は自動的に更新されません。 新しいサービス アカウントが、インストール ファイルとフォルダーへのアクセスを持っていることを確認する必要があります。 ゲートウェイのインストール フォルダーは、C:\Program Files\On-premises data gateway の下にあります。 
> 

## <a name="next-steps"></a>次の手順
[オンプレミス データ ゲートウェイ (個人用モード)](service-gateway-personal-mode.md)
[ファイアウォール情報](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

