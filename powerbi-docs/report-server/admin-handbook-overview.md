---
title: 管理の概要、Power BI Report Server
description: この記事では、Power BI Report Server の管理の概要について説明します。Power BI Report Server は、Power BI レポート、モバイル レポート、およびページ分割されたレポートを格納および管理するためのオンプレミスの場所です。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: maghan
ms.openlocfilehash: 228402dd2137f0cf2f3d480ff1acee10d2f28c51
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34296390"
---
# <a name="admin-overview-power-bi-report-server"></a>管理の概要、Power BI Report Server
この記事では、Power BI Report Server の管理の概要について説明します。Power BI Report Server は、Power BI レポート、モバイル レポート、およびページ分割されたレポートを格納および管理するためのオンプレミスの場所です。 この記事では、Power BI Report Server の計画、デプロイ、管理の概念について説明します。

![](media/admin-handbook-overview/admin-handbook.png)



## <a name="installing-and-migration"></a>インストールと移行
Power BI レポート サーバーの使用を開始するには、インストールする必要があります。 このタスクを処理できるようにするための情報を提供します。

Power BI レポート サーバーのインストール、アップグレードまたは移行を開始する前に、レポート サーバーの[システム要件](system-requirements.md)をご覧ください。

### <a name="installing"></a>インストール
新しい Power BI レポート サーバーを展開する場合は、次のドキュメントが役立ちます。 

[Power BI レポート サーバーのインストール](install-report-server.md)

### <a name="migration"></a>移行
SQL Server Reporting Services の一括アップグレードはありません。 Power BI Report Server にする既存の SQL Server Reporting Services インスタンスがある場合は、それを移行する必要があります。 移行を実行する理由は他にもあります。 詳細については、移行のドキュメントを確認してください。

[レポート サーバー インストールの移行](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>レポート サーバーを構成する
レポート サーバーを構成する際には、多数のオプションがあります。 SSL を使用するか、 電子メール サーバーを構成しているか、 Power BI サービスを統合して視覚エフェクトをピン留めするかなどです。

構成の大部分は、Report Server の構成マネージャー内で行われます。 詳細については、[構成マネージャー](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode)のドキュメントで確認してください。

## <a name="security"></a>セキュリティ
セキュリティと保護は、すべての組織にとって重要です。 認証、承認、役割およびアクセス許可については、[セキュリティ](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection) ドキュメントで学ぶことができます。

## <a name="next-steps"></a>次の手順
[Power BI レポート サーバーのインストール](install-report-server.md)  
[レポート サーバーのプロダクト キーを検索する](find-product-key.md)  
[Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール](install-powerbi-desktop.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

