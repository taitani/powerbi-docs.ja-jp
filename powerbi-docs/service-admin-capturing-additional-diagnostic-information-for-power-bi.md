---
title: 追加の診断情報のキャプチャ
description: 追加の診断情報のキャプチャ
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 65954c19087e9c9968c549f610d4e36e942e3206
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="capturing-additional-diagnostic-information"></a>追加の診断情報のキャプチャ
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Power BI 用に追加の診断情報をキャプチャする
次の手順では、Power BI Web クライアントから追加の診断情報を手動で収集するために可能性のある 2 つのオプションを提供します。  いずれかのオプションを実行すれば十分です。

## <a name="network-capture---edge--internet-explorer"></a>ネットワーク キャプチャ - Microsoft Edge および Internet Explorer
1. Microsoft Edge または Internet Explorer で [Power BI](https://app.powerbi.com) を参照します。
2. F12 キーを押して Edge 開発者ツールを開きます。
3. 開発者ツール ウィンドウが表示されます。 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. [ネットワーク] タブに切り替えます。既ににキャプチャされたトラフィックが一覧表示されます。 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. ウィンドウを参照して、発生している可能性がある問題を再現できます。 セッション中にいつでも F12 キーを押して、開発者ツール ウィンドウの表示/非表示を切り替えることができます。
6. キャプチャを停止するには、開発者ツール領域の [ネットワーク] タブの赤い四角形を選択します。
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. **HAR としてエクスポート**するにはフロッピー ディスクのアイコンを選択します。
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. ファイル名を指定し、HAR ファイルを保存します。
   
    HAR ファイルには、ブラウザー ウィンドウと Power BI の間のネットワーク要求に関するすべての情報が含まれます。  それには、各要求のアクティビティ ID、各要求の正確なタイムスタンプ、クライアントに返されるエラー情報が含まれます。  このトレースには、画面に表示されるビジュアルを設定するのに使われるデータも含まれます。
9. サポートのレビュー用にも HAR ファイルを提供できます。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

