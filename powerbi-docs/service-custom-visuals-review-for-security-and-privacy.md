---
title: "カスタム ビジュアルのセキュリティとプライバシーを確認する"
description: "カスタム ビジュアルを有効にする前に、セキュリティおよびプライバシーのビジュアルを確認し、組織の基準に適合することを確認してください。"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: 15f8d9090736a62fdaa53aa3f19e7e0fff127337
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2018
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>カスタム ビジュアルのセキュリティとプライバシーを確認する
カスタム ビジュアルを有効にする前に、セキュリティおよびプライバシーのビジュアルを確認し、組織の基準に適合することを確認してください。

## <a name="enable-a-custom-visual"></a>カスタム ビジュアルを有効にする
<a name="enable"></a>次に示すように、レポートのカスタム ビジュアルは、**[カスタム ビジュアルを有効にする]** を選択するまでは無効です。  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>カスタム ビジュアルを有効にする前の考慮事項
<a name="considerations"></a>

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシーのリスクがあるコードが含まれている可能性があります。そのため、レポートのカスタム ビジュアルは、[カスタム ビジュアルを有効にする] を選択するまでは無効状態になっています。 カスタム ビジュアルを有効にするかどうかを決定するときの考慮事項を次に示します。
> 
> 

1. レポートで使用するカスタム ビジュアルの作成者とソースが信頼できることを確認します。
2. はっきりしない場合は、表示するレポートでカスタム ビジュアルを有効にする必要があるかどうかを IT チームに問い合わせる必要があります。
3. 他のユーザーが作成したカスタム ビジュアルを含むレポートを共有する場合は、よく知っている共同作業者であっても、カスタム ビジュアルを有効にすることを義務と考えてはなりません。 現在の作業に必要があるかどうかを冷静に判断する必要があります。 カスタム ビジュアルを信頼できない場合は、カスタム ビジュアルを含まないレポートを提供するように他のユーザーに依頼してもまったく問題ありません。

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>カスタム ビジュアルを有効にするときのセキュリティに関する IT 担当者向けベスト プラクティス
<a name="security"></a>

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシーのリスクがあるコードが含まれている可能性があります。そのため、レポートのカスタム ビジュアルは、[カスタム ビジュアルを有効にする] を選択するまでは無効状態になっています。 カスタム ビジュアルのセキュリティおよびプライバシーを評価するときに従うべきベスト プラクティスがいくつかあります。
> 
> 

1. 組織内でのカスタム ビジュアルに対する審査プロセスを実装します。 審査に合格したカスタム ビジュアルは、SharePoint ドキュメント ライブラリや OneNote ドキュメントなどの内部 Web サイトを介して内部ユーザーと共有します。
2. カスタム ビジュアルの適切な使用方法に関するビジネス ユーザー向けのガイダンス、およびセキュリティとプライバシーの質問を送信するためのビジネス ユーザー向け電子メール グループを提供します。
3. カスタム ビジュアルの pbiviz ファイルの JavaScript コードを評価します。

**カスタム ビジュアルの JavaScript コードを評価するには**

カスタム ビジュアルは JavaScript を使用するので、セキュリティやプライバシーのリスクがあります。 カスタム ビジュアルまたはカスタム ビジュアルを含む pbix ファイルを不明なソースから受け取った場合は、JavaScript を調べて安全かどうかを確認します。

カスタム ビジュアルの JavaScript コードを評価するには、カスタム ビジュアルのコードを抽出します。 コードの抽出方法は次のとおりです。  

1. .pbiviz ファイルをフォルダーに保存します。
2. ファイルの拡張子を .zip に変更します。
3. ローカル フォルダーに zip ファイルを抽出します。

## <a name="custom-visual-file-contents"></a>カスタム ビジュアル ファイルの内容
pbiviz ファイルの内容は次のとおりです。

| **ファイル** | **説明** |
|:--- |:--- |
| ./package.json |カスタム ビジュアル用に読み込むファイルを示すマニフェスト ファイルです。 |
| ./resources |カスタム ビジュアルで使用される CSS、TypeScript、および JavaScript が含まれています。 |
| ./resources/&lt;name&gt; |&gt;name&lt; は、カスタム ビジュアルの名前です。 |
| ./resources/&lt;name&gt;.css |カスタム ビジュアルの css リソース ファイルです。 |
| ./resources/&lt;name&gt;.js |ユーザーが [カスタム ビジュアルを有効にする] をクリックしたときに、またはユーザーがカスタム ビジュアルをインポートした後に実行されるコードです。 警告: JavaScript コードにはセキュリティやプライバシーのリスクが含まれる場合があります。 |
| ./resources/&lt;name&gt;.ts |TypeScript 形式でのビジュアル用の JavaScript ソース コードです。 警告: JavaScript または TypeScript のコードにはセキュリティやプライバシーのリスクが含まれる場合があります。 |
| ./resources/&lt;name&gt;.png |ユーザーに表示されるビジュアルのアイコンです。 |

pbiviz ファイルを抽出した後は、コードを評価できます。 ベスト プラクティスおよび探す必要がある脅威を次に示します。

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>JavaScript コードまたは TypeScript コードの評価に関するベスト プラクティス
**JavaScript** または **TypeScript** のコードにはセキュリティやプライバシーのリスクが含まれる場合があります。 ベスト プラクティスおよび探す必要がある脅威を次に示します。

### <a name="best-practices-to-evaluate-javascript-code"></a>JavaScript コードの評価に関するベスト プラクティス
* 常に、.js ファイルの内容を評価します。 これが実際に実行されるコードです。 .ts ファイルの内容は、カスタム ビジュアルに含まれる .js ファイルにコンパイルされない可能性があります。
* 常に、.ts ファイルの内容を評価します。 .ts ファイルを**開発者ツール**に読み込み、ビジュアルをエクスポートして、新しく作成された .pbiviz ファイルの .js ファイルと、ビジュアルに含まれる元の .js ファイルを比較できます。
* カスタム ビジュアルのアイコンが、ユーザーが使い慣れた他のビジュアルと似すぎていないことを確認します。
* 常に、最小限の特権しか持たず、機密データにアクセスできないテスト アカウントでビジュアルを評価します。 Power BI 以外のサービスへのサインイン情報を持たないローカル アカウントをテスト アカウントに使用するのが理想的です。

### <a name="threats-to-look-for-in-javascript-code"></a>JavaScript コードで探す必要がある脅威
* ビジュアルを編集モードおよび表示モードの両方で使用して、ネットワーク アクティビティを確認します。 要求された内容に問題がないことを確認します。 ビジュアルの作成者から事前に伝えられていない限り、Power BI ドメインの外部リソースへの要求は表示されないはずです。
* Power BI ドメインから送信されるすべてのデータは、「正常な」使用と想定されるものと一致している必要があります。 たとえば、別のサイトからのビデオを表示するために IFrame を使用するビデオ プレイヤーがビジュアルで実装されている場合、ビデオを正しく表示するためにいくつかの情報が IFrame 要求で送信されます。 しかし、データ セット全体がネットワーク経由で送信されていることが検出された場合は、それが必要で望ましいことかどうかをさらに調査する必要があります。
* 個人を特定できる情報がカスタム ビジュアルによって送信または保存されるかどうかを確認します。
* ディスクへのファイルの書き込みや cookie へのアクセスなど、カスタム ビジュアルがローカル コンピューターのリソースにアクセスしようとしているかどうかを確認します。
* カスタム ビジュアルにわかりにくいコードまたは明確な目的のないコードと思われるものが含まれるかどうかを確認します。
* 過去にレビューした各ビジュアルのコピーを保存します。
* 以前にレビューしたビジュアルの更新を確認している場合は、変更内容を確認します。 常に、初めてのレビュー用にビジュアルを受け取ったときと同じ厳格さで更新を確認します。
* 何らかの疑わしい点または不明確な点が見つかった場合は、マイクロソフトに連絡してください。

## <a name="next-steps"></a>次の手順
[Power BI での視覚化](power-bi-report-visualizations.md)  
[Power BI でのカスタム ビジュアル](power-bi-custom-visuals.md)  
[カスタム ビジュアルを Office ストアに発行する](developer/office-store.md)  
[カスタム ビジュアル開発者ツールの概要](service-custom-visuals-getting-started-with-developer-tools.md)  
[カスタム ビジュアルを証明する方法](power-bi-custom-visuals-certified.md)    
[ビデオ: Sachin Patney と Nico Cristache による Power BI 用カスタム ビジュアルの作成](https://www.youtube.com/watch?v=kULc2VbwjCc)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

