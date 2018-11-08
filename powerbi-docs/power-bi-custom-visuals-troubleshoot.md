---
title: Power BI カスタム ビジュアルの開発方法に関するトラブルシューティング
description: この記事では、Power BI カスタム ビジュアルの開発または作成時に発生する一般的な問題について説明します。
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: d6f3f654574e9cca081ae2f8191fd7b9fc017afd
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223575"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Power BI カスタム ビジュアルのトラブルシューティング

## <a name="debug"></a>デバッグ

**Pbiviz コマンドが見つかりません (または類似のエラー)**

ターミナルのコマンド ラインで `pbiviz` を実行すると、ヘルプ画面が表示されるはずです。 ヘルプ画面が表示されない場合、コマンドは正しくインストールされていません。 バージョン 4.0 以降の NodeJS がインストールされていることを確認します。

**[視覚化] タブで "ビジュアルのデバッグ" が見つかりません**

"ビジュアルのデバッグ" は、**[視覚化]** タブ内でプロンプト アイコンのように表示されます。

![ビジュアルの選択](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

表示されない場合は、Power BI の設定内で有効にされていることを確認してください。

> [!NOTE]
> ビジュアルのデバッグ機能は、現時点では、Power BI サービスでのみ使用可能で、Power BI Desktop とモバイル アプリでは使用できません。 パッケージ化したビジュアルはあらゆる場所で機能します。

**ビジュアル サーバーに接続できません**

ビジュアル プロジェクトのルートから、ターミナルのコマンド ラインで `pbiviz start` コマンドを使用してビジュアル サーバーを実行します。 サーバーが動作する場合、SSL 証明書が正しくインストールされていない可能性があります。

## <a name="next-steps"></a>次の手順

詳細情報と質問の回答については、[Power BI カスタム ビジュアルについてよく寄せられる質問](power-bi-custom-visuals-faq.md#organizational-custom-visuals)に関するページをご覧ください。