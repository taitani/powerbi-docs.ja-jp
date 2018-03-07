---
title: "オンプレミス データ ゲートウェイの詳細"
description: "この記事では、オンプレミス ゲートウェイについて詳しく取り上げます。 Analysis Services の使用時にこのサービスが Azure Active Directory やローカルの Active Directory と連動するしくみについて説明します。"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 7283ee62838779590bbc01eb8b4348cfc7873dc1
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="on-premises-data-gateway-in-depth"></a>オンプレミス データ ゲートウェイの詳細
組織のユーザーはオンプレミス データ (アクセス認証を取得済みの) にアクセスできますが、オンプレミス データ ソースに接続するには、事前にオンプレミス データ ゲートウェイをインストールし、設定しておく必要があります。 このゲートウェイにより、クラウドのユーザーとオンプレミス データ ソースの間のバックグラウンドの通信が迅速かつ安全な方法で確立されます。

ゲートウェイのインストールと構成は、通常、管理者によって行われます。 この作業には、オンプレミスのサーバーの特別な知識と、場合によっては、サーバー管理者のアクセス許可が必要です。

この記事では、ゲートウェイをインストールして構成する方法の詳しい手順は説明しません。 そのために、「[オンプレミス データ ゲートウェイ](service-gateway-onprem.md)」を必ず参照してください。 この記事の目的は、ゲートウェイが機能するしくみを理解できるように、その詳細を説明することです。 また、Azure Active Directory と Analysis Services の両方におけるユーザー名とセキュリティの詳細も少し説明します。さらに、サインインでユーザーが使用した電子メール アドレス、ゲートウェイ、Active Directory をクラウド サービスが利用し、オンプレミスのデータにセキュリティで保護された接続を行い、クエリを実行する方法について説明します。

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>アカウントにサインインする
ユーザーは職場または学校のアカウントでサインインします。 これは組織アカウントです。 Office 365 サービスにサインアップし、実際の職場のメールを指定しなかった場合、nancy@contoso.onmicrosoft.com のようになります。クラウド サービス内では、アカウントは Azure Active Directory (AAD) のテナント内に保存されます。 ほとんどの場合、AAD アカウントの UPN はメール アドレスに一致します。

## <a name="authentication-to-on-premises-data-sources"></a>オンプレミス データ ソースの認証
保存された資格情報は、Analysis Services を除き、オンプレミス データ ソースにゲートウェイから接続するために使用されます。 個々のユーザーに関係なく、ゲートウェイは保存されている資格情報を利用して接続します。

## <a name="authentication-to-a-live-analysis-services-data-source"></a>ライブ Analysis Services データ ソースの認証
Analysis Services をユーザーが操作するたびに、有効なユーザー名がゲートウェイに渡され、次にオンプレミスの Analysis Services サーバーに渡されます。 ユーザー プリンシパル名 (UPN)、通常、クラウドにサインインするときに使用する電子メール アドレスは、有効なユーザーとして Analysis Services に渡すものです。 UPN は接続プロパティ EffectiveUserName に渡されます。 この電子メール アドレスは、ローカルの Active Directory ドメイン内で定義されている UPN と一致する必要があります。 UPN は、Active Directory アカウントのプロパティです。 サーバーにアクセスするには、その Windows アカウントが Analysis Services ロールに存在する必要があります。 Active Directory で一致を検出できない場合、ログインは正常に実行されません。

Analysis Services は、このアカウントに基づいて、フィルター処理も提供できます。 フィルター処理は、ロール ベースのセキュリティまたは行レベルのセキュリティで実行できます。

## <a name="role-based-security"></a>ロール ベース セキュリティ
モデルでは、ユーザー ロールに基づいてセキュリティが提供されます。 特定のモデル プロジェクトに対してロールが定義されるのは、SQL Server Data Tools – Business Intelligence (SSDT-BI) でのオーサリング中、または SQL Server Management Studio (SSMS) を使用してモデルをデプロイした後です。 ロールに含まれるメンバーは、Windows ユーザー名または Windows グループによって決まります。 ロールは、ユーザーがモデルに対してクエリまたは操作を実行するためのアクセス許可を定義します。 ほとんどのユーザーは、読み取りアクセス許可を持つロールに属します。 その他のロールは管理者向けで、項目を処理するアクセス許可、データベースの機能を管理するアクセス許可、他のロールを管理するアクセス許可を持つものがあります。

## <a name="row-level-security"></a>行レベルのセキュリティ
行レベルのセキュリティは、Analysis Services の行レベルのセキュリティに固有です。 モデルでは、動的な行レベルのセキュリティを提供できます。 ユーザーが少なくとも 1 つのロールに属する場合とは異なり、表形式モデルに動的なセキュリティは必要ではありません。 動的なセキュリティでは、上位レベルから、特定テーブル内の特定の行のデータに対してユーザーの読み取りアクセス権が定義されます。 ロールの場合と同様、動的な行レベルのセキュリティは、ユーザーの Windows ユーザー名に依存します。

ユーザーがモデルのデータを閲覧したりクエリを実行したりできるかどうかは、第 1 にそのユーザーの Windows ユーザー アカウントがメンバーとなっているロールによって決まり、第 2 に動的な行レベルのセキュリティ (構成されている場合) によって決まります。

モデルでのロールと動的な行レベル セキュリティの実装については、この記事では説明しません。  詳細については、MSDN の「[ロール (SSAS 表形式)](https://msdn.microsoft.com/library/hh213165.aspx)」と「[(Analysis Services - 多次元データ) のセキュリティ ロール](https://msdn.microsoft.com/library/ms174840.aspx)」を参照してください。 また、表形式モデルのセキュリティに関するさらに詳細な情報については、「[表形式 BI セマンティック モデルをセキュリティで保護する](https://msdn.microsoft.com/library/jj127437.aspx)」というホワイトペーパーをダウンロードしてお読みください。

## <a name="what-about-azure-active-directory"></a>Azure Active Directory の役割
Microsoft クラウド サービスは、ユーザーの認証を処理するために [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) を使用します。 Azure Active Directory は、ユーザー名とセキュリティ グループを含むテナントです。 通常、ユーザーがサインインに使用する電子メール アドレスはアカウントの UPN と同じです。

ローカル Active Directory の役割

Analysis Services に接続するユーザーがデータの読み取りアクセス許可を持つロールに属しているかどうかを判断するため、サーバーは、AAD からゲートウェイ、Analysis Services サーバーの順に渡された有効なユーザー名を変換する必要があります。 Analysis Services サーバーは、Windows Active Directory ドメイン コントローラー (DC) に有効なユーザー名を渡します。 Active Directory DC は、ローカル アカウントで、有効なユーザー名が有効 UPN であることを検証し、Analysis Services サーバーにそのユーザーの Windows ユーザー名を返します。

EffectiveUserName は、ドメインに参加していない Analysis Services サーバーで使用できません。 ログイン エラーを回避するには、Analysis Services サーバーをドメインに参加させる必要があります。

## <a name="how-do-i-tell-what-my-upn-is"></a>自分の UPN を確認する方法
自分の UPN がわからないけれども、自分がドメイン管理者ではない場合もあります。 ワークステーションから次のコマンドを実行して、自分のアカウントの UPN を確認できます。

    whoami /upn

結果は電子メール アドレスに似ていますが、これはローカル ドメイン アカウントの UPN です。 ライブ接続に Analysis Services データ ソースを使用している場合、これはゲートウェイから EffectiveUserName に渡されたものに一致する必要があります。

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Analysis Services データ ソースのユーザー名をマッピングする
Power BI では、Analysis Services データ ソースのユーザー名をマッピングできます。 Power BI のログイン ユーザー名を、Analysis Services 接続の有効なユーザー名に渡される名前にマッピングする規則を構成できます。 ユーザー名のマッピング機能は、AAD のユーザー名がローカル Active Directory の UPN に一致しないときの回避策として優れています。 たとえば、メール アドレスが nancy@contoso.onmicrsoft.com の場合、それを nancy@contoso.com にマッピングできます。その値がゲートウェイに渡されます。 詳細については、[ユーザー名のマッピング](service-gateway-enterprise-manage-ssas.md#map-user-names)方法に関するページを参照してください。

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>オンプレミスの Active Directory を Azure Active Directory と同期する
Analysis Services ライブ接続を使用する場合、ローカル Active Directory アカウントが Azure Active Directory に一致すると便利です。 UPN はアカウント間で一致する必要があるためです。

クラウドサービスは、Azure Active Directory 内のアカウントのみを認識します。 ローカル Active Directory にアカウントを追加したかどうかは問題ではなく、AAD に存在しなければ、使用できません。 ローカル Active Directory アカウントと Azure Active Directory はさまざまな方法で一致させることができます。

1. Azure Active Directory にアカウントを手動で追加できます。
   
   Azure ポータルで、あるいは Office 365 Admin ポータル内でアカウントを作成できます。アカウント名はローカル Active Directory アカウントの UPN と一致します。
2. [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) ツールを使用し、ローカル アカウントと Azure Active Directory テナントを同期させることができます。
   
   Azure AD Connect ツールには、ディレクトリとパスワードの同期オプションがあります。 テナント管理者またはローカル ドメイン管理者ではない場合、IT 管理者に問い合わせ、これを構成してもらう必要があります。
3. Active Directory Federation Services (ADFS) を構成できます。
   
   [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) ツールを使用し、ADFS サーバーを AAD テナントに関連付けることができます。 ADFS では、上記のディレクトリ同期が利用されますが、シングル サインオン (SSO) が可能です。 たとえば、職場のネットワークにいる場合、クラウド サービスにアクセスし、サインインに進むとき、ユーザー名またはパスワードの入力が求められません。 組織でこれが利用できる場合、IT 管理者と話し合う必要があります。

Azure AD Connect を利用すると、UPN は AAD とローカル Active Directory 間で一致します。

> [!NOTE]
> Azure AD Connect ツールでアカウントを同期させると、AAD テナント内に新しいアカウントが作成されます。
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>ゲートウェイについて
ゲートウェイは、クラウドとオンプレミス サーバー間のブリッジとして機能します。 クラウドとゲートウェイ間のデータ転送は、[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/) を介してセキュリティで保護されます。 Service Bus は、ゲートウェイでの送信接続を使用して、クラウドとオンプレミスのサーバーの間にセキュリティで保護されたチャネルを作成します。  オンプレミス ファイアウォールで開く必要のある受信接続はありません。

Analysis Services データ ソースを持っている場合は、Analysis Services サーバーと同じフォレストまたはドメインに結合しているコンピューターにゲートウェイをインストールする必要があります。

ゲートウェイがサーバーに近づけば近づくほど、接続は速くなります。 データ ソースと同じサーバー上にゲートウェイを取得できる場合、それはゲートウェイとサーバー間のネットワーク遅延を回避するのに最適です。

## <a name="what-to-do-next"></a>次に行うこと
ゲートウェイをインストールした後は、そのゲートウェイのデータ ソースを作成します。 データ ソースの追加は、**[ゲートウェイの管理]** 画面で行うことができます。 詳細については、データ ソースの管理に関する記事をご覧ください。

[データ ソースの管理 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[データ ソースの管理 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[データ ソースの管理 - SQL Server](service-gateway-enterprise-manage-sql.md)  
[データ ソースの管理 - Oracle](service-gateway-onprem-manage-oracle.md)  
[データ ソースの管理 - インポート/スケジュールされた更新](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>うまくいかない場合
場合によっては、ゲートウェイのインストールが失敗することがあります。 または、ゲートウェイのインストールが成功したように見えても、サービスがそれを処理できない場合があります。 多くの場合、それは簡単な要因です (ゲートウェイがデータ ソースにサインインするのに使用する資格情報のパスワードなど)。

その他のケースとして、ユーザーがサインインする電子メール アドレスの種類に問題がある場合や、Analysis Services が有効なユーザー名を解決できない場合があります。 相互に信頼関係を持つ複数のドメインがあり、ゲートウェイのあるドメインと、Analysis Services のあるドメインが異なっていると、そのことが問題の原因になる場合があります。

ゲートウェイのトラブルシューティングについては、この記事ではなく、トラブルシューティングの手順に関する別の記事で説明します。「[オンプレミス データ ゲートウェイのトラブルシューティング](service-gateway-onprem-tshoot.md)」をご覧ください。 何も問題が起きないことを願っています。 もし問題が起きてしまった場合は、この機能のしくみを理解しておくことと、トラブルシューティングの記事が役立ちます。

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>次の手順
[オンプレミス データ ゲートウェイのトラブルシューティング](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

