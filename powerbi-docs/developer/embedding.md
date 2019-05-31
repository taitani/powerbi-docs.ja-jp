---
title: Power BI を使用した埋め込み分析
description: Power BI には、ダッシュボードとレポート用の埋め込み分析をアプリケーションで利用するための API があります。 PaaS 環境と SaaS 環境の両方で、埋め込み分析ソフトウェア、埋め込み分析ツール、または埋め込みビジネス インテリジェンス ツールを使用した、Power BI を使用した埋め込みの詳細について説明します。
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051062"
---
# <a name="embedded-analytics-with-power-bi"></a>Power BI を使用した埋め込み分析

Power BI サービス (SaaS) と Azure (PaaS) の Power BI Embedded サービスには、ダッシュボードとレポートの埋め込み用の API があります。 コンテンツを埋め込むときにこれにアクセスできますダッシュ ボード、ゲートウェイ、アプリ ワークスペースなどの最新の Power BI 機能。

[埋め込みセットアップ ツール](https://aka.ms/embedsetup)に移動し、すばやく開始してサンプル アプリケーションをダウンロードすることができます。

適切なソリューションを選択します。

* [組織向けの埋め込み](embedding.md#embedding-for-your-organization)を使って、Power BI サービスを拡張することができます。 これを行うには、実装、 [、組織の埋め込み](https://aka.ms/embedsetup/UserOwnsData)ソリューション。
* [顧客向けの埋め込み](embedding.md#embedding-for-your-customers)ダッシュ ボードと Power BI アカウントを持っていないユーザーにレポートを埋め込むことができます。 これを行うには、実装、[顧客向けの埋め込み](https://aka.ms/embedsetup/AppOwnsData)ソリューション。

![PBIE サンプル](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>Api を使用します。

Power BI コンテンツを埋め込むための 2 つの主なシナリオがあります。
- (Power BI ライセンスを所有) する組織のユーザー向けの埋め込み。 
 
- ユーザーと Power BI ライセンスはありません必要があるお客様向けの埋め込み。 

[Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)両方のシナリオに対応できます。

Power BI ライセンスのない顧客やユーザーの場合、同じ API を使用して、組織用と顧客用のダッシュボードやレポートをカスタム アプリケーションに埋め込むことができます。 お客様は、アプリケーションで管理されるデータを参照してください。 また、追加のオプションを表示のある組織の Power BI ユーザー*データ*Power BI で直接、または埋め込みアプリケーションのコンテキストでします。 埋め込みのニーズに合わせて JavaScript や REST API を最大限に活用できます。

埋め込みのしくみを理解するを参照してください、 [JavaScript 埋め込みサンプル](https://microsoft.github.io/PowerBI-JavaScript/demo/)します。

## <a name="embedding-for-your-organization"></a>組織向けの埋め込み

**組織向けの埋め込み**を使って、Power BI サービスを拡張することができます。 この埋め込みコンテンツを表示する Power BI サービスに、アプリケーションのユーザー サインインが必要です。 サインインした組織のユーザーは、自分が所有しているか、誰かが Power BI サービスで自分と共有しているダッシュボードとレポートにのみアクセスできます。

組織の埋め込みの例では内部のアプリケーションをなどがあります[SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/)、 [(管理者権限が必要)、Microsoft Teams の統合](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/)、および[Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

組織に埋め込むを参照してください。[チュートリアル。組織のアプリケーションに Power BI コンテンツを埋め込む](embed-sample-for-your-organization.md)します。

編集や保存などのセルフサービス機能は、Power BI ユーザー向けの埋め込みの際に [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) を介して使用できます。

進めることができます、[埋め込みセットアップ ツール](https://aka.ms/embedsetup/UserOwnsData)を開始し、組織のレポートの統合について説明するサンプル アプリケーションをダウンロードします。

## <a name="embedding-for-your-customers"></a>顧客向けの埋め込み

**顧客向けの埋め込み**ダッシュ ボードと Power BI アカウントを持っていないユーザーにレポートを埋め込むことができます。 この埋め込みとも呼ばれますは*Power BI Embedded*します。

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md)は、 **Microsoft Azure**すばやくにより独立系ソフトウェア ベンダー (Isv)、および開発者サービス、アプリケーションにビジュアル、レポート、およびダッシュ ボードを埋め込みます。 容量に基づいて時間単位の従量制課金モデルを使ってこの埋め込みは行われます。

![顧客向けの埋め込みの埋め込みフロー](media/embedding/powerbi-embed-flow.png)

Power BI Embedded は ISV とその開発者、顧客に対して利点があります。 たとえば、ISV は、Power BI Desktop を使用して無料でビジュアルの作成を開始できます。 ビジュアル分析機能の開発作業を最小限に抑えでは、Isv は市場に時間が短縮され、エクスペリエンスを差別化されたデータで競合他社を目立たせます。 Isv は、埋め込み分析で作成する新たな価値について料金を請求することもできます。

Power BI Embedded を使用する場合、顧客は Power BI について何も知る必要がなくなります。 2 つの方法を使用すると、埋め込みアプリケーションを作成します。
- Power BI Pro アカウント 
- サービス プリンシパル 

Power BI Pro アカウントは、アプリケーションのマスター アカウント (そのプロキシ アカウントとして待ち時間) として機能します。 このアカウントでは、生成できる埋め込みトークンは、アプリケーションの Power BI ダッシュ ボードとレポートへのアクセスを提供します。

[サービス プリンシパル](embed-service-principal.md)を使用すると、**アプリ専用**トークンを使用して、アプリケーションに Power BI コンテンツを埋め込むことができます。 生成することもできます埋め込みトークンは、アプリケーションの Power BI ダッシュ ボードとレポートへのアクセスを提供します。

Power BI Embedded を使用する開発者には、構築、アプリケーションのコア機能ではなく支出時開発のビジュアルと分析に重点を時間を費やすことができます。 迅速にお客様のレポートとダッシュ ボードのニーズに対応し、完全に文書化されている Api と Sdk を簡単に埋め込むできます。 ナビゲーションが簡単なデータ探索をアプリで有効にすることで、ISV の顧客は、どのデバイスからでも迅速にデータ ドリブンの意思決定を下すことができるようになります。

> [!IMPORTANT]
> 埋め込み、Power BI サービスが必要ですが、お客様は、アプリケーションの埋め込みコンテンツを表示する Power BI アカウントを持っている必要はありません。 

運用環境に移行する準備ができたら、アプリ ワークスペースを専用の容量に割り当てる必要があります。 Microsoft Azure の Power BI Embedded には、アプリケーションに使用できる[専用の容量](azure-pbie-create-capacity.md)が用意されています。

詳細情報を埋め込むには、次を参照してください。 [Power BI コンテンツを埋め込む方法](embed-sample-for-customers.md)します。

## <a name="next-steps"></a>次の手順

Power BI コンテンツをアプリケーションに埋め込んだり、顧客向けに Power BI コンテンツを埋め込んだりすることができます。

> [!div class="nextstepaction"]
> [組織向けの埋め込み](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded とは何ですか?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[顧客向けに埋め込む](embed-sample-for-customers.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
