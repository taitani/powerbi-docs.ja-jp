---
title: データセットを認定する (プレビュー) - Power BI
description: エンタープライズ ユーザーを信頼性の高い、高品質なデータセットに誘導する方法について説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e790afee5b57b73a756ca3c1afd564b00e778186
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461329"
---
# <a name="certify-datasets-preview"></a>データセットを認定する (プレビュー)

重要な情報の信頼できるソースであるデータセットを、組織で認定することができます。 このようなデータセットはレポート デザイナーがレポートの作成を開始し、信頼性の高いデータを検索するときに特に役立ちます。 認定は、特に価値のあるデータセットのみを厳選して認定するプロセスです。 Power BI テナント管理者には新しい設定が付与されるため、データセットを認定するユーザーを厳密に制御できます。 そのため、管理者はデータセットの認定により、組織全体で使用するために設計された、本当に確実で信頼できるデータセットを確保できます。

これで Power BI ユーザーが多様なデータセットにアクセスできるようになるため、企業はユーザーを信頼性の高い、高品質のデータセットに誘導する必要があります。 Power BI には、データセットを*推奨する*方法が 2 つあります。

- **昇格**: データセットの所有者は、広範囲の使用が可能になったデータセットを昇格することができます。 詳細については、「[Promote your dataset](service-datasets-promote.md)」(データセットを昇格する) を参照してください。 
- **認定**: データセットの所有者は、昇格したデータセットの認定を要求できます。 **データセットの認定**のテナント管理者の設定で定義された選択ユーザーのグループが、認定するデータセットを決定します。

## <a name="certify-a-dataset"></a>データセットを認定する

テナント管理者は **[推奨]** 設定ページで**詳細情報**のリンクの URL を提供することができます。  認定プロセスについてのドキュメントとリンクさせることができます。 **詳細情報**のリンクの宛先が提供されない場合は、既定でこの記事が示されます。

![データセットの認定の詳細情報](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

データセットを認定できるユーザーに指定されることは、明らかに大きな責任です。 データセットの作成者からデータセットの認定について問い合わせがあったときから、審査プロセスが始まります。 データセットが認定に値することがわかったら、ここからが最後の手順です。

1. データセットの所有者は、データセットが存在するワークスペースにメンバーのアクセス許可を付与する必要があります。
1. テナント管理者からデータセットを認定するユーザーに指名された場合、そのデータセットの **[設定]** の **[推奨]** セクションに **[認定済み]** オプションが表示されます。 **[認定済み]** を選びます。
1. **[適用]** を選びます。

テナント管理者が[ワークスペース間でのデータセットの使用を制御する](service-datasets-admin-across-workspaces.md)方法の詳細をご確認ください。

## <a name="next-steps"></a>次の手順

* 「[Using datasets across workspaces](service-datasets-across-workspaces.md)」(ワークスペース全体でのデータセットの使用) を参照してください
* わからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
