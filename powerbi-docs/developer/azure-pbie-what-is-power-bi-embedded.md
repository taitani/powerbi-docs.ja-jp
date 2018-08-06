---
title: Azure Power BI Embedded の概要 | Microsoft Docs
description: Power BI Embedded は、ISV や開発者が Power BI の機能を使いやすくすることを目的としており、目を見張るようなビジュアル、レポート、ダッシュボードをアプリに簡単に追加できるようになっています。
author: markingmyname
ms.author: maghan
manager: kfile
ms.service: power-bi-embedded
ms.component: ''
ms.devlang: csharp, javascript
ms.topic: overview
ms.reviewer: ''
ms.date: 07/31/2018
ms.openlocfilehash: b46508aeca35769fb27324fb20f502ac66cb55ab
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2018
ms.locfileid: "39360556"
---
# <a name="what-is-power-bi-embedded-in-azure"></a>Azure の Power BI Embedded とは何か 

Power BI Embedded は、ISV や開発者が Power BI の機能を使いやすくすることを目的としています。 Power BI Embedded では Power BI の各種機能がシンプルになりました。目を見張るようなビジュアル、レポート、ダッシュボードをアプリに簡単に追加できます。 Microsoft Azure で開発されたアプリと同様に、機械学習と IoT を使用します。 ISV がナビゲーションが簡単なデータ探索をアプリで有効にすることで、ISV の顧客は十分な情報を得た上で迅速に意思決定できます。

> [!VIDEO https://www.youtube.com/embed/iEHfUuoZseo]

2017 年 5 月、Microsoft は Power BI サービスと Power BI Embedded サービスの統合を発表しました。 この統合により 1 つの API サーフェスが作られました。このサーフェスでは、両方のサービスの各種機能が一貫性をもって集められており、また、最新の機能にアクセスできます。 さらに、容量ベースの価格モデルを導入し、Power BI の使い方がシンプルになりました。

Power BI Embedded を利用することで、ISV や開発者は Power BI API を利用してアプリにインテリジェンスを埋め込むとき、さらに柔軟な手法を採用しています。 ISV や開発者は Microsoft の超一流の分析エンジンをアプリに組み込むことで開発労力を最小限に抑え、個性的なアプリを開発し、短期間で市場に投入できます。 同様に、開発者は視覚的分析機能を開発するより、顧客の要望を満たすソリューションに集中的に取り組むことに時間をかけられます。 また、Power BI Embedded では、使い慣れている開発環境内で作業できます (Visual Studio や Azure)。

Power BI Premium を利用して Power BI コンテンツを埋め込んだアプリをお持ちですか。 アプリを開発する ISV や開発者か、そのアプリを使用する組織は何も行う必要がありません。 開発者もお客様も中断なくアプリの使用を続けられます。 Power BI Workspace Collections で開発したアプリをお持ちで、統合 API サーフェスや新しい容量ベースの Azure SKU にご関心がございましたら、移行ガイドをご覧ください。

## <a name="comparing-power-bi-embedded-with-power-bi-premium"></a>Power BI Embedded と Power BI Premium の比較

**Power BI Embedded** は、顧客のためにアプリケーションを開発している独立系ソフトウェア ベンダー (ISV) と開発者向けです。 そのようなサービスを自分で開発しなくても、アプリケーション データを視覚化できるサードパーティ ビジネス インテリジェンス サービスとして利用できます。 Power BI Embedded は PaaS (サービスとしてのプラットフォーム) 分析ソリューションです。開発者は顧客向けのアプリケーションにレポートやダッシュボードを埋め込むことができます。 **Power BI Premium** は SaaS (サービスとしてのソフトウェア) 分析ソリューションです。組織は最も重要なビジネス データを 1 つの画面で見ることができます。 

[Power BI Embedded](https://azure.microsoft.com/pricing/details/power-bi-embedded/) は従量課金制ですが、[Power BI Premium](https://powerbi.microsoft.com/calculator/) は月額料金制です。 この[動画](https://www.youtube.com/watch?v=0y2oJikC6Xc&t=0s&list=PLv2BtOtLblH1dQPV49Ni12olDcUoW-GEl&index=3)をご覧ください。両者の違いをご理解いただけます。

## <a name="easy-to-use-tools"></a>使いやすいツール

Power BI Embedded を利用すれば、開発者が最も得意とすること、すなわち、優れたアプリを開発することに集中できます。 既にお持ちのツールやスキルを Power BI Embedded と共に利用して管理したり、開発したりできます。

* [**Azure Portal**](https://portal.azure.com/): すべての Azure サービスを管理するための Web ベースのアプリケーション
* [**Visual Studio Code**](https://code.visualstudio.com/docs): Windows、macOS、Linux 向けのオープンソースのコード エディターであり、無料でダウンロードできます。拡張機能をサポートします
* [**Power BI Desktop**](https://powerbi.microsoft.com/desktop/): 機能が豊富な視覚的分析付き対話型レポートを作成するためのツールです。無料でダウンロードできます

REST API を利用する Power BI Embedded では、あらゆる言語で開発できます。

## <a name="engage-with-the-power-bi-engineering-team"></a>Power BI エンジニアリング チームと交流する

* [コミュニティ](https://community.powerbi.com/): Power BI について質問する
* [Power BI のアイデア](https://ideas.powerbi.com): 機能を要望する/機能に投票する
* [Reddit](https://www.reddit.com/r/PowerBI/): Power BI について話し合う

## <a name="next-steps"></a>次の手順

容量ノードの詳細については、[価格設定ページ](https://azure.microsoft.com/pricing/details/power-bi-embedded/)を参照してください。

Power BI Embedded 容量の作成方法については、「[Create Power BI Embedded capacity in the Azure portal](azure-pbie-create-capacity.md)」 (Azure Portal で Power BI Embedded 要領を作成する) を参照してください。

Power BI コンテンツの埋め込みについては、[Power BI ダッシュボード、レポート、およびタイルを埋め込む方法](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/)に関するページをご覧ください。
