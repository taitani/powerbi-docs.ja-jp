---
title: Power BI の管理 - よく寄せられる質問 (FAQ)
description: Power BI へのサインアップ、テナントの管理、およびその他の管理タスクに関するよく寄せられる質問に対する回答について説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100773"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Power BI の管理 - よく寄せられる質問 (FAQ)

この記事では、Power BI の管理に関するよく寄せられる質問 (FAQ) を取り上げます。 Power BI の管理の概要については、[Power BI の管理](service-admin-administering-power-bi-in-your-organization.md)に関するページを参照してください。

## <a name="whats-in-this-article"></a>この記事の内容

### <a name="sign-up-for-power-bi-section"></a>Power BI のサインアップ セクション

* [PowerShell の使用](#using-powershell)
* [ユーザーは Power BI にどのような方法でサインアップできますか。](#how-do-users-sign-up-for-power-bi)
* [組織内の個々のユーザーは、どのような方法でサインアップできますか。](#how-do-individual-users-in-my-organization-sign-up)
* [既存の Office 365 テナントにユーザーが参加できないようにするにはどうすればよいですか。](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [既存の Office 365 テナントへの参加をユーザーに許可するにはどうすればよいですか。](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [テナント内、ブロックがあるはかどうかを確認する方法](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [既存のユーザーが Power BI の使用を開始できないようにするにはどうすればよいですか。](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [既存のユーザーに Power BI へのサインアップを許可するにはどうすればよいですか。](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Power BI の管理セクション

* [組織内のユーザーの ID を管理する方法はどのように変わりますか。](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Power BI を管理するにはどうすればよいですか。](#how-do-we-manage-power-bi)
* [Microsoft によってユーザーに対して作成されたテナントを管理するにはどうすればよいですか。](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [複数のドメインがある場合、ユーザーに追加される Office 365 テナントを制御できますか。](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [Power BI に既にサインアップしているユーザーを削除するにはどうすればよいですか。](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [新しいユーザーがいつテナントに参加したかを確認するにはどうすればよいですか。](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [他に何を準備する必要がありますはありますか。](#are-there-any-additional-things-i-should-prepare-for)
* [Power BI テナントの場所](#where-is-my-power-bi-tenant-located)
* [Power BI SLA (サービス レベル アグリーメント) とは何ですか。](#what-is-the-power-bi-sla)
* [Power BI では高可用性とフェールオーバーはどのように処理されますか。](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>Power BI のセキュリティ セクション

* [Power BI は、国、地域、および業界固有のコンプライアンス要件を満たしていますか。](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Power BI のセキュリティはどのように機能していますか。](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Power BI にサインアップする

### <a name="using-powershell"></a>PowerShell の使用

このセクションの一部の手順では、Windows PowerShell スクリプトが必要です。 PowerShell に慣れていない場合は、「[Windows PowerShell ファースト ステップ ガイド](http://go.microsoft.com/fwlink/p/?LinkID=286814)」を読むことをお勧めします。 スクリプトを実行するには、最初に [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/) の最新の 64 ビット バージョンをインストールします。

### <a name="how-do-users-sign-up-for-power-bi"></a>ユーザーは Power BI にどのような方法でサインアップできますか。

管理者はから Power BI にサインアップすることができます、 [Power BI web サイト](https://powerbi.microsoft.com)または[サービスを購入](https://admin.microsoft.com/AdminPortal/Home#/catalog)Microsoft 365 管理センターのページ。 管理者が Power BI のサインアップ時に、アクセス権を持つユーザーにユーザー ライセンスを割り当てることができます、します。

さらに、組織内の個々のユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com)から Power BI にサインアップすることができます。 組織内のユーザーが Power BI にサインアップすると、ときに、サービスは自動的にユーザーに Power BI ライセンスを割り当てます。 詳細については、次を参照してください。[個人として Power BI にサインアップする](service-self-service-signup-for-power-bi.md)と[、組織内の Power BI ライセンス](service-admin-licensing-organization.md)します。

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>組織内の個々のユーザーは、どのような方法でサインアップできますか。

組織内のユーザーに適用される可能性がある 3 つのシナリオがあります。

* **シナリオ 1**:組織に既存の Office 365 環境が既に存在し、Power BI にサインアップするユーザーが Office 365 アカウントを既に持っている。
    このシナリオで、ユーザーが既に職場または学校のアカウント、テナント (contoso.com など) ではがまだ Power bi では、Microsoft だけをアクティブにそのアカウントの計画。 ユーザーには、Power BI サービスを使用する方法についてで自動的に通知します。

* **シナリオ 2**:組織に既存の Office 365 環境が既に存在するが、Power BI にサインアップするユーザーがまだ Office 365 アカウントを持っていない場合。
    このシナリオでは、ユーザーは、組織のドメイン (contoso.com など) に、電子メール アドレスがあるが、Office 365 アカウントがまだないです。 この場合、ユーザーは Power BI にサインアップすることができ、アカウントが自動的に与えられます。 この操作には、Power BI サービスのユーザー アクセスことができます。 たとえば、従業員が Nancy を使用してという名前の場合、職場の電子メール アドレス (のようなnancy@contoso.com) にサインアップすると、Microsoft 自動的に Nancy を Contoso の Office 365 環境のユーザーとして追加し、そのアカウントに対して Power BI をアクティブにします。

* **シナリオ 3**:組織は、メールのドメインに接続されている Office 365 環境にありません。
    Power BI を活用するために、組織に必要な管理の操作はありません。 サービスでは、新しいクラウド専用ユーザーのディレクトリにユーザーを追加します。 テナント管理者として引き継ぐし、それらを管理することもできます。

> [!IMPORTANT]
> 組織に複数の電子メール ドメインがあり、すべての電子メール アドレスの拡張を同じテナントにまとめる場合は、ユーザーがサインアップする前に、すべての電子メール アドレス ドメインを Azure Active Directory テナントに追加する必要があります。 ユーザーを作成したら、テナント間でユーザーを移動する自動メカニズムはありません。 このプロセスの詳細については、次を参照してください。[複数のドメインがある場合、Office 365 テナントを制御できますユーザーに追加されるでしょうか。](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)この記事で後述と[Office 365 にドメインを追加](/office365/admin/setup/add-domain/)します。

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>既存の Office 365 テナントにユーザーが参加できないようにするにはどうすればよいですか。

既存の Office 365 テナントにユーザーが参加できないようにするために、管理者として実行できる手順があります。 失敗、サインアップするユーザーは、アクセスをブロックして、メッセージが表示場合、するよう指示、組織の管理者に問い合わせてください。既に (学生、教職員、およびスタッフ向けの教育機関向け Office 365) を使用してライセンスの自動配布を無効にした場合、このプロセスを繰り返す必要はありません。

新しいユーザーがマネージド テナントに参加できないようにするには、次の PowerShell スクリプトを使用します。 ([PowerShell の詳細を確認する][1]。)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> アクセスをブロックすると、組織内の新しいユーザーは Power BI にサインアップできなくなります。 組織の新しいサインアップを無効にする前に Power BI にサインアップしているユーザーは、引き続きライセンスを保持します。 ユーザーを削除する方法については、後の「[Power BI に既にサインアップしているユーザーを削除するにはどうすればよいですか](#how-do-i-remove-power-bi-for-users-that-already-signed-up)」をご覧ください。

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>既存の Office 365 テナントへの参加をユーザーに許可するにはどうすればよいですか。

次の PowerShell スクリプトを使用して、新しいユーザーが管理対象テナントに参加できるようにします。 ([PowerShell の詳細を確認する][1]。)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>テナント内、ブロックがあるはかどうかを確認する方法

設定を確認するのにには、次の PowerShell スクリプトを使用します。 *AllowEmailVerifiedUsers* が false になっている必要があります。 ([PowerShell の詳細を確認する][1]。)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>既存のユーザーが Power BI の使用を開始できないようにするにはどうすればよいですか。

これを制御する Azure AD の設定は、**AllowAdHocSubscriptions** です。 ほとんどのテナントがある、有効になっていることを意味する true に設定します。 パートナーを通じて Power BI を入手した場合、このを無効になっていることを意味する false に設定できます。

アドホック サブスクリプションを無効にするには、次の PowerShell スクリプトを使用します。 ([PowerShell の詳細を確認する][1]。)

1. Office 365 の資格情報を使用して Azure Active Directory にサインインします。 次の PowerShell のスクリプトの 1 行目では、ユーザーに資格証明が要求されます。 2 行目で、Azure Active Directory に接続します。

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Azure の Active Directory のスクリーン ショットが PowerShell を使ったサインイン](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. サインインすると、テナントの現在設定の方法を参照してください。 次のコマンドを実行します。

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. 有効にするのには、次のコマンドを実行 (`$true`) または無効にする (`$false`) **AllowAdHocSubscriptions**します。

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> 使用して、 **AllowAdHocSubscriptions**ユーザーが Azure Rights Management サービスにサインアップする機能など、組織内のいくつかのユーザー機能を制御するフラグ。 このフラグの変更は、これらすべての能力に影響します。

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>既存のユーザーに Power BI へのサインアップを許可するにはどうすればよいですか。

前の質問の一覧表示コマンドを実行して、Power BI にサインアップする既存のユーザーを許可するが、渡す`$true`の代わりに`$false`最後の手順でします。

## <a name="administration-of-power-bi"></a>Power BI の管理

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>組織内のユーザーの ID を管理する方法はどのように変わりますか。

組織内のユーザーに適用される可能性がある 3 つのシナリオがあります。

* **シナリオ 1**:場合は、組織で既にに既存の Office 365 環境があり、ユーザーが、組織内のすべてのユーザーが Office 365 アカウントを持っているは、id の管理方法の変更はありません。

* **シナリオ 2**:既に導入している既存の Office 365 環境が、組織内のすべてのユーザーが Office 365 アカウントを持っている、テナントでユーザーを作成し、ユーザーの職場または学校の電子メール アドレスに基づいてライセンスを割り当てます。

    結果として、組織のユーザーがサービスにサインアップすると、特定の時点に管理しているユーザーの数が増大します。

* **シナリオ 3**:組織では、電子メール ドメインに接続されている Office 365 環境があるない場合、id の管理方法の変更はありません。

    サービスでは、新しいクラウド専用ユーザーのディレクトリにユーザーを追加します。 また、テナント管理者として引き継ぐし、それらを管理することができます。

### <a name="how-do-we-manage-power-bi"></a>Power BI を管理するにはどうすればよいですか。

Power BI には、管理ポータル、使用状況の統計を表示することができるユーザーとグループを管理する Microsoft 365 管理センターへのリンクし、テナント全体の設定を制御する機能を提供しますが提供します。

Power BI の管理ポータルを使用するには、としてアカウントをマークする必要があります、**グローバル管理者**Office 365 または Azure 内で Active Directory、またはユーザーが割り当てる必要があります、Power BI サービス管理者ロール、ユーザー アカウントにします。 詳細については、次を参照してください。 [Power BI 管理者の役割について](service-admin-role.md)と[Power BI 管理ポータル](service-admin-portal.md)します。

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Microsoft によってユーザーに対して作成されたテナントを管理するにはどうすればよいですか。

セルフ サービス ユーザーが Azure AD を使用するクラウド サービスのサインアップ時にサービスに追加して非管理対象の Azure AD ディレクトリは、電子メール ドメインに基づきます。 要求のおよびと呼ばれるプロセスを使用して作成されたユーザーがテナントを管理することができます、*管理者の引き継ぎ*します。 引き継ぎを行うの種類によって異なります、ドメインに関連付けられているテナントを管理するかどうかが既に存在します。

* ドメインに対して新しいマネージド テナントを作成するには、"*内部の引き継ぎ*" を使用します。

* 既存のマネージド テナントにドメインを移動するには、"*外部の引き継ぎ*" を使用します。

詳細については、次を参照してください。 [Azure Active Directory で管理者として、非管理対象のディレクトリを引き継ぐ](/azure/active-directory/users-groups-roles/domains-admin-takeover)します。

外部の引き継ぎを行うと、サービスが配置 Power BI での引き継ぎの前に作成されたコンテンツを[Power BI アーカイブ済みワークスペース](service-admin-power-bi-archived-workspace.md)します。 新しいテナントで使いたいコンテンツは、すべて手動で移行する必要があります。

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>複数のドメインがある場合、ユーザーに追加される Office 365 テナントを制御できますか。

何を行うと、サービスは、各ユーザーの電子メール ドメインとサブドメインのテナントを作成します。 電子メール アドレスの拡張に関係なく、すべてのユーザーを同じテナントにまとめる場合:事前に、対象のテナントを作成するか、既存のテナントを使用します。 次に、すべての既存のドメインとそのテナントに統合するサブドメインを追加します。 サインアップするときに、自動的にこれらのドメインとサブドメインで終わる電子メール アドレスを持つすべてのユーザーは対象テナントを結合します。

> [!IMPORTANT]
> ユーザーを作成したら、テナント間でユーザーを移動する自動メカニズムがサポートされていることはありません。 1 つの Office 365 テナントにドメインを追加する方法については、[Office 365 へのユーザーとドメインの追加に関するページ](/office365/admin/setup/add-domain/)を参照してください。

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Power BI に既にサインアップしているユーザーを削除するにはどうすればよいですか。

Power BI にサインアップする必要がなくなったユーザーが Power BI にアクセスできないようにする場合は、そのユーザーの Power BI ライセンスを削除できます。

1. [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/Home#/homepage)に移動します。

1. 左側のナビゲーション バーで、 **[ユーザー]**  >  **[アクティブ ユーザー]** の順に選択します。

1. ライセンスを削除するユーザーを見つけ、その名前を選択します。

    ユーザーのライセンスは、一括管理することもできます。 これを実行するには、複数のユーザーを選択し、 **[製品ライセンスを編集]** を選択します。

1. ユーザーの詳細ウィンドウで、 **[製品ライセンス]** の隣にある **[編集]** を選択します。

1. 自分のアカウントに適用するライセンスの内容に応じて、設定**Power BI (無料)** または**Power BI Pro**に**オフ**します。

1. **[保存]** を選択します。

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>新しいユーザーがいつテナントに参加したかを確認するにはどうすればよいですか。

このプログラムの一環として、テナントに参加したユーザーは、管理ダッシュ ボードで、アクティブなユーザー ウィンドウ内でフィルター処理できます固有のライセンスを割り当てられます。 この新しいビューを作成するには、次の手順のようにします。

1. [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/Home#/homepage)に移動します。

1. 左側のナビゲーション バーで、 **[ユーザー]**  >  **[アクティブ ユーザー]** の順に選択します。

1. **[ビュー]** メニューの **[カスタム ビューの追加]** を選択します。

1. 新しいビューに名前を付け、 **[割り当て済みの製品ライセンス]** で、 **[Power BI (無料)]** または **[Power BI Pro]** を選択します。

    ビューごとにライセンスを 1 つだけ選択できます。 組織内に **Power BI (無料)** のライセンスと **Power BI Pro** のライセンスがある場合は、2 つのビューを作成できます。

1. 他の必要な条件を入力した後、 **[追加]** を選択します。

1. 使用できますが、新しいビューを作成した後、**ビュー**メニュー。

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>他に何を準備する必要がありますはありますか。

パスワードのリセット要求が増える可能性があります。 このプロセスの詳細については、次を参照してください。[ユーザーのパスワード リセット](/office365/admin/add-users/reset-passwords)します。

テナントからのユーザーの削除は、Microsoft 365 管理センターの標準的なプロセスを使用して実行できます。 ただし、ユーザーが組織のアクティブなメール アドレスを引き続き使用する場合、すべてのユーザーがブロックされない限り、そのユーザーはテナントに再び参加できます。

### <a name="where-is-my-power-bi-tenant-located"></a>Power BI テナントの場所

Power BI テナントが、データ領域の詳細については、次を参照してください。 [Power BI テナントはどこにあるでしょうか。](service-admin-where-is-my-tenant-located.md)します。

### <a name="what-is-the-power-bi-sla"></a>Power BI SLA とは何ですか。

詳細については、Power BI SLA (サービス レベル アグリーメント) は、次を参照してください。、[ライセンス条項とドキュメント](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37)記事、**ライセンス**Microsoft ライセンス web サイトの「します。

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Power BI では高可用性とフェールオーバーはどのように処理されますか。

高可用性とフェールオーバーの詳細については、次を参照してください。 [Power BI の高可用性、フェールオーバー、およびディザスター リカバリーに関する FAQ](service-admin-failover.md)します。

## <a name="security-in-power-bi"></a>Power BI のセキュリティ

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI は、国、地域、および業界固有のコンプライアンス要件を満たしていますか。

Power BI のコンプライアンスの詳細については、[Microsoft セキュリティ センター](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx)を参照してください。

### <a name="how-does-security-work-in-power-bi"></a>Power BI のセキュリティはどのように機能していますか。

Microsoft では、Azure Active Directory などの Azure サービス上に構築される Office 365 の基盤に Power BI が構築されています。 Power BI のアーキテクチャの概要については、「[Power BI のセキュリティ](service-admin-power-bi-security.md)」をご覧ください。

## <a name="next-steps"></a>次の手順

[Power BI 管理ポータル](service-admin-portal.md)  
[Power BI 管理者の役割について](service-admin-role.md)  
[Power BI のセルフサービス サインアップ](service-self-service-signup-for-power-bi.md)  
[Power BI Pro を購入する](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium とは何ですか?](service-premium-what-is.md)  
[Power BI Premium の購入方法](service-admin-premium-purchase.md)  
[Power BI Premium ホワイト ペーパー](https://aka.ms/pbipremiumwhitepaper)  
[Power BI および Office 365 でのグループ管理](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Office 365 のユーザー アカウント管理](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Office 365 グループ管理](/office365/admin/email/create-edit-or-delete-a-security-group/)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

[1]: https://docs.microsoft.com/powershell/scripting/overview