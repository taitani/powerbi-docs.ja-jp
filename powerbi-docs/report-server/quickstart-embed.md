---
title: iFrame を使用してレポートを埋め込む
description: SharePoint Server の iFrame に Power BI Report Server レポートを埋め込む
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.component: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 802107ce9c12075ffc51461375ca3e9a313f2be1
ms.sourcegitcommit: 9c3a9ec14c111d766ef5703366c316e72f6e588f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45558426"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>クイック スタート: SharePoint Server の iFrame を使用して Power BI Report Server レポートを埋め込む

このクイック スタートでは、SharePoint ページの iFrame を使用して Power BI Report Server レポートを埋め込む方法について説明します。 SharePoint Online を使用している場合は、Power BI Report Server にパブリックにアクセスできる必要があります。 SharePoint Online では、Power BI サービスで動作する Power BI Web パーツは、Power BI Report Server で動作しません。 

![iFrame のサンプル](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>前提条件
* [Power BI Report Server](https://powerbi.microsoft.com/en-us/report-server/) をインストールする必要があります。
* [Power BI Report Server 向けに最適化された Power BI Desktop](install-powerbi-desktop.md) をインストールする必要があります。
* [SharePoint](https://docs.microsoft.com/sharepoint/install/install) 環境をインストールし、構成する必要があります。

## <a name="creating-the-power-bi-report-server-report-url"></a>Power BI Report Server のレポート URL の作成

1. GitHub からサンプル [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) をダウンロードします。

    ![サンプル PBIX ファイルをダウンロードする](media/quickstart-embed/quickstart_embed_14.png)

2. **Power BI Desktop 向けに最適化された Power BI Desktop** で GitHub のサンプル PBIX ファイルを開きます。

    ![PBI RS Desktop ツール](media/quickstart-embed/quickstart_embed_02.png)

3. レポートを **Power BI Report Server** に保存します。 

    ![PBI RS の保存](media/quickstart-embed/quickstart_embed_03.png)

4. **Web ポータル**でレポートを表示します。

    ![Web ポータル](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>URL パラメーターの取得

URL を用意したら、レポートをホストする iFrame を SharePoint ページ内に作成できます。 Power BI Report Server のレポートの URL には、querystring パラメーター `?rs:embed=true` を追加してレポートを iFrame に埋め込むことができます。 

   例:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>PowerBI Report Server レポートを SharePoint の iFrame に埋め込む

1. SharePoint の **[サイト コンテンツ]** ページに移動します。

    ![[サイト コンテンツ] ページ](media/quickstart-embed/quickstart_embed_05.png)

2. レポートを追加するページを選択します。

    ![[サイト コンテンツ] ページのアプリ](media/quickstart-embed/quickstart_embed_06.png)

3. 右上の歯車アイコンを選択し、**[ページの編集]** を選択します。

    ![[ページの編集] オプション](media/quickstart-embed/quickstart_embed_07.png)

4. **[Web パーツの追加]** を選択します。

    ![Web パーツの追加](media/quickstart-embed/quickstart_embed_08.png)

5. **[カテゴリ]** で **[メディアとコンテンツ]** を選択し、**[パーツ]** で **[コンテンツ エディター]** を選択して **[追加]** を選択します。

    ![[コンテンツ エディター] Web パーツを選択し](media/quickstart-embed/quickstart_embed_09.png)、![[追加] を選択する](media/quickstart-embed/quickstart_embed_091.png)

6. **[ここをクリックして新しいコンテンツを追加]** を選択します。

    ![新しいコンテンツの追加](media/quickstart-embed/quickstart_embed_10.png)

7. リボンの **[テキストの書式設定]** タブを選択し、**[ソースの編集]** を選択します。

     ![ソースの編集](media/quickstart-embed/quickstart_embed_11.png)

8. [ソースの編集] ウィンドウに iFrame コードを貼り付け、[OK] を選択します。

    ![iFrame コード](media/quickstart-embed/quickstart_embed_12.png)

     例:
     ```
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. リボンの **[テキストの書式設定]** タブを選択し、**[編集の終了]** を選択します。

    ![編集の終了](media/quickstart-embed/quickstart_embed_13.png)

10. これでページにレポートが表示されます。

    ![iFrame のサンプル](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>次の手順

[クイックスタート: Power BI レポート サーバーの Power BI レポートの作成](quickstart-create-powerbi-report.md)  
[クイックスタート: Power BI Report Server のページ分割されたレポートの作成](quickstart-create-paginated-report.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。 