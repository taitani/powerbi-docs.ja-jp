---
title: "Power BI Embedded に関してよく寄せられる質問"
description: "Power BI Embedded についてよく寄せられる質問とその回答の一覧です。"
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
ms.date: 01/15/2018
ms.author: maghan
ms.openlocfilehash: 9d387208b1ace0b0f0fd700b471e07e3b2584883
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded に関してよく寄せられる質問

* 他の質問がある場合は、[Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
* それでも解決しない場合は、 [Power BI のサポート ページ](https://powerbi.microsoft.com/support/)をご覧ください。

## <a name="general"></a>全般

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded とは何ですか?

Microsoft Power BI Embedded を利用すれば、アプリケーション開発者は、完全にインタラクティブな優れたレポート、ダッシュボード、タイルをアプリケーションに組み込むことができます。データの視覚化やコントロールを自分で一から構築する必要がなく、時間と費用が節約されます。

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded の対象者は誰ですか?

独自のアプリケーションを開発している開発者やソフトウェア企業。ISV (Independent Software Vendor) と呼ばれています。

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded と Power BI サービスの違いは何ですか?

アプリケーションを開発するとき、お客様の意思決定に役立てるよう、アプリケーションにビジュアルを組み込みたいが、分析ソリューションを一から構築することは望まない ISV または開発者を Power BI Embedded は対象としています。 埋め込み分析では、ビジネス ユーザーはビジネス データにアクセスしてクエリを実行し、アプリケーション内でこのデータを利用してインサイトを生成できます。

一方、Power BI は SaaS (サービスとしてのソフトウェア) 分析ソリューションです。組織はその最も重要なビジネス データを 1 つのビューで見ることができます。

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium と Power BI Embedded の違いは何ですか?

Power BI Premium は、組織、パートナー、顧客、サプライヤーを 1 つのビューで見ることができる完全 BI ソリューションを望む企業向けです。 Power BI Premium は組織の意思決定に役立ちます。 Power BI Premium は SaaS 製品であり、Power BI ポータル、モバイル アプリ、社内で開発したアプリを介してコンテンツを利用するための機能が付いています。

Power BI Embedded は、アプリケーションの開発にビジュアルの埋め込みを利用したい ISV または開発者向けです。 Power BI Embedded はアプリケーション開発者向けであり、そのアプリケーションを入手すれば、組織の内外を問わず、誰でも Power BI Embedded 容量に保存されているコンテンツを利用できます。Power BI Embedded は顧客の意思決定に役立ちます。 Power BI Embedded 容量に入っているコンテンツは、ワンクリック Web 公開やワンクリック SharePoint 公開では共有できません。SSRS レポートには対応していません。

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Power BI Premium と Power BI Embedded を比較して、どのような状況でどちらを購入するべきか、Microsoft は勧めていますか?

企業は企業向けのセルフサービス クラウド BI ソリューションである Power BI Premium を購入するように、ISV はクラウド駆動の埋め込み分析コンポーネントである Power BI Embedded を購入するように Microsoft は勧めています。 しかしながら、顧客が購入する製品については何の制約もありません。

ISV (通常、大規模な ISV) が P SK を利用し、事前パッケージ済みの Power BI サービスだけの機能を組織内に与えたり、アプリケーションに埋め込んだりする場合もあります。 もちろん、基幹業務アプリケーションを開発し、それに分析を埋め込みたいが、事前パッケージ済み Power BI サービスは必要としない企業が A SKU の利用を決める場合もあります。

### <a name="how-many-embed-tokens-can-i-create"></a>埋め込みトークンはいくつ作成できますか?

PRO ライセンスの埋め込みトークンは、開発と開発テストのためのものです。そのため、Power BI マスター アカウントで生成できる埋め込みトークンの数には限りがあります。 運用環境で埋め込むには、[容量を購入する](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)必要があります。 容量を購入する場合、生成できる埋め込みトークンの数には上限がありません。

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Power BI Embedded は Azure でいつから利用できますか?

Power BI Embedded は現在ご利用いただけます。

## <a name="technical"></a>技術的な質問

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-em-skus-in-office-365"></a>Azure の A SKU と Office 365 の EM SKU の違いは何ですか?

PowerBI.com は、ソーシャル コラボレーションや電子メール サブスクリプションなど、多彩な機能が SaaS サービスに含まれる企業向けソリューションです。

Power BI Embedded は一連の API であり、開発者はこれを利用し、PaaS (サービスとしてのプラットフォーム) で埋め込み分析ソリューションを開発できます。 埋め込み分析シナリオの場合、ISV や開発者がその埋め込み分析ソリューション コンテンツやテナント レベル設定の管理を支援する目的で PowerBI.com を使用するべきです。

それぞれを利用する場合の違いについて、部分的にまとめたものが次の一覧です。

|おすすめ  |Power BI Embedded<br>(A SKU) |Power BI Premium 容量<br>(EM SKU)  |
|---------|---------|---------|
|Power BI アプリ ワークスペースからアーティファクトを埋め込む     |Azure 容量 |Office 365 容量 |
|レポートの利用に必要な Power BI ライセンス |いいえ  |はい |
|埋め込みアプリケーションで Power BI レポートを使用する |はい  |はい |
|SharePoint で Power BI レポートを利用する |いいえ |はい |
|Teams で Power BI レポートを利用する |いいえ |はい |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI は現在、埋め込みに 3 つの SKU を用意しています。A SKU、EM SKU、P SKU です。 私のシナリオでは、どちらを購入するべきですか?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|購入     |Azure Portal |Office |Office |
|ユース ケース |* 独自のアプリケーションにコンテンツを埋め込む |* 独自のアプリケーションにコンテンツを埋め込む<br>* PowerBI.com 外の Power BI FREE ユーザーとコンテンツを共有し、他の SaaS アプリケーションに埋め込む (SharePoint、Teams) |* 独自のアプリケーションにコンテンツを埋め込む<br>* PowerBI.com 外の Power BI FREE ユーザーとコンテンツを共有し、他の SaaS アプリケーションに埋め込む (SharePoint、Teams)<br>* PowerBI.com 経由で Power BI FREE ユーザーとコンテンツを共有する  |
|課金 |1 時間ごと |月単位 |月単位 |
|コミットメント  |コミットメントなし |年単位  |月単位/年単位 |
|差別化 |柔軟性に優れ、Azure Portal で、あるいは API 経由でリソースを拡大縮小したり、停止/再開したりできる  |SharePoint Online と Microsoft Teams にコンテンツを埋め込むために使用可能 |アプリケーションの埋め込みを結合し、同じ容量で Power BI Service を使用する |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure で PBIE 容量を作成するための前提条件は何ですか?

- 組織のディレクトリにサインインする必要があります (MSA アカウントはサポートされていません)。
- Power BI テナントを用意する必要があります。すなわち、ディレクトリの少なくとも 1 名のユーザーを Power BI に登録している必要があります。 
- 組織のディレクトリに Azure サブスクリプションを用意する必要があります。

### <a name="how-can-i-monitor-capacity-consumption"></a>容量の利用を監視する方法は?

Azure による監視が短期ロードマップに記載されています。 Azure リソースの Power BI Embedded には、健全性や使用状況を示す監視 KPI が含まれています。

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>私の容量はアプリの利用に合わせて調整する目的で自動的に拡大縮小しますか?

現在、拡大縮小は自動化されていませんが、API はすべていつでも拡大縮小できます。

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Power BI Embedded の認証モデルは何ですか?

Power BI Embedded は引き続き、マスター ユーザー (Power BI Pro のライセンスが与えられた指名ユーザー) の認証に Azure AD を利用します。Power BI 内でアプリケーションを認証します。

アプリケーション ユーザーの認証と承認は ISV が実装します。ISV はそのアプリケーションに独自の認証を実装できます。

Azure AD テナントを既に用意している場合、既存のディレクトリを利用できます。あるいは、埋め込みアプリケーション コンテンツ セキュリティに新しい Azure AD テナントを作成できます。

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded とその他の Azure サービスの違いは何ですか?

ISV/開発者は Azure で Power BI Embedded を購入する前に Power BI アカウントを用意する必要があります。 Power BI Embedded のデプロイ リージョンはお使いの Power BI アカウントによって決まります。 Azure の Power BI Embedded リソースを次の目的で管理します。

* 拡大/縮小
* 容量管理者の追加
* サービスの一時停止/再開

PowerBI.com を利用し、Power BI Embedded 容量のワークスペースの割り当て/割り当て解除を行います。

### <a name="what-deploy-regions-are-supported"></a>どのようなデプロイ リージョンがサポートされていますか?

オーストラリア南東部、ブラジル南部、カナダ中央、米国東部 2、インド西部、東日本、米国中北部、北ヨーロッパ、米国中南部、東南アジア、英国南部、西ヨーロッパ、米国西部、米国西部 2 です。

## <a name="licensing"></a>ライセンス

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded の購入方法は?

Power BI Embedded は Azure からお買い求めいただけます。

### <a name="how-power-bi-embedded-be-metered"></a>Power BI Embedded の課金方法は?

Power BI Embedded には時間単位のメーターが用意されています。

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded の使用状況は請求書にどのように表示されますか?

Power BI Embedded は、デプロイしたノードの種類に基づき、予測可能な時間レートで課金されます。 リソースが有効である限り、使用していなくても課金されることにご注意ください。 課金を停止するには、自発的にリソースを一時停止する必要があります。 Azure または ARM API から一時停止できます。

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Power BI Premium を既に購入しているとき、Azure で Power BI Embedded の機能を利用したいと考えた場合、どうなりますか?

購入した既存の Power BI Premium に対して現在の契約期間終了まで引き続き支払い、終了時点で必要に応じて、購入した他のサービスに切り替えることができます。

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded にアクセスするには Power BI Premium を購入する必要がありますか?

いいえ。Power BI Embedded には、デプロイし、ソリューションを顧客に配信するために必要な Azure ベースの容量が含まれています。

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded に Power BI Pro のライセンスを必要とするのはどのようなユーザーですか? また、その理由は?

Power BI ワークスペースにレポートを追加する必要があるアナリスト、REST API を使用する必要がある開発者、Power BI のテナントと容量を管理する必要があるテナント管理者は Power BI Pro ライセンスを用意する必要があります。

Power BI Embedded では、埋め込みコンテンツの管理と検証に Power BI ポータルを利用できるため、PowerBI.com 内でアプリを認証し、正しいリポジトリのレポートにアクセスするには、Power BI Pro ライセンスが必要です。

### <a name="can-i-get-started-for-free"></a>無料で始めることはできますか?

はい。Power BI Embedded の [Azure クレジット](https://azure.microsoft.com/free/)をご利用いただけます。

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure で Power BI Embedded を試してみることはできますか?

Power BI Embedded は Azure の一部であるため、[Azure 登録時に受け取った $200 のクレジット](https://azure.microsoft.com/free/)でこのサービスを利用できます。

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded の購入コミットメントは何ですか? 

顧客は時間単位で使用方法を変更できます。 Power BI Embedded サービスには、月または年単位のコミットメントはありません。

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>Power BI Embedded はどこで利用できますか? 米国政府は? ドイツは? 中国は? いつ利用できますか?

Power BI Embedded は GA の Azure 商用クラウドで利用できるようになります。  ソブリン クラウドは将来的に追加される予定です。

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>非営利団体や教育機関は Power BI Embedded を利用できますか?

非営利団体や教育機関は Azure を購入できます。 Azure では、非営利団体や教育機関に特別料金は設定されていません。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
