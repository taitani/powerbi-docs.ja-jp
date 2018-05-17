---
title: Power BI レポート サーバーをインストールするためのハードウェアとソフトウェアの要件
description: ここでは、Power BI レポート サーバーをインストールして実行するためのハードウェアとソフトウェアの最小要件について説明します。
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 26710c6a19ea4f9389718bea51ffff82dfadd3eb
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Power BI レポート サーバーをインストールするためのハードウェアとソフトウェアの要件
ここでは、Power BI レポート サーバーをインストールして実行するためのハードウェアとソフトウェアの最小要件について説明します。

## <a name="processor-memory-and-operating-system-requirements"></a>プロセッサ、メモリ、およびオペレーティング システムの要件
| コンポーネント | 要件 |
| --- | --- |
| .NET Framework |4.6<br><br>.NET Framework は、「[Microsoft .NET Framework 4.6 (Web Installer) for Windows](http://support.microsoft.com/kb/3045560)」(Windows 用 Microsoft.NET Framework 4.6 (Web インストーラー)) から手動でインストールできます。<br/><br/> .NET Framework 4.6 の詳細情報、推奨事項、およびガイダンスについては、「[.NET Framework 配置ガイド (開発者向け)](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx)」をご覧ください。<br/><br/>Windows 8.1 および Windows Server 2012 R2 では、.NET Framework 4.6 をインストールする前に、[KB2919355](http://support.microsoft.com/kb/2919355) をインストールする必要があります。 |
| ハード ディスク |Power BI レポート サーバーには、最低 1 GB の使用可能なハード ディスク空き領域が必要です。<br><br>レポート サーバーのデータベースをホストしているデータベース サーバーには、追加の領域が必要です。 |
| メモリ |**最低:** 1 GB<br/><br/> **推奨:** 4 GB 以上 |
| プロセッサ速度 |**最低:** x64 プロセッサ: 1.4 GHz<br/><br/> **推奨:** 2.0 GHz 以上 |
| プロセッサの種類 |x64 プロセッサ: AMD Opteron、AMD Athlon 64、Intel Xeon (Intel EM64T サポート付き)、Intel Pentium IV (EM64T サポート付き) |
| オペレーティング システム |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Power BI Report Server をインストールできるのは x64 プロセッサだけです。
> 
> 

## <a name="database-server-version-requirements"></a>データベース サーバーのバージョン要件
SQL Server は、レポート サーバー データベースをホストするために使用します。 SQL Server データベース エンジンのインスタンスは、ローカルにもリモートにも指定できます。 レポート サーバー データベースをホストするために使用できる SQL Server データベース エンジンのサポートされているバージョンを次に示します。

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

リモート コンピューターにレポート サーバー データベースを作成するには、ネットワーク アクセスが可能なドメイン ユーザー アカウントまたはサービス アカウントを使用する接続を構成する必要があります。 リモートの SQL Server インスタンスを使用する場合は、SQL Server インスタンスへの接続に、レポート サーバーでどの資格情報を使用するかをよく検討してください。 詳細については、「[Configure a Report Server Database Connection](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)」(レポート サーバー データベース接続を構成する) を参照してください。

## <a name="considerations"></a>考慮事項
Power BI レポート サーバーは、既定値をインストールして、レポート サーバーの動作に必要なコア設定を構成します。 次の要件があります。

* セットアップが終了した後、レポート サーバー用にデータベースを構成する前に、SQL Server データベース エンジンを使用できる状態にする必要があります。 データベース エンジンのインスタンスは、Reporting Services Configuration Manager が作成するレポート サーバー データベースをホストします。 データベース エンジンは、実際のセットアップ エクスペリエンスには必要ありません。
* セットアップの実行に使うユーザー アカウントは、ローカル Administrators グループのメンバーである必要があります。
* Reporting Services Configuration Manager に使うユーザー アカウントには、レポート サーバー データベースをホストするデータベース エンジン インスタンスのデータベースにアクセスしたり、インスタンスにデータベースを作成したりするためのアクセス許可が必要です。
* セットアップでは、既定値を使用して、レポート サーバーと Web ポータルにアクセスする URL を予約できる必要があります。 既定値は、ポート 80、強力なワイルドカード、および **ReportServer** と **Reports** の形式の仮想ディレクトリ名です。

## <a name="read-only-domain-controller-rodc"></a>読み取り専用ドメイン コントローラー (RODC)
 レポート サーバーは読み取り専用ドメイン コント ローラー (RODC) が存在する環境にインストールできますが、Reporting Services が正常に機能するには、読み取り/書き込み可能なドメイン コントローラーへのアクセスが必要です。 Reporting Services が RODC にしかアクセスできない場合は、サービスを管理しようとするとエラーが発生する可能性があります。

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI レポートおよび Analysis Services のライブ接続
表形式または多次元インスタンスに対してライブ接続を使用することはできません。 Analysis Services サーバーが正常に動作するには、適切なバージョンとエディションを満たす必要があります。

| **サーバーのバージョン** | **必要な SKU** |
| --- | --- |
| 2012 SP1 CU4 以降 |Business Intelligence と Enterprise SKU |
| 2014 |Business Intelligence と Enterprise SKU |
| 2016 以降 |Standard SKU 以上 |

## <a name="next-steps"></a>次の手順
[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[Power BI レポート サーバーのインストール](install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

