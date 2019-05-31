---
title: 追加の診断情報をキャプチャします。
description: 次の手順では、Power BI Web クライアントから追加の診断情報を手動で収集するために可能性のある 2 つのオプションを提供します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100228"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Power BI 用の追加の診断情報をキャプチャします。

この記事では、Power BI web クライアントから手動で追加の診断情報を収集するための手順を提供します。

1. 参照する[Power BI](https://app.powerbi.com) Microsoft Edge または Internet Explorer。

1. キーを押して**F12** Microsoft Edge の開発者ツールを開きます。

   ![Microsoft Edge の開発者のスクリーン ショット ツール タブ。](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. **[ネットワーク]** タブを選びます。既ににキャプチャされたトラフィックが一覧表示されます。

   ![Microsoft Edge の開発者のスクリーン ショット ツール ネットワーク タブ。](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    次の操作を実行できます。

    * ウィンドウを参照し、遭遇する可能性があります、問題を再現します。

    * 非表示にし、F12 キーを押して、セッション中にいつでも、開発者ツール ウィンドウを表示します。

1. プロファイリング セッションを停止するの赤い四角形を選択できる、**ネットワーク** タブの開発者ツールの領域。

   ![停止 ボタンからの呼び出しで Microsoft Edge の開発者のスクリーン ショット ツール ネットワーク タブ。](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. HTTP アーカイブ (HAR) ファイルとしてデータをエクスポートするフロッピー ディスクのアイコンを選択します。

   ![フロッピー ディスクのアイコンのコールアウトを含む Microsoft Edge の開発者のスクリーン ショット ツール ネットワーク タブ。](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. ファイル名を指定し、HAR ファイルを保存します。

    HAR ファイル ブラウザーのウィンドウと Power BI などの間のネットワーク要求に関するすべての情報が含まれます。

    * 各要求のアクティビティ Id。

    * 各要求の正確なタイムスタンプ。

    * すべてのエラー情報は、クライアントに返されます。

    このトレースには、画面に表示されるビジュアルを設定するのに使われるデータも含まれます。

1. サポートのレビュー用にも HAR ファイルを提供できます。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
