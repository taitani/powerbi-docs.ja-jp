---
title: "Power BI Desktop で CSV に接続する"
description: "Power BI Desktop で CSV ファイルのデータに簡単に接続して使用します"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: b8594dabcd4d0fa9e102f1ffe20456805833c02c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-csv-files-in-power-bi-desktop"></a>Power BI Desktop で CSV に接続する
Power BI Desktop からコンマ区切り値 (*CSV*) ファイルへの接続は、Excel ブックへの接続とよく似ています。 どちらも簡単です。この記事では、アクセス権がある CSV ファイルに接続する手順を説明します。

最初に、Power BI Desktop の **[ホーム]** リボンで **[データの取得]、[CSV]** の順に選択します。

![](media/desktop-connect-csv/connect-to-csv_1.png)

表示される **[開く]** ダイアログで CSV ファイルを選択します。

![](media/desktop-connect-csv/connect-to-csv_2.png)

**[開く]** を選択すると、Power BI Desktop はファイルにアクセスして、ファイルの作成元、区切り記号の種類、ファイルのデータの種類の特定に使用する必要がある行数などの特定のファイル属性を決定します。

これらのファイル属性とオプションは、次に示すように、**[CSV のインポート]** ダイアログ ウィンドウの上部にあるドロップダウン選択に表示されます。 検出されたこれらの設定は、ドロップダウンの選択肢から別のオプションを選択することにより手動で変更できます。

![](media/desktop-connect-csv/connect-to-csv_3.png)

選択が済んだら、**[読み込み]** を選択して Power BI Desktop にファイルをインポートするか、または **[編集]** を選択して **[クエリ エディター]** を開き、インポートする前にデータをさらに調整または変換できます。

Power BI Desktop にデータを読み込むと、Power BI Desktop のレポート ビューの右側の **[フィールド]** ウィンドウにテーブルとその列 (Power BI Desktop ではフィールドとして表示されます) が表示されます。

![](media/desktop-connect-csv/connect-to-csv_4.png)

CSV ファイルのデータを Power BI Desktop に取り込む手順は以上です。

Power BI Desktop でそのデータを使用して、表示やレポートを作成したり、Excel ブック、データベース、他のデータ ソースなどの他のデータに接続してインポートしたりできます。

### <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

