---
title: "Power BI レポート サーバーの概要"
description: "Power BI レポート サーバーのインストール方法について説明します。 "
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
ms.date: 3/5/2018
ms.author: maghan
ms.openlocfilehash: 88aa347a5e6feae969cf9b32e0e2177114efc757
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2018
---
# <a name="get-started-with-power-bi-report-server"></a>Power BI レポート サーバーの概要
Power BI レポート サーバーが提供するすぐに使用できるツールとサービスを使用して、Power BI レポート、モバイル レポート、およびページ分割されたレポートをオンプレミスで作成、展開、管理します。

## <a name="create-deploy-and-manage-reports"></a>レポートの作成、展開、および管理
Power BI レポート サーバーとは、顧客がレポートを作成、展開、管理した後、それらを該当するユーザーに、Web ブラウザーやモバイル デバイスで表示したり、または電子メールで送信するなどのさまざまな方法で配布するために独自の施設内に展開するソリューションです。

Power BI レポート サーバーは、次の製品スイートを提供しています。

* どの最新ブラウザーでも表示可能な最新の Web ポータル。 Web ポータルでは、レポートおよび KPI を整理して表示することができます。 ポータルには Excel ブックを格納することもできます。
* Power BI Desktop で作成された Power BI レポート。お使いの環境で Web ポータル内に表示できます。
* ページ分割されたレポート。作成ツールを使用して、現代的な外観のレポートを作成できます。
* さまざまなデバイスに対応し、さまざまな方法で保持できる柔軟なレイアウトのモバイル レポート。

それぞれについて詳しく説明します。

### <a name="whats-new-in-power-bi-report-server"></a>Power BI レポート サーバーの新機能
これらのソースには、Power BI レポート サーバーの新機能に関する最新情報があります。

* [Power BI レポート サーバーの新機能](whats-new.md)
* [Microsoft Power BI ブログ](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services チームのブログ](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube の YouTube チャネル](https://aka.ms/guyinacube)

## <a name="web-portal"></a>Web ポータル
![](media/get-started/web-portal.png)

Power BI レポート サーバーのエンドユーザーのための入口は、どの最新ブラウザーでも表示可能な最新の Web ポータルです。 新しいポータルでは、すべてのレポートと KPI にアクセスできます。

独自のカスタム [ブランド](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal) を Web ポータルに適用できます。 また、Web ポータルで直接 KPI を作成できます。 KPI は、レポートを開かなくても、ブラウザーでひとめでわかる主要なビジネス指標を示すことができます。

Web ポータルのコンテンツは、次の種類別に分類されています。Power BI レポート、モバイル レポート、ページ分割されたレポート、および KPI に加え、レポートの構成要素として使用する Excel ブック、共有データセット、および共有データ ソースです。 Web ポータルでは、それらを従来のフォルダー階層で安全に格納して管理できます。 お気に入りのタグを付けて、コンテンツを管理できます (該当するロールを持っている場合)。

また、レポート処理をスケジュールしたり、オンデマンドでレポートにアクセスしたり、新しい Web ポータルでパブリッシュされたレポートをサブスクライブできます。

Web ポータルの詳細は、[こちら](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)をご覧ください。

## <a name="power-bi-reports"></a>Power BI レポート
![](media/get-started/powerbi-reports.png)

Power BI レポートは、データセットのマルチパースペクティブ表示で、視覚化によってデータセットからのさまざまな発見や洞察を表します。  レポートでは、単独の視覚化を使用することも、各ページでさまざまな視覚化を使用することもできます。 職務に応じて、レポートの作成者になる場合と、レポートのコンシューマー、つまり使用者になる場合があります。

レポートは、単一のデータセットに基づいています。 レポート内の視覚化は、それぞれがひとかたまりの情報を表します。 視覚化は静的なものではありません。データを追加および削除することや、視覚化の種類を変更することができます。また、フィルターやスライサーを適用してデータを詳しく考察し、洞察を得たり、答えを見つけたりすることもできます。 レポートはダッシュボードと同様に、あるいはそれ以上に、高度な対話機能とカスタマイズ機能を備え、基になっているデータが変化すると視覚化が更新されます。

## <a name="paginated-reports"></a>ページ分割されたレポート
![](media/get-started/paginated-reports.png)

ページ分割されたレポートは、多くのデータがある場合、テーブル内に多くの行がある場合、およびレポートに多くのページがある場合にページ分割される文書形式のレポートです。 これは、PDF や Word などの印刷用に最適化された固定レイアウトの完璧なピクセルのドキュメントを生成するのに適しています。

[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) で[レポート ビルダー](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016)またはレポート デザイナーを使用して、現代的な外観のレポートを作成できます。

## <a name="report-server-programming-features"></a>Report Server のプログラミング機能
Power BI レポート サーバーのプログラミング機能を利用すると、レポート作成機能を拡張してカスタマイズしたり、API を使用してデータとレポート処理をカスタム アプリケーションに統合または拡張することができます。

詳細は、「[Report Server developer documentation](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation)」 (Report Server の開発者向けドキュメント) をご覧ください。

## <a name="next-steps"></a>次の手順
[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[クイックスタート: Power BI レポート サーバーをインストールする](quickstart-install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。


