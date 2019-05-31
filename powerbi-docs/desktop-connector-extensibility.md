---
title: Power BI でのコネクタの機能拡張
description: コネクタの拡張機能, 機能, セキュリティ設定, 認定コネクタ
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 16b96d91a9dd37fa8a502bbcca772438c703cb63
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412981"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI でのコネクタの機能拡張

Power BI では、顧客と開発者はさまざまな方法で接続するデータ ソースを拡張できます。 既存のコネクタと (ODBC、OData、Oledb、Web、CSV、XML、JSON) などの汎用データ ソースを使用します。 また、開発者と呼ばれる、データ拡張機能を作成する**カスタム コネクタ**、し、それらを**コネクタの認定**します。

有効にすると現在のところ、**カスタム コネクタ**システム上で実行できるようにするカスタム コードのレベルを制御できるようにする安全にメニューを使用します。 すべてのカスタム コネクタまたは認定を受けたうえで Microsoft によって分散コネクタのみを選択することができます、**データの取得**ダイアログ。

## <a name="custom-connectors"></a>カスタム コネクタ

**カスタム コネクタ**さまざまな可能性を含めることができます、お客様のビジネス、業界固有の大規模なサービスをマイクロソフト重要な小規模の Api からまでのコネクタを公開していません。 多数のコネクタは、ベンダーによって分散されます。 特定のデータ コネクタの必要がある場合は、ベンダーに問い合わせてください。

使用する、**カスタム コネクタ**に、 *\[ドキュメント]\\Power BI Desktop\\カスタム コネクタ*フォルダー」の説明に従って、セキュリティ設定を調整および次のセクションでは。

**認定コネクタ**を使用するためにセキュリティ設定を調整する必要はありません。

## <a name="data-extension-security"></a>データ拡張機能のセキュリティ

データ拡張機能のセキュリティ設定を変更する**Power BI Desktop**選択**ファイル > オプションと設定 > オプション > セキュリティ**します。

![データ拡張機能のセキュリティ オプションを使用してカスタム コネクタをロードするかどうかを制御します。](media/desktop-connector-extensibility/data-extension-security-1.png)

**[データ拡張機能]** の下では、2 つのセキュリティ レベルから選択できます。

* [(Recommended) Only allow certified extensions to load]\(推奨) 認定されている拡張機能のみ読み込みを許可する\
* [(Not Recommended) Allow any extension to load without warning]\(非推奨) あらゆる拡張機能の読み込みを警告なしで許可する\

使用する場合**カスタム コネクタ**かを選択する必要がありますか、サード パーティが開発したコネクタ、 **"(Not Recommended) 警告せずに読み込むには、その拡張子の許可"** します。 このセキュリティ設定は、カスタム コネクタを完全に信頼できる場合を除き、お勧めしません。 そこでコードが HTTP 経由での送信などの資格情報の処理し、プライバシー レベルを無視するためです。

**「(推奨)」** セキュリティ設定、システムにカスタム コネクタがある場合、エラーが表示されるセキュリティのため読み込むことができませんコネクタを記述します。

![ダイアログ ボックスは、この case TripPin でのセキュリティ設定のため読み込むことができませんカスタム コネクタをについて説明します](media/desktop-connector-extensibility/data-extension-security-2.png)

エラーを解決し、これらのコネクタを使用して、変更、セキュリティ設定を **"(Not Recommended) 警告せずに読み込むには、その拡張子の許可"** 前に説明したように設定します。 その後、再起動**Power BI Desktop**します。

## <a name="certified-connectors"></a>認定コネクタ

データ拡張機能の限定されたサブセットと見なされる**Certified**します。 認定コネクタへのアクセス、**データの取得**ダイアログ。 コネクタを作成したサード パーティの開発者は、メンテナンスとサポートを担当します。 Microsoft では、コネクタを配布するときに、パフォーマンスや関数の継続的な責任を負いますがありません。

カスタム コネクタの認定を希望する場合は、dataconnectors@microsoft.com に連絡するようにベンダーにご依頼ください。
