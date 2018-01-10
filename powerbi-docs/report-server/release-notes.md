---
title: "Power BI レポート サーバーのリリース ノート"
description: "このトピックでは、Power BI レポート サーバーの制限事項と問題について説明します。"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: aa0f8870396980edfdb85739e0459c365d1e2163
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2018
---
# <a name="power-bi-report-server-release-notes"></a>Power BI レポート サーバーのリリース ノート
このトピックでは、Power BI レポート サーバーの制限事項と問題について説明します。

Power BI Report Server および Power BI Report Server 向けに最適化された Power BI Desktop をダウンロードするには、「[Power BI Report Server によるオンプレミスでのレポート作成](https://powerbi.microsoft.com/report-server/)」を参照してください。

## <a name="october-2017"></a>2017 年 10 月
* Power BI レポートにおけるインポートされたデータのサポート
* Web ポータル内で Excel ブックを表示する機能。 これは Office Online Server を構成することで行われます。
* 新しい Power BI のテーブルとマトリックス ビジュアルのサポート。
* REST API のサポート

## <a name="june-2017"></a>2017 年 6 月
* 2017 年 6 月の新しい項目はありません。

## <a name="may-2017"></a>2017 年 5 月
* Power BI レポートを Power BI レポート サーバーで使用できるようにするには、Power BI レポート サーバー向けに最適化された Power BI Desktop でレポートを作成する必要があります。 Power BI Desktop は、このページの上部にあるダウンロード リンクからダウンロードできます。
* Power BI レポートでは、Analysis Services へのライブ接続のみがサポートされます (表形式または多次元)。
* R のビジュアルはサポートされません。

**問題と顧客への影響:** 同じコンピューターに SQL Server Reporting Services と Power BI レポート サーバーの両方があり、いずれか一方をアンインストールすると、レポート サーバーの構成マネージャーで残ったレポート サーバーに接続できなくなります。

**回避策** この問題を回避するには、いずれかのサーバーをアンインストールした後に次の操作を実行する必要があります。

1. 管理者モードでコマンド プロンプトを起動します。
2. 残りのレポート サーバーがインストールされているディレクトリに移動します。
   
    *Power BI レポート サーバーの既定の場所: C:\Program Files\Microsoft Power BI Report Server*
   
    *SQL Server Reporting Services の既定の場所: C:\Program Files\Microsoft SQL Server Reporting Services*
3. 次のフォルダーに移動します。 これは、残っているレポート サーバーに応じて、*SSRS* または *PBIRS* のいずれかになります。
4. WMI フォルダーに移動します。
5. 次のコマンドを実行します。
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    次のエラーは、表示されても無視できます。
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>次の手順
[Power BI レポート サーバーの新機能](whats-new.md)  
[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[クイックスタート: Power BI レポート サーバーをインストールする](quickstart-install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

