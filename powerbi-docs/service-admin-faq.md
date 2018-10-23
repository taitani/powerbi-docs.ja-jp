---
title: Power BI の管理 - よく寄せられる質問 (FAQ)
description: Power BI のサインアップ、テナント管理、その他の管理タスクに関するよく寄せられる質問 (FAQ) とその回答について説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b77d20b8c9705e4b4cd811ea8dfa3008908a4438
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641691"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Power BI の管理 - よく寄せられる質問 (FAQ)

この記事では、Power BI の管理に関するよく寄せられる質問 (FAQ) を取り上げます。 Power BI の管理の概要については、[Power BI の管理](service-admin-administering-power-bi-in-your-organization.md)に関するページを参照してください。

## <a name="whats-in-this-article"></a>この記事の内容
**Power BI にサインアップする**

* [ユーザーは Power BI にどのような方法でサインアップできますか。](#how-do-users-sign-up-for-power-bi)
* [組織内の個々のユーザーは、どのような方法でサインアップできますか。](#how-do-individual-users-in-my-organization-sign-up)
* [既存の Office 365 テナントにユーザーが参加できないようにするにはどうすればよいですか。](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [既存の Office 365 テナントへの参加をユーザーに許可するにはどうすればよいですか。](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [テナントをブロックしたかどうかを確認するにはどうすればよいですか。](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [既存のユーザーが Power BI の使用を開始できないようにするにはどうすればよいですか。](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [既存のユーザーに Power BI へのサインアップを許可するにはどうすればよいですか。](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Power BI の管理**

* [組織内のユーザーの ID を管理する方法はどのように変わりますか。](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Power BI を管理するにはどうすればよいですか。](#how-do-we-manage-power-bi)
* [Microsoft によってユーザーに対して作成されたテナントを管理するにはどうすればよいですか。](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [複数のドメインがある場合、ユーザーが追加される Office 365 テナントを制御できますか。](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Power BI に既にサインアップしているユーザーを削除するにはどうすればよいですか。](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [新しいユーザーがいつテナントに参加したかを確認するにはどうすればよいですか。](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [他に何か準備する必要があることはありますか。](#are-there-any-additional-things-i-should-be-prepared-for)
* [Power BI テナントの場所](#where-is-my-power-bi-tenant-located)
* [Power BI SLA (サービス レベル アグリーメント) とは何ですか。](#what-is-the-power-bi-sla)

**Power BI のセキュリティ**

* [Power BI は、国、地域、および業界固有のコンプライアンス要件を満たしていますか。](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Power BI のセキュリティはどのように機能していますか。](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Power BI にサインアップする
### <a name="how-do-users-sign-up-for-power-bi"></a>ユーザーは Power BI にどのような方法でサインアップできますか。
Power BI には、[Power BI Web サイト](https://powerbi.microsoft.com)からサインアップすることができます。 Office 365 管理センターの [サービスを購入する] ページからサインアップすることもできます。 管理者が Power BI にサインアップした場合は、アクセスする必要があるユーザーにユーザー ライセンスを割り当てることができます。

さらに、組織内の個々のユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com)から Power BI にサインアップすることができます。 組織内のユーザーが Power BI にサインアップすると、そのユーザーに Power BI ライセンスが自動的に割り当てられます。 [詳細情報](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>組織内の個々のユーザーは、どのような方法でサインアップできますか。
組織内のユーザーに適用される可能性がある 3 つのシナリオがあります。

シナリオ 1: 組織に既存の Office 365 環境が既に存在し、Power BI にサインアップするユーザーが Office 365 アカウントを既に持っている。
このシナリオでは、ユーザーがテナント (contoso.com など) に既に職場または学校のアカウントを持っているが、まだ Power BI にサインアップしていない場合は、Microsoft がそのアカウントに対してプランをアクティブ化するだけで、Power BI サービスの使用方法に関する通知が自動的にユーザーに送信されます。

シナリオ 2: 組織に既存の Office 365 環境が既に存在し、Power BI にサインアップするユーザーがまだ Office 365 アカウントを持っていない場合。
このシナリオでは、ユーザーは、組織のドメイン (contoso.com など) の電子メール アドレスを持っていますが、まだ Office 365 アカウントを持っていません。 この場合、ユーザーは Power BI にサインアップすることができ、アカウントが自動的に与えられます。 これにより、ユーザーは、Power BI サービスにアクセスすることができます。 たとえば、Nancy という名前の従業員が職場の電子メール アドレス (Nancy@contoso.com など) を使用してサインアップした場合、Contoso の Office 365 環境に Nancy がユーザーとして自動的に追加され、そのアカウントに対して Power BI が有効になります。

シナリオ 3: 組織に電子メール ドメインに接続されている Office 365 環境がない。
Power BI を利用するために組織が行う必要がある管理操作はありません。 ユーザーは新しいクラウド専用のユーザー ディレクトリに追加され、管理者はテナント管理者としてユーザーの管理を引き継ぐことを選択できます。

> [!IMPORTANT]
> 組織に複数の電子メール ドメインがあり、すべての電子メール アドレスの拡張を同じテナントにまとめる場合は、ユーザーがサインアップする前に、すべての電子メール アドレス ドメインを Azure Active Directory テナントに追加する必要があります。 ユーザーを作成した後でテナント間でユーザーを自動的に移動するメカニズムはありません。 このプロセスの詳細については、この記事の「[複数のドメインがある場合、ユーザーが追加される Office 365 テナントを制御できますか。](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)」と、オンラインの[Office 365 へのドメインの追加に関する記事](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>既存の Office 365 テナントにユーザーが参加できないようにするにはどうすればよいですか。
既存の Office 365 テナントにユーザーが参加できないようにするために、管理者として実行できる手順があります。 このブロックを実行すると、ユーザーのサインアップは失敗し、ユーザーは組織の管理者に連絡するように指示されます。ライセンスの自動配布 (学生、教職員、およびスタッフ向けの Office 365 for Education など) を既に無効にしている場合は、このプロセスを繰り返す必要はありません。

次の手順を実行するには、Windows PowerShell を使用する必要があります。 Windows PowerShell の使用を開始するには、[PowerShell ファースト ステップ ガイド](http://go.microsoft.com/fwlink/p/?LinkID=286814)を参照してください。

次の手順を実行するには、最新の 64 ビット バージョンの [Azure Active Directory Module for Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) をインストールする必要があります。

リンクを選択した後、**[実行]** を選択してインストーラー パッケージを実行します。

**テナントの自動参加を無効にする**: 管理対象テナントに新しいユーザーが参加できないようにするには、次の Windows PowerShell コマンドを使用します。

* 新しいユーザーによるテナントの自動参加を無効にするには:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* 新しいユーザーによるテナントの自動参加を有効にするには:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> このブロックは、組織内の新しいユーザーが Power BI にサインアップできないようにします。 組織の新しいサインアップを無効にする前に Power BI にサインアップしているユーザーは、引き続きライセンスを保持します。 サービスに既にサインアップしているユーザーの Power BI へのアクセスを削除する手順については、「How Can I Remove Licenses?」セクションを参照してください。
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>既存の Office 365 テナントへの参加をユーザーに許可するにはどうすればよいですか。
テナントへのユーザーの参加を許可するには、前の質問で説明されているコマンドとは逆のコマンドを実行します。

次の手順を実行するには、最新の 64 ビット バージョンの [Azure Active Directory Module for Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) をインストールする必要があります。

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>テナントをブロックしたかどうかを確認するにはどうすればよいですか。
次の PowerShell スクリプトを使用します。

次の手順を実行するには、最新の 64 ビット バージョンの [Azure Active Directory Module for Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) をインストールする必要があります。

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>既存のユーザーが Power BI の使用を開始できないようにするにはどうすればよいですか。
ユーザーが Power BI にサインアップできないようにするために、管理者として実行できる手順があります。 このブロックを実行すると、ユーザーのサインアップは失敗し、ユーザーは組織の管理者に連絡するように指示されます。ライセンスの自動配布 (学生、教職員、およびスタッフ向けの Office 365 for Education など) を既に無効にしている場合は、このプロセスを繰り返す必要はありません。 [詳細情報](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

これを制御する AAD 設定は、**AllowAdHocSubscriptions** です。 ほとんどのテナントでは、この設定は有効を意味する true に設定されます。 パートナーを通じて Power BI を入手した場合、これは既定では無効を意味する false に設定されている可能性があります。

次の手順を実行するには、最新の 64 ビット バージョンの [Azure Active Directory Module for Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) をインストールする必要があります。

1. まず、Office 365 の資格情報を使用して Azure Active Directory にサインインする必要があります。 最初の行で、資格情報が求められます。 2 行目で、Azure Active Directory に接続します。
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. サインインの後、次のコマンドを発行してテナントの構成内容を見ることができます。
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. このコマンドを使用して、AllowAdHocSubscriptions を有効 ($True) または無効 ($false) にすることができます。
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions フラグは、組織内のさまざまなユーザーの能力を制御するために使用されます。この中には、ユーザーが Azure Rights Management サービスにサインアップする能力も含まれます。 このフラグの変更は、これらすべての能力に影響します。
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>既存のユーザーに Power BI へのサインアップを許可するにはどうすればよいですか。
既存のユーザーに Power BI へのサインアップを許可するには、前の質問で説明されているコマンドを実行しますが、false の代わりに true を渡します。

次の手順を実行するには、最新の 64 ビット バージョンの [Azure Active Directory Module for Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) をインストールする必要があります。

1. まず、Office 365 の資格情報を使用して Azure Active Directory にサインインする必要があります。 最初の行で、資格情報が求められます。 2 行目で、Azure Active Directory に接続します。
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. サインインの後、次のコマンドを発行してテナントの構成内容を見ることができます。
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. このコマンドを使用して、AllowAdHocSubscriptions を有効 ($True) または無効 ($false) にすることができます。
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions フラグは、組織内のさまざまなユーザーの能力を制御するために使用されます。この中には、ユーザーが Azure Rights Management サービスにサインアップする能力も含まれます。 このフラグの変更は、これらすべての能力に影響します。
> 
> 

## <a name="administration-of-power-bi"></a>Power BI の管理
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>組織内のユーザーの ID を管理する方法はどのように変わりますか。
組織に既存の Office 365 環境が既に存在し、組織内のすべてのユーザーが Office 365 アカウントを持っている場合、ID 管理に変更はありません。

組織に既存の Office 365 環境は既に存在するが、組織内の一部のユーザーのみが Office 365 アカウントを持っている場合は、テナント内にユーザーが作成され、ユーザーの職場または学校の電子メール アドレスに基づいてライセンスが割り当てられます。 つまり、組織内のユーザーがサービスにサインアップすると、その時点で管理しているユーザーの数が増加します。

組織に電子メール ドメインに接続されている Office 365 環境がない場合、ID を管理する方法は変更されません。 ユーザーは新しいクラウド専用のユーザー ディレクトリに追加され、管理者はテナント管理者としてユーザーの管理を引き継ぐことを選択できます。

### <a name="how-do-we-manage-power-bi"></a>Power BI を管理するにはどうすればよいですか。
Power BI には、使用状況の統計を表示でき、ユーザーとグループを管理する Office 365 管理センターへのリンクとテナント全体の設定を制御するための機能を備えた管理ポータルが用意されています。 

> [!NOTE]
> Power BI の管理ポータルにアクセスするには、アカウントが Office 365 または Azure Active Directory 内で **[グローバル管理者]** とマークされているか、Power BI サービス管理者の役割が割り当てられている必要があります。 Power BI サービス管理者の役割の詳細については、「[Power BI 管理者の役割について](service-admin-role.md)」を参照してください。
> 
> 

詳細については、「[Power BI 管理ポータル](service-admin-portal.md)」を参照してください。

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Microsoft によってユーザーに対して作成されたテナントを管理するにはどうすればよいですか。
テナントが Microsoft によって作成された場合は、次の手順に従うことで、そのテナントを管理できるようになります。

1. 管理するテナントのドメインに対応する電子メール アドレスのドメインを使用して Power BI にサインアップすることで、テナントに参加します。 たとえば、Microsoft によって contoso.com テナントが作成されている場合は、@contoso.com で終わる電子メール アドレスを使用してテナントに参加する必要があります。
2. ドメインの所有権を確認することで、管理権を要求します。テナントに参加した後、ドメインの所有権を確認することで、自分自身を *[グローバル管理者]* ロールに昇格させることができます。 これを行うには、次の手順に従います。
   
   1. [https://portal.office.com](https://portal.office.com) に移動します。
   2. 左上のアプリケーション ランチャー アイコンを選択し、**[管理者]** を選択します。
   3. **[Become the admin (管理者になる)]** ページ指示を確認した後、**[Yes, I want to be the admin (はい、管理者になります)]** を選択します。
      
      > [!NOTE]
      > このオプションが表示されない場合は、Office 365 管理者が既に存在します。
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>複数のドメインがある場合、ユーザーが追加される Office 365 テナントを制御できますか。
何もしなければ、各ユーザーの電子メール ドメインとサブドメイン用のテナントが作成されます。

電子メール アドレスの拡張に関係なく、すべてのユーザーを同じテナントにまとめる場合:

* 対象テナントを事前に作成するか既存のテナントを使用して、そのテナントに統合するすべての既存のドメインとサブドメインを追加します。 これで、これらのドメインとサブドメインで終わる電子メール アドレスを持つすべてのユーザーは、サインアップすると自動的に対象テナントに参加するようになります。

> [!IMPORTANT]
> ユーザーを作成した後でテナント間でユーザーを自動的に移動するメカニズムはサポートされていません。 1 つの Office 365 テナントにドメインを追加する方法については、[Office 365 へのユーザーとドメインの追加に関するページ](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Power BI に既にサインアップしているユーザーを削除するにはどうすればよいですか。
Power BI にサインアップする必要がなくなったユーザーが Power BI にアクセスできないようにする場合は、そのユーザーの Power BI ライセンスを削除できます。

1. Office 365 管理センターに移動します。
2. 左側のナビゲーション バーで、**[ユーザー]** > **[アクティブ ユーザー]** の順に選択します。
3. ライセンスを削除するユーザーを見つけ、その名前を選択し、**[編集]** を選択します。
4. [ユーザーの詳細] ページで、左側のナビゲーション バーの **[ライセンス]** を選択します。
5. アカウントに適用されているライセンスに応じて、**[Power BI (無料)]** または **[Power BI Pro]** をオフにします。
6. **[保存]** を選択します。

> [!NOTE]
> ユーザーのライセンスは、一括管理することもできます。 これを実行するには、複数のユーザーを選択し、**[編集]** を選択します。
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>新しいユーザーがいつテナントに参加したかを確認するにはどうすればよいですか。
このプログラムの一部であるテナントに参加したユーザーには、管理ダッシュボードの [アクティブ ユーザー] ウィンドウでフィルター処理することができる一意のライセンスが割り当てられます。

この新しいビューを作成するには、Office 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** の順に選択し、**[ビューの選択]** メニューから **[新しいビュー]** を選択します。 新しいビューに名前を付け、**[割り当て済みのライセンス]** で、**[Power BI (無料)]** または **[Power BI Pro]** を選択します。 ビューごとにライセンスを 1 つだけ選択できます。 組織内に **Power BI (無料)** のライセンスと **Power BI Pro** のライセンスがある場合は、2 つのビューを作成する必要があります。 新しいビューを作成した後、このプログラムに登録しているテナントのすべてのユーザーを表示することができます。

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>他に何か準備する必要があることはありますか。
パスワードのリセット要求が増える可能性があります。 このプロセスの詳細については、「[Office 365 でユーザーのパスワードを再設定する](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)」を参照してください。

テナントからのユーザーの削除は、Office 365 管理センターの標準的なプロセスを使用して実行できます。 ただし、ユーザーが組織のアクティブな電子メール アドレスを引き続き使用する場合、すべてのユーザーがブロックされない限り、そのユーザーはテナントに再び参加できます。

### <a name="where-is-my-power-bi-tenant-located"></a>Power BI テナントの場所
Power BI テナントがある場所 (データ領域とも呼ばれます) を調べる方法については、「[Power BI テナントの場所](service-admin-where-is-my-tenant-located.md)」をご覧ください。

### <a name="what-is-the-power-bi-sla"></a>Power BI SLA とは何ですか。
Power BI SLA (サービス レベル アグリーメント) の詳細については、Microsoft ライセンス Web サイトの「**Licensing**」 (ライセンス) セクションにある「[Licensing Terms and Documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37)」 (ライセンス条項とドキュメント) という記事を参照してください。

## <a name="security-in-power-bi"></a>Power BI のセキュリティ
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI は、国、地域、および業界固有のコンプライアンス要件を満たしていますか。
Power BI のコンプライアンスの詳細については、[Microsoft セキュリティ センター](http://go.microsoft.com/fwlink/?LinkId=785324)を参照してください。

### <a name="how-does-security-work-in-power-bi"></a>Power BI のセキュリティはどのように機能していますか。
Power BI は Office 365 上に構築されており、Azure Active Directory などの Azure サービス上に構築されます。 Power BI のアーキテクチャの概要については、「[Power BI のセキュリティ](service-admin-power-bi-security.md)」をご覧ください。 

## <a name="next-steps"></a>次の手順
[Power BI 管理ポータル](service-admin-portal.md)  
[Power BI 管理者の役割について](service-admin-role.md)  
[Power BI のセルフサービス サインアップ](service-self-service-signup-for-power-bi.md)  
[Power BI Pro を購入する](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium とは何ですか?](service-premium.md)  
[Power BI Premium の購入方法](service-admin-premium-purchase.md)  
[Office 365 のユーザー アカウント管理](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365 グループ管理](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Power BI および Office 365 でのグループ管理](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Power BI Premium ホワイト ペーパー](https://aka.ms/pbipremiumwhitepaper)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。