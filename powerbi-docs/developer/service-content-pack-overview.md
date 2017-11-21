---
title: "Power BI サービスのコンテンツ パック プログラムの概要"
description: "コンテンツ パック認定プログラム"
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
ms.date: 10/09/2017
ms.author: asaxton
ms.openlocfilehash: 4a8ea2acfcfe41192b82addfe52dbe67a0df8088
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Power BI サービスのコンテンツ パック プログラムの概要
コンテンツ パックは、ユーザーがソースからすぐに洞察を得られるようにするための既定のコンテンツのセットです。 コンテンツ パックは、通常、役割、ドメイン、またはワークフローの洞察を提供する特定のビジネス シナリオに焦点を当てています。

ISV は、顧客が自分のアカウントで接続し、インスタンス化することを可能にするテンプレート コンテンツ パックを構築できます。 ドメインの専門家として、ビジネス ユーザーが簡単に利用できる方法でデータのロックを解除できます。 コンテンツ パックは、インフラストラクチャのレポートに多額の投資をすることなく、顧客へアドホック監視と分析を提供します。 

これらの ISV 構築テンプレート コンテンツ パックは Power BI チームに提出し、Power BI コンテンツ パック ギャラリー (app.powerbi.com/getdata/services) と Microsoft AppSource (appsource.microsoft.com) で一般公開できます。 公開用コンテンツ パックの体験例を[ここ](template-content-pack-experience.md)で確認できます。

## <a name="overview"></a>概要
テンプレート コンテンツ パックを開発し送信する一般的なプロセスには、複数のステップが含まれます。

 ![プロセス](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [要件を見直し](#requirements)、満たしていることを確認する
2. Power BI Desktop で[コンテンツを作成](template-content-pack-authoring.md#queries)する
3. PowerBI.com で[ダッシュボードを作成](template-content-pack-authoring.md#dashboard)する
4. 組織内で、自分で[コンテンツ パックをテスト](template-content-pack-testing.md)する
5. 発行用の Power BI にコンテンツを[送信](template-content-pack-testing.md#submission)する

<a name="requirements"></a>

## <a name="requirements"></a>要件
コンテンツを構築して提出し、PowerBI サービスと AppSource で公開するには、次の要件を満たす必要があります。

* ビジネス ユーザーが使用する SaaS アプリケーションを用意しています。
* SaaS アプリケーションには、Power BI で視覚化できるユーザー データが含まれています。
* SaaS アプリケーションに、公共のインターネットからアクセスできる API が含まれています。 API は REST ベースの API か OData フィードであることが理由できます。 Power BI コンテンツ パックは、基本認証、OAuth 2.0、API キーのようなさまざまな種類の認証に対応しています。 
* 署名付きのパートナー契約。 これは[提出手順](template-content-pack-testing.md#submission)で行います。

技術的な要件の詳細については、「[オーサリング](template-content-pack-authoring.md)」セクションを参照してください。

## <a name="business-scenario"></a>ビジネス シナリオ
コンテンツ パックは、洞察と特定のビジネス シナリオに焦点を当てたメトリックを提供します。 対象ユーザーとコンテンツ パックからパッケージを受け取ることのメリットを理解するのは、提供するコンテンツでユーザーが正常であることを確認するのに役立ちます。

### <a name="tips"></a>ヒント
* 対象ユーザーと、彼らが実行しようとしているタスクを特定する  
* 特定の期間 (過去 90 日間) または最後の N 個の結果に焦点を当てる  
* 自分のシナリオに関連するテーブル/列のみをインポートする  
* 独立した固有のシナリオのために複数のコンテンツ パックの提供を考慮する  

## <a name="frequently-asked-questions"></a>よく寄せられる質問
**自分で所有していないサードパーティ製 SaaS アプリケーションに対して Power BI サービス コンテンツ パックを構築できますか。**

いいえ。現在のところ、サービスでコンテンツ パックを公開する前に、SaaS アプリケーションの所有者がパートナー契約に署名する必要があります。

**サービスのために公共開発者 API を用意できません。データ ストレージからデータを直接引き出す Power BI コンテンツ パックをそれでも構築できますか。**

いいえ。Power BI サービス コンテンツ パックには、公共のインターネットからアクセスできる開発者 API が必要です。

**どのような種類の API がサービス コンテンツ パックに対応していますか。どのような種類の認証を利用できますか。**

Power BI サービス コンテンツ パックはあらゆる REST API または OData フィードに対応しています。 Power BI では、基本認証、OAuth2.0、Web API キーなど、さまざまな種類の認証を利用できます。 記述的な要件の詳細は「[オーサリング](template-content-pack-authoring.md#dashboard)」という記事にあります。

**サービス コンテンツ パックについて他にも質問があります。問い合わせ方法は何ですか。**

メールでお気軽にお問い合わせください。アドレスは pbiservicesapps@microsoft.com です。

## <a name="support"></a>サポート
開発中のサポートのために、[https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support) を使用してください。 これは積極的に監視および管理されています。 顧客のインシデントは、すみやかに該当するチームに伝わります。

## <a name="next-step"></a>次の手順
[作成](template-content-pack-authoring.md)

