---
title: 追加購入が必要になる場合がある - Power BI ビジュアルのガイドライン
description: AppSource にカスタム ビジュアルを発行して、それを他のユーザーが見つけたり、購入して使用できるようにする方法について説明します。
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 280f60d0ae60a445d94a640af974a2624c73bb83
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430006"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Power BI ビジュアルの追加購入のガイドライン

最近まで、**Marketplace (AppSource)** では、無料の Power BI ビジュアルのみが受け付けられていました。 このポリシーは変わり、"additional purchase may be required" (追加購入が必要になる場合があります) の価格タグが付いたビジュアルも **AppSource** に送信できるようになります。 追加購入が必要なビジュアルは、Office ストアのアプリ内購入 (IAP) アドインと似ています。 [認定されたカスタム ビジュアルに関する記事](../power-bi-custom-visuals-certified.md)で説明されているように、開発者はこれらのビジュアルを、**AppSource** チームの承認後、認定の要件に準拠していることを確認してから認定のために送信することも可能です。

> [!Note]
> ビジュアルが認定されるには、外部サービスやリソースにはアクセスしないようにする必要があります。

## <a name="whats-changing-in-the-submission-process"></a>送信プロセスの変更点

開発者は IAP ビジュアルを、無料のビジュアルと同様に販売者のダッシュボードを使用して AppSource にアップロードします。 開発者は、送信したビジュアルに IAP 機能が含まれることを示すために、販売者のダッシュボードのメモに "Visual with in-app purchase." (アプリ内購入があるビジュアル) と記載する必要があります。 また、開発者は検証チームが IAP 機能を検証できるように、ライセンス キーやトークンを提供する必要があります。 ビジュアルが検証され承認されたら、AppSource の IAP ビジュアルの登録情報の価格オプションの下には、'Additional purchase may be required' (追加購入が必要になる場合があります) と記載されます。

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>IAP 機能のある Power BI ビジュアルとは

IAP ビジュアルは、無料のビジュアルで無料の機能があります。しかしこれに加え、操作に追加費用を支払う必要がある追加の機能もあります。 開発者は、操作にはどの機能を追加購入する必要があるか、ビジュアルの説明でユーザーに通知する必要があります。 現在、Microsoft では、アプリおよびアドイン内での購入をサポートするネイティブ アプリケーション プログラミング インターフェイス (API) は用意していません。開発者は、このような購入には、サードパーティ製の支払いシステムを使用する必要があります。 弊社のストア [ポリシー](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads)を参照してください。

## <a name="logo-guidelines"></a>ロゴのガイドライン

このセクションでは、ロゴをビジュアルに追加するための仕様について説明します。

> [!NOTE]
> ロゴは編集モードでのみ許可されています。 ロゴはビュー モードでは表示できません。

![definitions](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![things-to-keep](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![things-to](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![size-and-format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![margins-and](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![edit-mode](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>ベスト プラクティス

### <a name="visual-landing-page"></a>ビジュアルのランディング ページ

ランディング ページを使用すると、ユーザーにご自分のビジュアルの使用方法およびライセンスの購入場所を明確にできます。 自動でトリガーされる動画は含めないでください。 ライセンスの購入の詳細情報やリンクや IAP 機能の使用方法など、ユーザーの操作性を改善する資料のみを追加してください。

### <a name="license-key-and-token"></a>ライセンス キーおよびトークン

ユーザーの利便性のために、ユーザーに便利な場所である書式ウィンドウの上部にライセンス キーやトークン関連のフィールドを追加します。

## <a name="faq"></a>よく寄せられる質問

詳細情報と質問の回答については、[ビジュアルの追加購入についてよく寄せられる質問](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases)に関する記事をご覧ください。

## <a name="next-steps"></a>次の手順

[AppSource](office-store.md) にカスタム ビジュアルを発行して、他のユーザーが見つけたり使用したりすることができるようにする方法について説明します。
