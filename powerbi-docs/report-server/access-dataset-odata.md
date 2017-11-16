---
title: "Power BI Report Server で OData フィードとして共有データセットにアクセスする"
description: "Power BI レポートは、さまざまなデータ ソースに接続できます。 データの使い方に応じて、異なるデータ ソースを利用できます。"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: f31d37b6fe9c0e4695719b9bbaa13a2c8deabc75
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="accessing-shared-datasets-as-odata-feeds-in-power-bi-report-server"></a>Power BI Report Server で OData フィードとして共有データセットにアクセスする
OData フィードを使って Power BI Desktop から共有データセットにアクセスできます。

1. OData フィード URL では、OData ソースに接続します。
   
    ![レポート サーバーの OData フィード ソース](media/access-dataset-odata/report-server-odata-feed.png)
2. Power BI Desktop にデータを取り込んだ後は、クエリ エディターを使って変更できます。
   
    ![Power BI Desktop のクエリ エディターと OData フィード](media/access-dataset-odata/report-server-odata-results-query-editor.png)
3. レポートの設計でデータを使えるようになりました。
   
    ![Power BI Desktop レポートの設計と OData フィード](media/access-dataset-odata/report-server-odata-power-bi-desktop-report-design.png)

オープン型の列を有効にして、ニーズに合わせて Power Query で列を適切に書式設定できるように、**[詳細オプション]** を使ってください。

詳細については、「[Power BI Desktop で OData フィードに接続する](../desktop-connect-odata.md)」をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

