---
title: "Power BI Desktop の起動時の問題を解決する"
description: "Power BI Desktop の起動時の問題を解決する"
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 515832b9e6b737a942b08b491b78337d78398ee3
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Power BI Desktop が起動しない問題を解決する
**Power BI Desktop** では、以前のバージョンの **Power BI オンプレミス データ ゲートウェイ**をインストールして実行していたユーザーが Power BI Desktop を起動できないことがあります。これは、Power BI オンプレミス データ ゲートウェイがローカル コンピューターの名前付きパイプに設定した管理ポリシー制限が原因で発生します。 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>オンプレミス データ ゲートウェイと Power BI Desktop での問題を解決する
オンプレミス データ ゲートウェイに関する問題を解決して、Power BI Desktop を起動できるようにするには、3 つのオプションがあります。

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>解決方法 1: 最新バージョンの Power BI オンプレミス データ ゲートウェイをインストールする
Power BI オンプレミス データ ゲートウェイの最新バージョンでは、ローカル コンピューターの名前付きパイプに制限が設定されないため、Power BI Desktop を正常に起動できます。 引き続き Power BI オンプレミス データ ゲートウェイを使う必要がある場合は、この解決方法をお勧めします。 最新バージョンの Power BI オンプレミス データ ゲートウェイは、[こちら](https://go.microsoft.com/fwlink/?LinkId=698863)からダウンロードできます。 なお、このリンクはインストール用の実行可能ファイルへの直接ダウンロード リンクですのでご注意ください。

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>解決方法 2: Power BI オンプレミス データ ゲートウェイの Windows サービスをアンインストールまたは停止する
Power BI オンプレミス データ ゲートウェイが不要になった場合は、これをアンインストールするか、Power BI オンプレミス データ ゲートウェイの Windows サービスを停止すれば、ポリシー制限が解除され、Power BI Desktop を起動できるようになります。

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>解決方法 3: 管理者特権を使って Power BI Desktop を実行する
別の方法として、Power BI Desktop を管理者として正常に起動できれば、Power BI Desktop も正常に起動できます。 この場合でも、前述のとおり Power BI オンプレミス データ ゲートウェイの最新バージョンをインストールすることを勧めします。

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Power BI Desktop 起動時の他の問題に関するヘルプ
**Power BI Desktop** で発生するできる限り多くの問題に対応するように作業しています。 多くのお客様に影響を与える可能性がある問題を常に注視し、記事にしています。

**Power BI Desktop** の起動時の問題がオンプレミス データ ゲートウェイと関係ない場合、または前記の解決方法で解決しないときは、[Power BI のサポート](https://support.powerbi.com) (https://support.powerbi.com) にサポート インシデントを送信して、問題の特定と解決を依頼できます。

今後 **Power BI Desktop** で他の問題が発生した場合は (発生しないか非常に少ないことが望ましい)、トレースを有効にしてログ ファイルを収集すると、問題の分離と特定に役立ちます。 トレースを有効にするには、**[ファイル] > [オプションと設定] > [オプション]** を選び、**[診断]** を選んだ後、*[診断オプション]* の **[トレースを有効にする]** をオンにします。 このオプションを設定するには **Power BI Desktop** が動作している必要があることはわかっていますが、**Power BI Desktop** の起動に関する将来の問題にはいっそう有用です。

