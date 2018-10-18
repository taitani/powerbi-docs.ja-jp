---
title: Power BI Desktop で Power BI データフローによって作成されたデータに接続する (プレビュー)
description: Power BI Desktop でデータフローに簡単に接続して使用します
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/10/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f3964b96f8f282772f6d511c9c412e0caabd1d00
ms.sourcegitcommit: c51461690e8faa121a1325957ca79b7a3975e8b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2018
ms.locfileid: "44512909"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-preview"></a>Power BI Desktop で Power BI データフローによって作成されたデータに接続する (プレビュー)
**Power BI Desktop** では、Power BI Desktop の他のデータ ソースと同様に、**Power BI データフロー**によって作成されたデータに接続できます。

![データフローへの接続](media/desktop-connect-dataflows/connect-dataflows_01.png)

**Power BI データフロー (プレビュー)** コネクタを使用すると、Power BI サービスでデータフローによって作成されたエンティティに接続できます。 データフローはプレビュー段階なので、システムでデータフロー コネクタを使用できるようにするためにいくつかの手順を行う必要があります。 


## <a name="download-and-enable-the-power-bi-dataflows-connector-preview"></a>Power BI データフロー コネクタをダウンロードして有効にする (プレビュー)

**Power BI データフロー** コネクタのコピーをダウンロードし、コンピューター上の特定の場所にコピーする必要があります。 Power BI Desktop の次回の月次更新プログラムでは、データ コネクタの一覧にこのコネクタが自動的に含まれるので、この手順は不要になります。

**Power BI データフロー コネクタ**は次の場所からダウンロードできます: [Power BI データフロー コネクタ](https://visuals.azureedge.net/cds-analytics/PublicPreview/CDSA.mez)

**Power BI データフロー** コネクタ (プレビュー) をコンピューターで使用できるようにするには、次の手順を行います。

1. .MEZ ファイル (データ コネクタ ファイル) のコピーをダウンロードします。 プライベート プレビューのお客様は、.MEZ ファイルのダウンロード情報を Microsoft から直接受信します。

2. ダウンロードされたデータ コネクタ ファイルを、コンピューター上の**ドキュメント > Power BI Desktop > カスタム コネクタ フォルダー**に配置します。

3. Power BI Desktop で、**[ファイル]、[オプションと設定]、[オプション]** の順に選択し、左側のウィンドウで **[プレビュー機能]** を選択します。

    ![カスタム コネクタの有効化](media/desktop-connect-dataflows/connect-dataflows_02.png)

4. **[カスタム データ コネクタ]** ボックスがオンになっていない場合は、オンにします。 

5. **Power BI Desktop** を再起動して、コネクタを表示します。

## <a name="use-the-power-bi-dataflows-connector-preview"></a>Power BI データフロー コネクタを使用する (プレビュー)
**Power BI Desktop** が再起動されると、コネクタが利用可能なデータ ソースとして表示されます。 データプールに接続するには、次の図に示すように、**[データの取得]、[オンライン サービス]、[Power BI データフロー (ベータ)]** の順に選択します。

![データフローへの接続](media/desktop-connect-dataflows/connect-dataflows_01.png)

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

このプレビュー バージョンの **Power BI データフロー コネクタ**を使用するには、最新バージョンの **Power BI Desktop** を実行している必要があります。 最新バージョンを確保するために、いつでも [Power BI Desktop をダウンロード](desktop-get-the-desktop.md)し、コンピューターにインストールできます。  

注: **Power BI Desktop** の次回の月次更新プログラムで Power BI データフロー コネクタが表示されたら、このダウンロードされた .MEZ ファイルを**ドキュメント > Power BI Desktop > カスタム コネクタ** フォルダーから削除する*必要があります*。 


## <a name="next-steps"></a>次の手順
Power BI データ接続を使用して、さまざまな目的の処理を実行できます。また、**Power BI Desktop** に関する次の記事を参照すると役立ちます。

* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

