---
title: Power BI で組織のカスタム ビジュアルを使用する
description: Power BI で組織のカスタム ビジュアルを使用、管理、作成する
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: e34491ebc1cc7554e8c8c000da7528754b5a673b
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223101"
---
# <a name="use-organizational-custom-visuals-in-power-bi"></a>Power BI で組織のカスタム ビジュアルを使用する

Power BI でカスタム ビジュアルを使用し、独自のビジュアルを作成したり、伝えたいことをデータ インサイトで作成したりできます。 多くの場合、このようなカスタム ビジュアルは開発者が作成します。Power BI にたくさん付属しているビジュアルでは要件を満たさないときに作成されます。 

カスタム ビジュアルが重要視される組織もあります。その組織に特有のデータやインサイトを伝えるために必要だからです。その組織だけのビジネス手法を反映し、データに特別な要件が求められることもあります。 そのような組織はカスタム ビジュアルを開発し、組織全体で共有し、適切に保守管理する必要があります。 Power BI カスタム ビジュアルではその機能を利用できます。

次の図は、Power BI における組織のカスタム ビジュアルのフロー プロセスを示したものです。管理者から始まり、開発と保守管理を経由し、最終的にデータ アナリストの元に届けられます。

![カスタム ビジュアルの図](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

組織のビジュアルが展開されます。これは Power BI 管理者が管理ポータルから管理します。 組織のリポジトリに展開されると、組織のユーザーは簡単に見つけて、Power BI Desktop から直接、自分のレポートに組織のカスタム ビジュアルをインポートできます。

作成したレポートで組織のカスタム ビジュアルを使用する方法については、組織のカスタム ビジュアルをレポートにインポートする方法を紹介している[この記事](power-bi-custom-visuals.md)を参照してください。

## <a name="administer-organizational-custom-visuals"></a>組織のカスタム ビジュアルを管理する

組織のカスタム ビジュアルを管理し、展開する方法については、組織のカスタム ビジュアルの展開と管理について説明している[この記事](https://go.microsoft.com/fwlink/?linkid=866790)を参照してください。

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシーのリスクがあるコードが含まれる場合があります。 組織のリポジトリに展開する前に、カスタム ビジュアルの作成者とソースを信頼できることを確認してください。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

注意する必要がある考慮事項と制限事項がいくつかあります。

管理者:

* レガシ カスタム ビジュアル (新しいバージョンの API に基づいて作成されていないカスタム ビジュアルなど) はサポートされていません。

* カスタム ビジュアルがリポジトリから削除されると、削除されたそのビジュアルを利用している既存のレポートでレンダリングが停止します。 リポジトリからの削除は元に戻せません。 カスタム ビジュアルを一時的に無効にするには、[無効にする] 機能を使用します。

エンド ユーザー:

* 組織のカスタム ビジュアルは、組織のリポジトリからインポートされるプライベートなビジュアルです。 他のプライベートなビジュアルと同じように、これらを [PowerPoint にエクスポート](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint)したり、ユーザーが[レポート ページをサブスクライブする](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe)ときに受信する電子メールに表示したりすることはできません。 これらの機能をサポートしているのは、マーケットプレースから直接インポートされる[認定済みカスタム ビジュアル](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified)のみです。

* AppSource マーケットプレースの Visio ビジュアル、PowerApps ビジュアル、Map box ビジュアル、GlobeMap ビジュアルは、組織のリポジトリから展開された場合、レンダリングされません。

## <a name="troubleshoot"></a>トラブルシューティング

トラブルシューティングについては、[Power BI カスタム ビジュアルのトラブルシューティング](power-bi-custom-visuals-troubleshoot.md)に関する記事を参照してください。

## <a name="faq"></a>よく寄せられる質問

詳細情報と質問の回答については、[Power BI カスタム ビジュアルについてよく寄せられる質問](power-bi-custom-visuals-faq.md#organizational-custom-visuals)に関するページをご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
