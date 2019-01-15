---
title: Power BI と Azure エグレス
description: Azure エグレスの料金と Power BI をテナントの場所と Power BI Premium に基づいて理解する
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 528d31a72d2c78b0a00f853d2df82f3a4eb04eae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295335"
---
# <a name="power-bi-and-azure-egress"></a>Power BI と Azure エグレス

Power BI と共に Azure データ ソースを使用するとき、Power BI テナントを Azure データ ソースと同じリージョンに置くことで Azure エグレス料金を回避できます。

Power BI テナントがデータ ソースをデプロイしたリージョンと同じ Azure リージョンにデプロイされているとき、スケジュールした更新と DirectQuery のやりとりに対してエグレス料金が発生しません。 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Power BI テナントの場所を確認する

Power BI テナントの場所を見つける方法については、「[Power BI テナントの場所](service-admin-where-is-my-tenant-located.md)」という記事を参照してください。

Power BI Premium Multi-Geo のお客様については、Power BI テナントが一部の Azure ベース データ ソースにとって最適な場所にない場合、目的の Azure リージョンに Power BI Premium Multi-Geo をデプロイし、Power BI テナントと Azure データ ソースを同じ Azure リージョンに置くことの利点を得ることができます。

## <a name="next-steps"></a>次の手順

Power BI Premium または Multi-Geo に関する詳細については、次のリソースをご覧ください。

* [Microsoft Power BI Premium とは何ですか?](service-premium.md)
* [Power BI Premium の購入方法](service-admin-premium-purchase.md)
* [Power BI Premium の Multi-Geo のサポート (プレビュー)](service-admin-premium-multi-geo.md)
* [Power BI テナントの場所](service-admin-where-is-my-tenant-located.md)
* [Power BI Premium のよく寄せられる質問](service-premium-faq.md)


