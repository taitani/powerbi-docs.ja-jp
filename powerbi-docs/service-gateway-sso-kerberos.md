---
title: オンプレミス データ ソースへのシングル サインオン (SSO) に Kerberos を使用する
description: Power BI からオンプレミス データ ソースへの SSO を有効にするようにゲートウェイの Kerberos を構成します
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 7256de8dd36c25af9959e7103186666d65123360
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295261"
---
# <a name="use-kerberos-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Power BI からオンプレミス データ ソースへの SSO (シングル サインオン) に Kerberos を使用する

[Kerberos の制約付き委任](/windows-server/security/kerberos/kerberos-constrained-delegation-overview)を使用して、シームレスなシングル サインオン接続を有効にします。 SSO を有効にすると、Power BI レポートおよびダッシュボードはオンプレミスのソースからデータを簡単に更新できるようになります。

## <a name="supported-data-sources"></a>サポートされているデータ ソース

現在サポートされているデータ ソースは次のとおりです。

* SQL Server
* SAP HANA
* SAP BW
* Teradata
* Spark
* Impala

[Security Assertion Markup Language (SAML)](service-gateway-sso-saml.md) を使用した SAP HANA もサポートされています。

### <a name="sap-hana"></a>SAP HANA

SAP HANA で SSO を有効にするには、次の手順に従います。

* SAP HANA サーバーが必要な最小バージョンを実行していることを確認します。これは、SAP Hana サーバー プラットフォームのレベルによって異なります。
  * [HANA 2 SPS 01 改訂 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 改訂 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 改訂 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* ゲートウェイ マシンに、SAP の最新の HANA ODBC ドライバーをインストールする。  最小バージョンは 2017 年 8 月の HANA ODBC バージョン 2.00.020.00 です。

Kerberos を使って SAP HANA に対するシングル サインオンのセットアップと構成を行う方法について詳しくは、SAP HANA セキュリティ ガイドのトピック「[Single Sign-on Using Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/en-US/1885fad82df943c2a1974f5da0eed66d.html)」(Kerberos を用いたシングル サインオン) とそのページからのリンク (特に SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory) をご覧ください。

## <a name="preparing-for-kerberos-constrained-delegation"></a>Kerberos の制約付き委任のための準備

Kerberos の制約付き委任が正しく機能するためには、*サービス プリンシパル名* (SPN) やサービス アカウントでの委任の設定など、いくつかのことを構成する必要があります。

### <a name="prerequisite-1-install--configure-the-on-premises-data-gateway"></a>前提条件 1:オンプレミス データ ゲートウェイをインストールして構成する

オンプレミス データ ゲートウェイのこのリリースでは、インプレース アップグレードだけでなく既存のゲートウェイの引き継ぎの設定がサポートされています。

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>前提条件 2:ゲートウェイの Windows サービスをドメイン アカウントとして実行する

標準のインストールでは、ゲートウェイは、次の図のようにコンピューター ローカル サービス アカウントとして実行されます (具体的には、*NT Service\PBIEgwService*)。

![サービス アカウント](media/service-gateway-sso-kerberos/service-account.png)

Azure AD が既に (Azure AD DirSync/Connect を使って) ローカルの Active Directory と同期されている場合を除き、**Kerberos の制約付き委任**を有効にするには、ゲートウェイをドメイン アカウントとして実行する必要があります。 アカウントをドメイン アカウントに切り替える必要がある場合は、この記事で後述する「[ゲートウェイをドメイン アカウントに切り替える](#switching-the-gateway-to-a-domain-account)」を参照してください。

> [!NOTE]
> Azure AD DirSync/Connect が構成されていて、ユーザー アカウントが同期されている場合、ゲートウェイは実行時にローカル AD 参照を実行する必要はなく、ゲートウェイ サービスに対して (ドメイン アカウントを要求する代わりに) ローカル サービス SID を使うことができます。 この記事で説明する Kerberos の制約付き委任の構成手順は、その構成と同じです (ドメイン アカウントではなく、Active Directory のゲートウェイのコンピューター オブジェクトに単に適用されます)。

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>前提条件 3:SPN (SetSPN) および Kerberos 制約付き委任の設定を構成するためのドメイン管理者権限がある

ドメイン管理者権限を要求せず、ドメイン管理者が SPN および Kerberos 委任を構成する権限を一時的または永続的に他のユーザーに許可することは技術的には可能ですが、そのような方法はお勧めできません。 次のセクションで、**前提条件 3** に必要な構成手順を詳しく説明します。

## <a name="configuring-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>ゲートウェイとデータ ソースに対して Kerberos の制約付き委任を構成する

システムを正しく構成するには、次の 2 つのことを構成または検証する必要があります。

1. 必要に応じて、ゲートウェイ サービスのドメイン アカウントに SPN を構成します。

2. ゲートウェイ サービスのドメイン アカウントに委任設定を構成します。

これら 2 つの構成手順はドメイン管理者が実行する必要があることに注意してください。

以下のセクションでは、これらの手順を順番に説明します。

### <a name="configure-an-spn-for-the-gateway-service-account"></a>ゲートウェイ サービス アカウントに SPN を構成する

最初に、以下の手順に従って、ゲートウェイ サービス アカウントとして使われるドメイン アカウントに SPN が既に作成されているかどうかを調べます。

1. ドメイン管理者として **[Active Directory ユーザーとコンピューター]** を起動します。

2. ドメインを右クリックし、**[検索]** を選んで、ゲートウェイ サービス アカウントのアカウント名を入力します

3. 検索結果で、ゲートウェイ サービス アカウントを右クリックして、**[プロパティ]** を選びます。

4. **[委任]** タブが **[プロパティ]** ダイアログに表示される場合、SPN は既に作成されており、委任設定の構成に関する次のサブセクションに進むことができます。

    **[委任]** タブが **[プロパティ]** ダイアログにない場合は、そのアカウントに SPN を手動で作成でき、作成すると **[委任]** タブが追加されます (これが、委任設定を構成する最も簡単な方法です)。 SPN の作成は、Windows に付属する [setspn ツール](https://technet.microsoft.com/library/cc731241.aspx)を使って行うことができます (SPN を作成するにはドメイン管理者権限が必要です)。

    たとえば、ゲートウェイ サービス アカウントが "PBIEgwTest\GatewaySvc" で、ゲートウェイ サービスを実行しているコンピューターの名前が **Machine1** であるとします。 この例のコンピューターにゲートウェイ サービス アカウントの SPN を設定するには、次のコマンドを実行します。

    ![SPN を設定する](media/service-gateway-sso-kerberos/set-spn.png)

    このステップが完了したら、委任設定の構成に進むことができます。

### <a name="configure-delegation-settings-on-the-gateway-service-account"></a>ゲートウェイ サービス アカウントで委任設定を構成する

2 番目の構成要件は、ゲートウェイ サービス アカウントでの委任の設定です。 この手順は複数のツールを使って実行できます。 この記事では **[Active Directory ユーザーとコンピューター]** を使います。これは、ディレクトリ内の情報の管理と発行に使うことができる Microsoft 管理コンソール (MMC) のスナップインです。 既定ではドメイン コントローラーで使用できます。 他のコンピューターでの **Windows 機能**の構成により有効にすることもできます。

プロトコル遷移のある **Kerberos の制約付き委任**を構成する必要があります。 制約付き委任では、委任先のサービスを明示的に指定する必要があります。 たとえば、SQL Server または SAP HANA サーバーは、ゲートウェイ サービス アカウントからの委任呼び出しを受け入れます。

このセクションでは、基になるデータ ソース (SQL Server、SAP HANA、Teradata、Spark など) に対して SPN を既に構成してあるものとします。 これらのデータ ソース サーバーの SPN を構成する方法については、それぞれのデータベース サーバーの技術ドキュメントを参照してください。 [*アプリで必要な SPN*](https://blogs.msdn.microsoft.com/psssql/2010/06/23/my-kerberos-checklist/) について説明されているブログ投稿もご覧ください。

次の手順では、ゲートウェイ コンピューターと、SQL Server を実行しているデータベース サーバーの 2 つのコンピューターで構成されるオンプレミス環境を想定しています。 また、この例では次の設定と名前を使用します。

* ゲートウェイ コンピューターの名前:**PBIEgwTestGW**
* ゲートウェイ サービス アカウント:**PBIEgwTest\GatewaySvc** (アカウントの表示名:Gateway Connector)
* SQL Server データ ソースのコンピューター名:**PBIEgwTestSQL**
* SQL Server データ ソースのサービス アカウント:**PBIEgwTest\SQLService**

これらの例の名前と設定を使うと、構成手順は次のようになります。

1. ドメイン管理者権限で、**[Active Directory ユーザーとコンピューター]** を起動します。

2. ゲートウェイのサービス アカウント (**PBIEgwTest\GatewaySvc**) を右クリックし、**[プロパティ]** を選びます。

3. **[委任]** タブを選びます。

4. **[指定されたサービスへの委任でのみこのコンピューターを信頼する]** をオンにします。

5. **[任意の認証プロトコルを使う]** をオンにします。

6. **[このアカウントが委任された資格情報を提示できるサービス]** で **[追加]** を選びます。

7. 新しいダイアログ ボックスで、**[ユーザーまたはコンピューター]** を選びます。

8. SQL Server データベース サービスのサービス アカウント (**PBIEgwTest\SQLService**) を入力し、**[OK]** を選びます。

9. データベース サーバー用に作成した SPN を選びます。 この例では、SPN は **MSSQLSvc** で始まります。 データベース サービスに FQDN と NetBIOS 両方の SPN を追加した場合は、両方とも選びます。 1 つだけしか表示されない場合があります。

10. **[OK]** を選択します。 リストに SPN が表示されます。

11. 必要に応じて、**[展開済み]** を選んで FQDN SPN と NetBIOS SPN を両方表示できます。

12. **[展開済み]** をオンにした場合、ダイアログ ボックスの表示は次のようになります。 **[OK]** を選択します。

    ![ゲートウェイ コネクタのプロパティ](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

最後に、ゲートウェイ サービス (この例では **PBIEgwTestGW**) を実行しているコンピューターで、ゲートウェイ サービス アカウントにローカル ポリシー "認証後にクライアントを偽装" を付与する必要があります。 これは、ローカル グループ ポリシー エディター (**gpedit**) で実行/確認できます。

1. ゲートウェイ コンピューターで、*gpedit.msc* を実行します。

1. **[ローカル コンピューター ポリシー] > [コンピューターの構成] > [Windows の設定] > [セキュリティの設定] > [ローカル ポリシー] > [ユーザー権利の割り当て]** の順に移動します (次の図を参照)。

    ![ユーザー権利の割り当て](media/service-gateway-sso-kerberos/user-rights-assignment.png)

1. **[ユーザー権利の割り当て]** のポリシーの一覧で、**[認証後にクライアントを偽装]** を選びます。

    ![クライアントの偽装](media/service-gateway-sso-kerberos/impersonate-client.png)

    **[認証後にクライアントを偽装]** を右クリックして **[プロパティ]** を開き、アカウントの一覧を確認します。 ゲートウェイ サービス アカウント (**PBIEgwTest\GatewaySvc**) が含まれている必要があります。

1. **[ユーザー権利の割り当て]** のポリシーの一覧から、**[オペレーティング システムの一部として機能 (SeTcbPrivilege)]** を選びます。 アカウントの一覧にゲートウェイ サービス アカウントが含まれることも確認します。

1. **オンプレミス データ ゲートウェイ** サービス プロセスを再起動します。

SAP HANA を使用している場合は、次のパフォーマンスが若干向上させるために次の追加手順を実行することをお勧めします。

1. ゲートウェイのインストール ディレクトリで、次の構成ファイルを見つけて開きます:*Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*。

1. *FullDomainResolutionEnabled* プロパティを見つけて、その値を *True* に変更します。

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

## <a name="running-a-power-bi-report"></a>Power BI レポートを実行する

この記事でこれまでに説明したすべての構成手順が完了すると、Power BI の **[Manage Gateway]\(ゲートウェイの管理\)** ページを使ってデータ ソースを構成することができます。 その後、**[詳細設定]** で SSO を有効にし、そのデータ ソースに対するレポートとデータセットのバインドを発行します。

![詳細設定](media/service-gateway-sso-kerberos/advanced-settings.png)

この構成は、ほとんどの場合に機能します。 ただし、Kerberos については、環境に応じて構成が異なる可能性があります。 レポートがまだ読み込まれない場合は、ドメイン管理者に連絡してさらに詳しく調査する必要があります。

## <a name="switching-the-gateway-to-a-domain-account"></a>ゲートウェイをドメイン アカウントに切り替える

この記事の前半で、**オンプレミス データ ゲートウェイ**のユーザー インターフェイスを使って、ゲートウェイをローカル サービス アカウントからドメイン アカウントとして実行するように切り替えることを説明しました。 そのために必要な手順を以下に示します。

1. **[オンプレミスのデータ ゲートウェイ]** 構成ツールを起動します。

   ![ゲートウェイ デスクトップ アプリ](media/service-gateway-sso-kerberos/gateway-desktop-app.png)

2. メイン ページの **[サインイン]** ボタンを選び、Power BI アカウントでサインインします。

3. サインインが完了した後、**[サービスの設定]** タブを選びます。

4. 次の図に示すように、**[アカウントの変更]** を選んでガイド付きチュートリアルを開始します。

   ![アカウントの変更](media/service-gateway-sso-kerberos/change-account.png)

## <a name="configuring-sap-bw-for-sso"></a>SAP BW に対する SSO の構成

Kerberos がゲートウェイと連携するしくみを理解できたので、SAP Business Warehouse (SAP BW) に対して SSO を構成できます。 次の手順は、この記事で前述したように、[Kerberos の制約付き委任の準備](#preparing-for-kerberos-constrained-delegation)が既にできていることを前提としています。

このガイドは、可能な限り包括的になるように書かれています。 一部の手順を既に完了している場合は、それをスキップできます。たとえば、BW サーバーのサービス ユーザーを既に作成して SPN をマップしてある場合や、gsskrb5 ライブラリを既にインストールしてある場合です。

### <a name="setup-gsskrb5-on-client-machines-and-the-bw-server"></a>クライアント コンピューターと BW サーバーに gsskrb5 をセットアップする

ゲートウェイを介して SSO 接続を完了するには、クライアントとサーバーの両方で gsskrb5 が使用されている必要があります。 Common Crypto Library (sapcrypto) は現在サポートされていません。

1. [SAP Note 2115486](https://launchpad.support.sap.com/) から gsskrb5/gx64krb5 をダウンロードします (SAP S-User が必要)。 バージョン 1.0.11.x 以降の gsskrb5.dll および gx64krb5.dll があることを確認します。

1. ゲートウェイ インスタンスによって (また、SAP GUI/ログオンを使用して SSO 接続をテストする場合は、SAP GUI によっても) アクセスできるゲートウェイ コンピューター上の場所に、ライブラリを配置します。

1. BW サーバーによってアクセスできる BW サーバー コンピューター上の場所に、別のコピーを配置します。

1. クライアント コンピューターとサーバー コンピューター上で、SNC\_LIB 環境変数と SNC\_LIB\_64 環境変数を、それぞれ gsskrb5.dll と gx64krb5.dll の場所を指すように設定します。

### <a name="create-a-bw-service-user-and-enable-snc-communication-using-gsskrb5-on-the-bw-server"></a>BW サービス ユーザーを作成し、BW サーバー上の gsskrb5 を使用した SNC 通信を有効にする

既に実行したゲートウェイ構成に加えて、SAP BW 固有のいくつかの追加手順があります。 このドキュメントの「[**ゲートウェイ サービス アカウントで委任設定を構成する**](#configure-delegation-settings-on-the-gateway-service-account)」セクションは、基になるデータ ソースに対して SPN を既に構成していることを前提としています。 SAP BW に対してこの構成を実行するには、次の手順に従います。

1. Active Directory ドメイン コントローラー サーバーで、Active Directory 環境内の BW アプリケーション サーバーに対してサービス ユーザー (最初は単純な Active Directory ユーザー) を作成します。 その後、このユーザーに SPN を割り当てます。

    SAP では SAP/ で SPN を始めることが推奨されていますが、HTTP/ などの他のプレフィックスも使用できるはずです。 SAP/ の後に続く文字は開発者次第です。1 つのオプションとしては、BW サーバーのサービス ユーザーのユーザー名を使用します。 たとえば、サービス ユーザーとして BWServiceUser@\<ドメイン\> を作成した場合、SPN SAP/BWServiceUser を使用できます。 SPN のマッピングを設定する方法の 1 つは、setspn コマンドです。 たとえば、先ほど作成したサービス ユーザーの SPN を設定するには、ドメイン コントローラー コンピューターでコマンド ウィンドウからコマンド: `setspn -s SAP/ BWServiceUser DOMAIN\ BWServiceUser` を実行します。 詳しくは、SAP BW のドキュメントをご覧ください。

1. サービス ユーザーに、BW アプリケーション サーバーへのアクセス権を付与します。

    1. BW サーバー コンピューターで、BW サーバーのローカル管理者グループにサービス ユーザーを追加します。[コンピューターの管理] プ ログラムを開き、サーバーのローカル管理者グループをダブルクリックします。

        ![コンピューターの管理](media/service-gateway-sso-kerberos/computer-management.png)

    1. ローカル管理者グループをダブルクリックし、**[追加]** を選んで、グループに BW サービス ユーザーを追加します。 **[名前の確認]** ボタンを使用して、名前を正しく入力したことを確認します。 **[OK]** を選択します。

1. BW サーバーのサービス ユーザーを、BW サーバー コンピューターで BW サーバー サービスを開始したユーザーとして設定します。

    1. [ファイル名を指定して実行] プログラムを開き、「Services.msc」と入力します。 BW アプリケーション サーバー インスタンスに対応するサービスを探します。 そのサービスを右クリックし、**[プロパティ]** を選びます。

        ![サーバーのプロパティ](media/service-gateway-sso-kerberos/server-properties.png)

    1. **[ログオン]** タブに切り替えて、上記で指定したとおり、ユーザーを BW サービス ユーザーに変更します。 ユーザーのパスワードを入力し、**[OK]** を選びます。

1. SAP GUI/ログオンでサーバーにサインインし、RZ10 トランザクションを使用して次のプロファイル パラメーターを設定します。

    1. snc/identity/as プロファイル パラメーターを p:\<作成した BW サービス ユーザー\> (p:BWServiceUser@MYDOMAIN.COM など) に設定します。 サービス ユーザーの UPN の前に付いている p: に注意してください。SNC ライブラリとして Common Crypto Lib を使用するときのような、p:CN= ではありません。

    1. snc/gssapi\_lib プロファイル パラメーターを \<サーバー コンピューター上の gsskrb5.dll/gx64krb5.dll へのパス (使用するライブラリは OS のビット数によって異なります)\> に設定します。 BW アプリケーション サーバーがアクセスできる場所にライブラリを配置してください。

    1. また、次の追加のプロファイル パラメーターを設定し、ニーズに合わせて値を変更します。 最後の 5 つのオプションでは、クライアントは SNC を構成することなく、SAP ログオン/GUI を使用して BW サーバーに接続することができます。

        | **設定** | **値** |
        | --- | --- |
        | snc/data\_protection/max | 3 |
        | snc/data\_protection/min | 1 |
        | snc/data\_protection/use | 9 |
        | snc/accept\_insecure\_cpic | 1 |
        | snc/accept\_insecure\_gui | 1 |
        | snc/accept\_insecure\_r3int\_rfc | 1 |
        | snc/accept\_insecure\_rfc | 1 |
        | snc/permit\_insecure\_start | 1 |

    1. プロパティ snc/enable を 1 に設定します。

1. これらのプロファイル パラメーターを設定してから、サーバー コンピューターで SAP 管理コンソールを開き、BW インスタンスを再起動します。 サーバーが起動しない場合は、プロファイル パラメーターを正しく設定したことを再確認します。 プロファイル パラメーターの設定の詳細については、[SAP のドキュメント](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm)を参照してください。 また、問題が発生した場合、このセクションで後述するトラブルシューティング情報も参照できます。

### <a name="map-a-bw-user-to-an-active-directory-user"></a>BW ユーザーを Active Directory ユーザーにマップする

Active Directory ユーザーを SAP BW アプリケーション サーバー ユーザーにマップし、SAP GUI/ログオンで SSO 接続をテストします。

1. SAP GUI/ログオンを使用して、BW サーバーにサインインします。 トランザクション SU01 を実行します。

1. **[ユーザー]** で、SSO 接続を有効にする対象の BW ユーザーを入力します (上記のスクリーンショットでは、BIUSER のアクセス許可を設定しています)。 SAP ログオン ウィンドウの左上隅近くにある**編集**アイコン (ペンのイメージ) を選びます。

    ![ユーザーの管理](media/service-gateway-sso-kerberos/user-maintenance.png)

1. **[SNC]** タブを選びます。SNC 名の入力ボックスに、「p:\<Active Directory ユーザー\>@\<ドメイン\>」と入力します。 Active Directory ユーザーの UPN の前に指定する必須の p: に注意してください。 指定した Active Directory ユーザーは、BW アプリケーション サーバーへの SSO アクセスを有効にする対象の個人または組織に属している必要があります。 たとえば、ユーザー [testuser@TESTDOMAIN.COM](mailto:testuser@TESTDOMAIN.COM) に対して SSO アクセスを有効にする場合、「p:testuser@TESTDOMAIN.COM」と入力します。

    ![ユーザーを管理する](media/service-gateway-sso-kerberos/maintain-users.png)

1. 保存アイコン (画面の左上隅近くにあるフロッピー ディスク) を選びます。

### <a name="test-sign-in-using-sso"></a>SSO を使用したサインインをテストする

SSO 経由で SAP ログオン/SAP GUI を使用して、先ほど SSO アクセスを有効にした対象の Active Directory ユーザーとして、サーバーにサインインできることを確認します。

1. *先ほど SSO アクセスを有効にした対象の Active Directory ユーザーとして*、SAP ログオンがインストールされているコンピューターにサインインし、SAP GUI/ログオンを起動します。 新しい接続を作成します。

1. **[Create New System Entry]/(新しいシステム エントリの作成/)** ウィンドウで **[User Specified System]/(ユーザー指定のシステム/)** を選び、**[次へ]** を選びます。

    ![新しいシステム エントリ](media/service-gateway-sso-kerberos/new-system-entry.png)

1. 次のページで、アプリケーション サーバー、インスタンス番号、システムの ID などの該当する詳細情報を入力し、**[完了]** を選びます。

1. 新しい接続を右クリックし、**[プロパティ]** を選びます。 **[ネットワーク]** タブを選びます。**[SNC Name]\(SNC 名\)** ウィンドウで、「p:\<BW サービス ユーザーの UPN\>」 (例: p:BWServiceUser@MYDOMAIN.COM) と入力して、**[OK]** を選択します。

    ![システム エントリ プロパティ](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. 先ほど作成した接続をダブルクリックして、BW サーバーへの SSO 接続を試みます。 この接続に成功した場合は、次の手順に進みます。 そうでない場合は、このドキュメントの前述の手順を参照して、接続が正常に完了したことを確認するか、または次のトラブルシューティングのセクションを参照します。 このコンテキストで SSO を使用して BW サーバーに接続できない場合は、ゲートウェイのコンテキストで SSO を使用して BW サーバーに接続することはできません。

### <a name="troubleshoot-installation-and-connections"></a>インストールと接続のトラブルシューティングを行う

問題が発生した場合は、以下の手順に従って、SAP GUI/ログオンから gsskrb5 インストールと SSO 接続のトラブルシューティングを行います。

1. サーバー ログ (サーバー コンピューター上の …work\dev\_w0) を参照すると、gsskrb5 のセットアップ手順の実行時に発生したエラーのトラブルシューティングを行うことができます。特に、プロファイル パラメーターが変更された後に BW サーバーが起動しない場合に役立ちます。

1. "ログオンに失敗した" ために BW サービスを開始できない場合、BW "開始" ユーザーを設定するときに不正なパスワードを指定した可能性があります。 BW サービス ユーザーとして Active Directory 環境内のコンピューターにログインして、パスワードを確認します。

1. SQL 資格情報に関するエラーが発生してサーバーが起動できない場合は、BW データベースへのサービス ユーザー アクセス権が付与されていることを確認します。

1. "(GSS-API) specified target is unknown or unreachable (指定されたターゲットが不明であるか、または到達不能)": これは通常、不正な SNC 名が指定されていることを意味します。 サービス ユーザーの UPN 以外には、"p:CN =" やクライアント アプリケーション内の何らかの項目ではなく、必ず "P:" だけを使用してください。

1. "(GSS-API) An invalid name was supplied (無効な名前が指定されました)": サーバーの SNC ID プロファイル パラメーターの値に "p:" が含まれることを確認してください。

1. "(SNC エラー) the specified module could not be found (指定したモジュールが見つかりませんでした)": これは通常、アクセスするのに高度な特権 (管理者権限) を必要とする場所に gsskrb5.dll/gx64krb5.dll を配置したことが原因で発生します。

### <a name="add-registry-entries-to-the-gateway-machine"></a>ゲートウェイ コンピューターにレジストリ エントリを追加する

ゲートウェイがインストールされているコンピューターのレジストリに、必要なレジストリ エントリを追加します。

1. コマンド ウィンドウで、次のコマンドを実行します。

    1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

    1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="set-configuration-parameters-on-the-gateway-machine"></a>ゲートウェイ コンピューターで構成パラメーターを設定する

ユーザーが Azure AD ユーザーとして Power BI サービスにサインインできるように Azure AD DirSync を構成してあるかどうかにより、構成パラメーターの設定には 2 つのオプションがあります。

Azure AD DirSync を構成してある場合は、以下の手順のようにします。

1. メインのゲートウェイ構成ファイル *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll* を開きます。 このファイルは、既定では *C:\Program Files\On-premises data gateway* に格納されています。

1. **FullDomainResolutionEnabled** プロパティが True に設定されていて、**SapHanaSsoRemoveDomainEnabled** が False に設定されていることを確認します。

1. 構成ファイルを保存します。

1. タスク マネージャーの [サービス] タブ (右クリックして [再起動] をクリック) を使用して、ゲートウェイ サービスを再起動します

    ![ゲートウェイを再起動する](media/service-gateway-sso-kerberos/restart-gateway.png)

Azure AD DirSync を構成していない場合は、**Azure AD ユーザーにマップするすべての Power BI サービス ユーザー**に対し、以下の手順のようにします。 次の手順では、BW にサインインするアクセス許可を持つ Active Directory ユーザーに、Power BI サービスのユーザーを手動でリンクします。

1. メインのゲートウェイ構成ファイル Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll を開きます。 このファイルは、既定では C:\Program Files\On-premises data gateway に格納されています。

1. **ADUserNameLookupProperty** を msDS-cloudExtensionAttribute1 に、**ADUserNameReplacementProperty** を SAMAccountName に設定します。 構成ファイルを保存します。

1. タスク マネージャーの **[サービス]** タブ (右クリックして **[再起動]** をクリック) を使用して、ゲートウェイ サービスを再起動します。

    ![ゲートウェイを再起動する](media/service-gateway-sso-kerberos/restart-gateway.png)

1. BW ユーザーにマップした Active Directory ユーザーの msDS-cloudExtensionAttribute1 プロパティを、Kerberos SSO を有効にする対象の Power BI サービス ユーザーに設定します。 msDS-cloudExtensionAttribute1 プロパティを設定する方法の 1 つは、[Active Directory ユーザーとコンピューター] MMC スナップインを使用することです (他の方法を使用こともできます)。

    1. 管理者ユーザーとしてドメイン コントローラー コンピューターにサインインします。

    1. スナップイン ウィンドウで**ユーザー** フォルダーを開き、BW ユーザーにマップした Active Directory ユーザーをダブルクリックします。

    1. **[属性エディター]** タブを選びます。

        このタブが表示されない場合は、このタブを有効にする手順を確認するか、または別の方法を使用して msDS cloudExtensionAttribute1 プロパティを設定する必要があります。 いずれかの属性を選び、'm' キーを押して、Active Directory の先頭が 'm' のプロパティに移動します。 msDS-cloudExtensionAttribute1 プロパティを見つけてダブルクリックします。 その値を、Power BI サービスへのサインインに使用するユーザー名 (YourUser@YourDomain の形式) に設定します。

    1. **[OK]** を選択します。

        ![属性を編集する](media/service-gateway-sso-kerberos/edit-attribute.png)

    1. **[適用]** を選びます。 [値] 列に正しい値が設定されていることを確認します。

### <a name="add-a-new-bw-application-server-data-source-to-the-power-bi-service"></a>Power BI サービスに新しい BW アプリケーション サーバー データ ソースを追加する

ゲートウェイに BW データ ソースを追加します。この記事で前述した[レポートの実行](#running-a-power-bi-report)に関する手順に従ってください。

1. データ ソース構成ウィンドウで、Power BI Desktop から BW サーバーにサインインする際と同様に、アプリケーション サーバーの **[ホスト名]**、**[システム番号]**、および **[クライアント ID]** を入力します。 **[認証方法]** で、**[Windows]** を選びます。

1. **[SNC パートナー名]** フィールドに、「p:\<BW サービス ユーザーにマップした SPN\>」と入力します。 たとえば、SPN が SAP/BWServiceUser@MYDOMAIN.COM の場合は、**[SNC パートナー名]** フィールドに「p:SAP/BWServiceUser@MYDOMAIN.COM」と入力する必要があります。

1. SNC ライブラリでは、SNC\_LIB または SNC\_LIB\_64 を選びます。

1. **[ユーザー名]** と **[パスワード]** は、SSO を使用して BW サーバーにサインインする権限のある Active Directory ユーザー (SU01 トランザクションを使用して BW ユーザーにマップされている Active Directory ユーザー) のユーザー名とパスワードにする必要があります。 これらの資格情報は、**[Use SSO via Kerberos for DirectQuery queries]/(DirectQuery クエリに Kerberos 経由で SSO を使用する/)** ボックスがオンになって*いない*場合にのみ使用されます。

1. **[DirectQuery クエリには Kerberos 経由で SSO を使用します]** ボックスをオンにして、**[適用]** を選択します。 テスト接続が成功しなかった場合は、前のセットアップおよび構成手順が正常に完了したことを確認します。

    ゲートウェイは常に入力された資格情報を使用してサーバーへのテスト接続を確立し、インポート ベースのレポートのスケジュールされた更新を行います。 **[DirectQuery クエリには Kerberos 経由で SSO を使用します]** がオンになっていて、ユーザーが直接クエリ ベースのレポートまたはデータセットにアクセスしている場合にのみ、ゲートウェイは SSO 接続の確立を試みます。

### <a name="test-your-setup"></a>セットアップをテストする

Power BI Desktop から Power BI サービスに DirectQuery レポートを発行して、セットアップをテストします。 Azure AD ユーザーとして、または Azure AD ユーザーの msDS-cloudExtensionAttribute1 プロパティにマップしたユーザーとして、Power BI サービスにサインインしていることを確認します。 セットアップが正常に完了したら、Power BI サービスで発行済みのデータセットに基づいてレポートを作成し、レポート内のビジュアルを通してデータを取り込むことができます。

### <a name="troubleshooting-gateway-connectivity-issues"></a>ゲートウェイ接続の問題のトラブルシューティング

1. ゲートウェイのログを確認します。 ゲートウェイ構成アプリケーションを開き、**[診断]**、**[ログのエクスポート]** の順に選びます。 最新のエラーは、確認するログ ファイルの下部に記載されています。

    ![ゲートウェイ診断](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. BW トレースを有効にし、生成されたログ ファイルを確認します。 さまざまな種類の BW トレースを使用できます。 詳細については、SAP のドキュメントを参照してください。

## <a name="errors-from-an-insufficient-kerberos-configuration"></a>Kerberos の不適切な構成によるエラー

基になっているデータベース サーバーとゲートウェイが **Kerberos の制約付き委任**用に正しく構成されていない場合、次のエラー メッセージが表示される可能性があります。

![データの読み込みエラー](media/service-gateway-sso-kerberos/load-data-error.png)

また、エラー メッセージ (DM_GWPipeline_Gateway_ServerUnreachable) に関連付けられている技術的な詳細は次のようになります。

![サーバーに到達できません](media/service-gateway-sso-kerberos/server-unreachable.png)

つまり、ゲートウェイは元のユーザーを適切に偽装できず、データベース接続の試行は失敗しました。

## <a name="next-steps"></a>次の手順

**オンプレミス データ ゲートウェイ**と **DirectQuery** の詳細については、次のリソースをご覧ください。

* [オンプレミス データ ゲートウェイ](service-gateway-onprem.md)
* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery でサポートされるデータ ソース](desktop-directquery-data-sources.md)
* [DirectQuery と SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery と SAP HANA](desktop-directquery-sap-hana.md)