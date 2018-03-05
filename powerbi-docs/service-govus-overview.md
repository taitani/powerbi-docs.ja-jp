---
title: "米国政府顧客向け Power BI - 概要"
description: "米国政府顧客向けに、Power BI 米国政府サービスの機能と制限事項を説明します。"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: b3682deb1897647a7de6f32dc87a4d7ed8bc2c9f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="power-bi-for-us-government-customers"></a>米国政府顧客向け Power BI
**Power BI サービス**には、**Office 365 US Government Community** サブスクリプションの一部として米国政府顧客が利用できるバージョンがあります。 この記事で説明する **Power BI サービス**のバージョンは、米国政府顧客向けに特に設計されており、**Power BI サービス**の市販バージョンとは独立した別のものです。

![](media/service-govus-overview/service_usgov_overview-1.png)

以下のセクションでは、 **Power BI サービス** の米国政府バージョンで使用できる *機能* について説明し、いくつかの *制限事項* を明らかにし、よくある質問 ( **FAQ** ) と回答 (サインアップ方法を含みます) を示して、詳細情報へのリンクを提供します。

## <a name="features-of-power-bi-us-government"></a>米国政府向け Power BI の機能
**米国政府向け Power BI** は **Pro ライセンス**のみで入手できます。無償版ライセンスはありません。 Power BI サービスの一部の機能は、このサービスの**米国政府向け Power BI** バージョンで利用できます。

次の機能は **Pro** ライセンスのものであり、**米国政府向け Power BI** で利用できます。

* ダッシュボードとレポートの作成と表示
* [データ容量の制限](service-admin-manage-your-data-storage-in-power-bi.md)
* [スケジュールされたデータ更新](refresh-data.md)
* 更新可能なチーム ダッシュボード
* アクセス制御の共有と管理のための Active Directory グループ
* Excel、CSV、Power BI Desktop ファイルからのレポートと[データのインポート](service-get-data.md)
* Data Management Gateway
* すべてのデータは、Azure SQL と Power BI 用 Blob Storage の両方で暗号化されます
* [コンテンツ パック](service-connect-to-services.md)でのサービスへの接続

## <a name="connectivity-between-government-and-public-azure-cloud-services"></a>行政機関向けおよびパブリックの Azure Cloud Services 間の接続 

Azure は複数のクラウドに分散されます。 既定では、テナントにはクラウド固有のインスタンスに対するファイアウォール規則を開くことが許可されていますが、クラウド間ネットワーキングの場合は異なり、サービス間で通信するために特定のファイアウォール規則を開く必要があります。 Power BI のお客様で、アクセスする必要があるパブリック クラウドに既存の SQL インスタンスをお持ちのお客様の場合、次のデータセンターについては Azure Government Cloud IP 空間に対する特定のファイアウォール規則を SQL で開く必要があります。

* 米国政府アイオワ
* 米国政府バージニア州
* 米国政府テキサス
* 米国政府アリゾナ

パブリック クラウドの場合、IP 空間を使用できますが、政府機関向けクラウドの場合は、Azure サポート チケットを開いて、上記に一覧したデータ センターの IP 範囲を要求する必要があります。 


## <a name="limitations-of-power-bi-us-government"></a>米国政府向け Power BI の制限事項
**Power BI サービス** の市販バージョンで利用できる機能の一部は、 **Power BI サービス** の米国政府顧客バージョンでは利用 *できません* 。 Power BI チームは米国政府顧客がこれらの機能を使用できるようにする作業を行っており、これらの機能が利用できるようになった時点でこの記事を更新します。

* **米国政府向け Power BI** は **Pro** ライセンスとしてのみ利用できます。 管理ポータルで (あるいは、ユーザーとして) Power BI (無償版) ライセンスを参照するとき、それは商用 Power BI サービス クラウドで実行されます。
* **監査** - Office 365 のセキュリティとコンプライアンス ポータルでは、監査を使用できません。
* **Cortana の Power BI コンテンツ** - Power BI の結果は Cortana の検索結果に表示されません。たとえば、Power BI コンテンツ (ダッシュボード、レポート、アプリ) の結果や、特定のキーワードに対して Cortana 最適化レポート ページを表示する結果は表示されません。
* **外部ユーザー共有** - 共有は BI テナント内でのみ許可されます。Power BI テナントの外部のユーザーとは共有できません。

**Power BI** 無償版ライセンスがアカウントに割り当てられている場合、そのアカウントは **Power BI** サービスの商用バージョンで実行されます。**米国政府向け Power BI** サービスには含まれません。 無償版アカウントの場合、次の問題が発生することがあります。

* ゲートウェイ、モバイル、デスクトップを認証できません
* Azure の商用データ ソースにアクセスできません
* PBIX ファイルを商用から手動でアップロードする必要があります
* Power BI モバイル アプリを使用できません

問題を解決するには、アカウント担当者に問い合わせてください。

## <a name="frequently-asked-questions-faq-for-the-us-government-version-of-the-power-bi-service"></a>Power BI サービス米国政府バージョンによく寄せられる質問 (FAQ)
次の質問 (と回答) は、サービスに関して必要な情報を迅速に入手できるようにするために提供されます。

**質問:** 市販版 **Power BI** のデータを **Power BI サービス**米国政府バージョンに移行する方法を教えてください。

**回答:** 管理者は、独立した米国政府固有サブスクリプションに、**Power BI** の新しいインスタンスを作成する必要があります。 その後、市販版データを米国政府向け **Power BI サービス**にレプリケートし、市販版ライセンスを削除して、既存のドメインを新しい米国政府固有サービスに関連付けることができます。

**質問:** 特定のコンテンツ パックに接続できないのはなぜですか。

**回答:** コンテンツ パックに接続する前に、サブスクリプションが有効になっていることを確認する必要があります。

**質問:** 自分の米国政府組織内で **Power BI** を使ってみたいと思います。 使ってみる方法

**回答:** サインアップ ( *オンボーディング*  とも呼ばれます) は、既存のライセンスとサブスクリプションによって異なる場合があります。 詳細については、[米国政府向け Power BI へのサインアップ](service-govus-signup.md)に関する記事をご覧ください。

**質問:** 米国政府向け **Power BI** に接続するための URL は、市販バージョンの **Power BI** の URL とは異なりますか。

**回答:** はい、URL は異なります。 次の表に各 URL を示します。

| 市販バージョンの URL | 米国政府バージョンの URL |
| --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) |

## <a name="next-steps"></a>次の手順
Power BI を使うと、さまざまなことを行えます。 サービスにサインアップする方法を説明する記事など、詳細および学習については、次のリソースをご覧ください。

* [米国政府向け Power BI へのサインアップ](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">米国政府向け Power BI のデモ</a>
* [Power BI のガイド付き学習](guided-learning/gettingstarted.yml#step-1)
* [Power BI サービスの概要](service-get-started.md)
* [Power BI Desktop の概要](desktop-getting-started.md)

