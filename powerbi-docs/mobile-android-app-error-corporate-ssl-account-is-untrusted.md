---
title: "エラー: "
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Power BI 用の Android アプリにサインインするとき、\"お使いの企業 SSL 証明書が信頼されていないため、認証できませんでした\" というメッセージが表示されることがあります"
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>エラー: "企業 SSL 証明書が信頼されていません" - Power BI
Microsoft Power BI 用の Android モバイル アプリにサインインするとき、"お使いの企業 SSL 証明書がこのデバイスによって信頼されていないため、認証できませんでした。 会社の IT 管理者にお問い合わせください。" というメッセージが表示されることがあります。 

このメッセージへの対処方法は、通常、Android デバイスのオペレーティング システムによって異なりますが、このエラーの原因になる可能性のある問題が他にも 2 つあります。

## <a name="on-android-7-or-later"></a>Android 7 以降
**Chrome** という名前のアプリの更新プログラムを探してインストールします。

## <a name="on-android-6-and-earlier"></a>Android 6 以前
デバイスの System Webview の更新バージョンが必要な場合があります。 既にデバイスにインストールされている可能性があり、その場合は **[更新]** をクリックする必要があるだけです。

System Webview がデバイスにインストールされていない場合:

1. Android デバイスで、Power BI を閉じます。
2. Google Play ストアを開き、Google Inc. の **System Webview** を検索します。
3. インストールします。
4. Power BI アプリを再起動し、サインインします。

## <a name="time-zone-settings"></a>タイム ゾーンの設定
デバイスのタイム ゾーンの設定が正しくない可能性があります。 

**[設定]** > **[システム]** > **[日付と時刻]** で確認します。

## <a name="custom-authentication-server"></a>カスタム認証サーバー
カスタム認証サーバーを使っている場合、会社の認証サーバーの SSL 証明書が有効ではない可能性があります。 組織の IT 管理者に問い合わせてください。

## <a name="next-steps"></a>次の手順
* Android アプリ ストアから [Android アプリをダウンロード](http://go.microsoft.com/fwlink/?LinkID=544867)する。
* わからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

