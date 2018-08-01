---
title: Power BI で組織のカスタム ビジュアルを使用する
description: Power BI で組織のカスタム ビジュアルを使用、管理、作成する
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: bc4dcc26ac2007e482b396139d572018c8a3acd3
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2018
ms.locfileid: "34291905"
---
# <a name="using-organization-custom-visuals-in-power-bi"></a>Power BI で組織のカスタム ビジュアルを使用する

Power BI でカスタム ビジュアルを使用し、独自のビジュアルを作成したり、伝えたいことをデータ インサイトで作成したりできます。 多くの場合、このようなカスタム ビジュアルは開発者が作成します。Power BI にたくさん付属しているビジュアルでは要件を満たさないときに作成されます。 

カスタム ビジュアルが重要視される組織もあります。その組織に特有のデータやインサイトを伝えるために必要だからです。その組織だけのビジネス手法を反映し、データに特別な要件が求められることもあります。 そのような組織はカスタム ビジュアルを開発し、組織全体で共有し、適切に保守管理する必要があります。 Power BI カスタム ビジュアルではその機能を利用できます。

次の図は、Power BI における組織のカスタム ビジュアルのフロー プロセスを示したものです。管理者から始まり、開発と保守管理を経由し、最終的にデータ アナリストの元に届けられます。

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

組織のビジュアルが展開されます。これは Power BI 管理者が管理ポータルから管理します。 組織のリポジトリに展開されると、組織のユーザーは簡単に見つけて、Power BI Desktop から直接、自分のレポートに組織のカスタム ビジュアルをインポートできます。

## <a name="using-organizational-custom-visuals"></a>組織のカスタム ビジュアルを使用する

作成したレポートで組織のカスタム ビジュアルを使用する方法については、組織のカスタム ビジュアルをレポートにインポートする方法を紹介している[この記事](power-bi-custom-visuals.md)を参照してください。
 
## <a name="administering-organizational-custom-visuals"></a>組織のカスタム ビジュアルを管理する

組織のカスタム ビジュアルを管理し、展開する方法については、組織のカスタム ビジュアルの展開と管理について説明している[この記事](https://go.microsoft.com/fwlink/?linkid=866790)を参照してください。

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシーのリスクがあるコードが含まれる場合があります。 組織のリポジトリに展開する前に、カスタム ビジュアルの作成者とソースを信頼できることを確認してください。 
> 

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
 
注意する必要がある考慮事項と制限事項がいくつかあります。
 
管理者:

* レガシ カスタム ビジュアル (新しいバージョンの API に基づいて作成されていないカスタム ビジュアルなど) はサポートされていません。

* カスタム ビジュアルがリポジトリから削除されると、削除されたそのビジュアルを利用している既存のレポートでレンダリングが停止します。 リポジトリからの削除は元に戻せません。 カスタム ビジュアルを一時的に無効にするには、[無効にする] 機能を使用します。
 
エンド ユーザー:

* 組織のビジュアルでは、Power BI ワークスペース コレクションを利用できません。

* AppSource マーケットプレースの Visio ビジュアル、PowerApps ビジュアル、GlobeMap ビジュアルは、組織のリポジトリから展開された場合、レンダリングされません。
