---
title: "クイックスタート: Power BI レポート サーバーをインストールする"
description: "Power BI レポート サーバー自体のインストールはすぐに終わります。 ダウンロードし、インストールして構成し、実行できるようになるまで、数分で終わります。"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 01/29/2018
ms.author: maghan
ms.openlocfilehash: 3ddf8870fd4fb3186ff884220fc4a7de7632c78d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>クイックスタート: Power BI レポート サーバーをインストールする
Power BI レポート サーバー自体のインストールはすぐに終わります。 ダウンロードし、インストールして構成し、実行できるようになるまで、数分で終わります。

ここでは、新しいサーバーで Report Server を稼働させる場合のインストール方法について簡単に説明します。 レポート サーバーのインストールの詳細については、「[Power BI レポート サーバーのインストール](install-report-server.md)」をご覧ください。

 **ダウンロード** ![ダウンロード](media/quickstart-install-report-server/download.png "ダウンロード")

Power BI Report Server をダウンロードするには、「[Power BI Report Server によるオンプレミスでのレポート作成](https://powerbi.microsoft.com/report-server/)」に移動します。 

Microsoft ダウンロード センターに移動して [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (Power BI Report Server 向けに最適化 - 2017 年 10 月) をダウンロードします。

![ヒント](media/quickstart-install-report-server/fyi-tip.png "ヒント") 最新のリリース ノートについては、「[Power BI Report Server - Release notes](release-notes.md)」 (Power BI レポート サーバー - リリース ノート) をご覧ください。

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>始める前に
Power BI レポート サーバーをインストールする前に、「[Power BI レポート サーバーをインストールするためのハードウェアとソフトウェアの要件](system-requirements.md)」を確認することをお勧めします。

## <a name="step-1-download"></a>手順 1: ダウンロードする
Power BI レポート サーバーのインストール ファイルをローカルにダウンロードします。 Power BI レポート サーバーをダウンロードするには、[Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?linkid=839351)にアクセスします。

![Power BI レポート サーバーのダウンロード](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>手順 2: インストーラーを実行する
ダウンロードした PowerBIReportServer.exe ファイルを実行し、インストール画面の手順に従います。 インストール パスとインストールするエディションを選択できます。 有効期限が 180 日間の評価版または Developer Edition を選択するか、プロダクト キーを入力します。

![Power BI レポート サーバーのインストール](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>手順 3: サーバーを構成する
インストールが完了したら、構成マネージャーを実行して、サーバーのセットアップを完了します。 ReportServer カタログ データベースを作成し、Web ポータルと Web サービスの URL を確認する必要があります。

![Power BI レポート サーバーの構成](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>手順 4: Web ポータルを参照する
構成が終わったら、ブラウザーを開いてサーバーの Web ポータルを参照できます。 既定では、これは `http://localhost/reports` になります。 また、どの種類のファイアウォールにもブロックされないという前提で、localhost を使用する代わりに、既定でコンピューター名を使用して参照できます。

![Power BI レポート サーバーの Web ポータル](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>次の手順
[管理者向けハンドブック](admin-handbook-overview.md)  
[レポート サーバーのプロダクト キーを検索する方法](find-product-key.md)  
[Power BI レポート サーバーのインストール](install-report-server.md)  
[Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール](install-powerbi-desktop.md)  
[Power BI レポート サーバーのブラウザーのサポート](browser-support.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

