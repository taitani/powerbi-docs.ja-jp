---
title: "Power BI から PowerPoint にレポートをエクスポートする (プレビュー)"
description: "Power BI レポートを PowerPoint にエクスポートする方法について説明します。"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/22/2018
ms.author: davidi
ms.openlocfilehash: 5ebfa2f54c26c0b4c3321120558e1cccb8bce146
ms.sourcegitcommit: ed49510adee96042c02d6bdadbfcf8a2e566fbf8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2018
---
# <a name="export-reports-from-power-bi-to-powerpoint-preview"></a>Power BI から PowerPoint にレポートをエクスポートする (プレビュー)
Power BI では、レポートを **Microsoft PowerPoint** に発行して、Power BI レポートに基づくスライド デッキを簡単に作成できるようになりました。 **PowerPoint にエクスポート**すると、次のようになります。

* Power BI レポートの各ページは、PowerPoint では個別のスライドになります
* Power BI レポートの各ページは、単一の高解像度のイメージとして PowerPoint にエクスポートされます
* Power BI レポートのテキスト ボックスは、PowerPoint では編集可能なテキスト ボックスになります
* PowerPoint に、Power BI レポートへのリンクが作成されます

**Power BI レポート**は、**PowerPoint** に簡単にエクスポートできます。 次のセクションで説明する手順に従うだけです。

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Power BI レポートを PowerPoint にエクスポートする方法
Power BI サービスで、左側のナビゲーション ペインの **[レポート]** セクションを選択して展開し、キャンバスに表示するレポートを選択します。 レポートが **[マイ ワークスペース]** セクションまたは **[お気に入り]** に含まれる場合は、これらの場所からレポートを選択することもできます。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_0.png)

PowerPoint にエクスポートするレポートがキャンバスに表示されている場合は、Power BI サービスのメニュー バーから **[ファイル] > [PowerPoint へのエクスポート (プレビュー)]** を選択します (次の図を参照)。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_1.png)

レポートが PowerPoint にエクスポートされていることを示す通知バナーが、Power BI サービス ブラウザー ウィンドウの右上隅に表示されます。 これには数分間かかる場合があり、レポートのエクスポート中も Power BI で作業を進めることができます。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_2.png)

完了すると、Power BI サービスのエクスポート処理が終了したことが通知バナーで示されます。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_3.png)

ファイルは、ブラウザーがダウンロードしたファイルを表示する場所から使用できます。 次の図では、ブラウザー ウィンドウ下部のダウンロード バナーとして表示されています。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_4.png)

これで完了です。 ファイルをダウンロードし、PowerPoint で開き、他の PowerPoint デッキと同様に変更したり拡張したりできます。

## <a name="checking-out-your-exported-powerpoint-file"></a>エクスポートした PowerPoint ファイルの確認
Power BI でエクスポートした PowerPoint ファイルを開くと、便利な要素がいくつかあることに気付きます。 次の図を見てから、番号に対応する説明で機能を確認してください。

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_5.png)

1. スライド デッキの最初のページには、レポートの名前と、スライド デッキの基になっているレポートを表示する **[Power BI で表示する]** リンクが含まれます。
2. レポートに関する有用な情報も表示されます。エクスポートされたレポートの基になっている *前回のデータ更新* 日時や、Power BI レポートを PowerPoint ファイルにエクスポートした日時を示す *ダウンロード* 日時などです。
3. 左側のナビゲーション ウィンドウを見るとわかるように、各レポート ページは異なるスライドになっています。
4. 公開されたレポートは Power BI の言語設定かブラウザーのロケール設定に基づいてレンダリングされます。 言語の優先順位を表示または設定するには、歯車アイコン ![](media/service-report-subscribe/power-bi-settings-icon.png) **、[設定]、[全般]、[言語]** の順に選択します。 ロケール情報については、「[Power BI でサポートされる言語と国/地域](supported-languages-countries-regions.md)」を参照してください。
5. PowerPoint プレゼンテーションにはカバー スライドが含まれますが、そこには正しいタイム ゾーンの時刻がエクスポートされます。

個々のスライドを見ると、各ビジュアルが独立した画像になっていることがわかります。

>[!NOTE]
> レポート ページごとにビジュアルを 1 つ含める動作は、新しい動作となります。 ビジュアルごとに独立したイメージを指定していた以前の動作は、現在実装されていません。 
 

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_6.png)

PowerPoint デッキや高解像度画像についての作業を自由に行うことができます。

## <a name="limitations"></a>制限事項
**PowerPoint へのエクスポート**機能を使用するときに留意する必要のある注意事項と制限事項がいくつかあります。

* 現在、**R ビジュアル**はサポートされていません。 このようなビジュアルは空の画像として PowerPoint にエクスポートされ、サポートされていないビジュアルであるというエラー メッセージが表示されます。
* **認定を受けた****カスタム ビジュアル**はサポートされます。 カスタム ビジュアルの認定を受ける方法など、認定を受けたカスタム ビジュアルの詳細については、「[カスタム ビジュアルの*認定*を受ける](power-bi-custom-visuals-certified.md)」を参照してください。 認定を受けていないカスタム ビジュアルはサポートされず、空の画像として PowerPoint にエクスポートされ、サポートされていないビジュアルであるというエラー メッセージが表示されます。
* **認定済みカスタム ビジュアル**がサポートされています。 認定済みカスタム ビジュアルとは、Power BI で使用できるように承認され、所定のコードの要件を満たし、厳密なセキュリティ テストに合格したものです。 詳細については、[**認定済みカスタム ビジュアル**に関するページをご覧ください](power-bi-custom-visuals-certified.md)。
* 現在、レポート ページが 15 ページを超えるレポートはエクスポートできません。
* レポートを PowerPoint にエクスポートする処理には、数分かかる場合があります。 必要な時間に影響する要因としては、レポートの構造や、Power BI サービスの現在の負荷などがあります。
* Power BI サービスで **[PowerPoint へのエクスポート (プレビュー)]** メニュー項目を使用できない場合は、テナント管理者が機能を無効にしている可能性があります。 詳細については、テナント管理者に問い合わせてください。
* 背景画像はグラフの境界領域でトリミングされます。 PowerPoint にエクスポートする前に背景画像を削除することを強くお勧めします。
* 強調表示、フィルター処理、ドリルダウンなどの**セッション内の対話機能**は、PowerPoint へのエクスポートではまだサポートされていません。 エクスポートされた PowerPoint に表示されるのは、レポートに保存された時点での元のビジュアルです。
* PowerPoint のページは、Power BI レポートの元のページのサイズまたは寸法に関係なく、常に標準の 9:16 サイズで作成されます。
* Power BI テナント ドメイン外のユーザーによって所有されているレポート (組織外のユーザーが所有していて、そのユーザーから共有されているレポートなど) は、PowerPoint に発行できません。
* 組織外の人 (つまり、Power BI テナント内にいないユーザー) とダッシュボードを共有している場合、そのユーザーは共有されたダッシュ ボードに関連付けられているレポートを PowerPoint にエクスポートできません。 たとえば、ユーザー aaron@contoso.com は david@cohowinery.com と共有することができます。しかし、david@cohowinery.com は関連付けられたレポートを PowerPoint にエクスポートできません。
* 前述のように、各レポート ページは、PowerPoint ファイルに単一のイメージとしてエクスポートされます。
* Power BI サービスでは、Power BI の言語設定を PowerPoint のエクスポート用の言語として使用します。 言語の優先順位を表示または設定するには、歯車アイコン ![](media/service-report-subscribe/power-bi-settings-icon.png) **、[設定]、[全般]、[言語]** の順に選択します。
* エクスポートした PowerPoint ファイルの、表紙スライドの **[Downloaded at]\(ダウンロードした時刻\)** は、お使いのコンピューターのタイム ゾーンにおけるエクスポート時の時刻に設定されます。

## <a name="next-steps"></a>次の手順
[Excel で分析](service-analyze-in-excel.md)

[Power BI の Excel データ](service-excel-workbook-files.md)

[カスタム ビジュアルの認定を受ける](power-bi-custom-visuals-certified.md)

