---
title: "カスタム ビジュアルをレポートに追加する (Desktop)"
description: "Desktop でカスタム ビジュアルをレポートに追加する"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: b3a3e34fac546ee57cd66924e72a2c93aa647850
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="add-a-custom-visual-to-a-report-desktop"></a>カスタム ビジュアルをレポートに追加する (Desktop)
ここまでで、[カスタム ビジュアルのテンプレート](service-custom-visuals-office-store.md)をダウンロードし、コンピューターまたはその他の場所に保存することができました。  次の手順では、そのカスタム ビジュアル テンプレートをレポートにインポートすることにより、[ビジュアル化] ウィンドウにオプションとして追加できるようにします。

![](media/power-bi-custom-visuals-use/pbi-custom-viz-icon.png)

インポートしたカスタム ビジュアル テンプレートは、特定のレポートに追加されます。 ビジュアル テンプレートを別のレポートで使用する場合は、そのレポートにもインポートする必要があります。 カスタム ビジュアルを含むレポートを **[名前を付けて保存]** オプションを使って保存すると、カスタム ビジュアル テンプレートのコピーがその新しいレポートと共に保存されます。

1. Power BI Desktop を開き、カスタム ビジュアルを追加するレポートを選択します。   
2. カスタム ビジュアル テンプレートをインポートするには、 **[ファイル]** メニューから行う方法と **[視覚化]** ウィンドウから行う方法の 2 つの方法があります。
   
    **Desktop の [ファイル] メニューから**
   
    レポートの **[ファイル]** メニューで、**[インポート]** &gt; **[Power BI カスタム ビジュアル]** の順に選択します。 編集ビューを使用する必要があります。    
   
      ![](media/power-bi-custom-visuals-use/power-bi-import.png)
   
    **[視覚化] ウィンドウから**
   
    **[視覚化]** ウィンドウで、 **[挿入 (...)]**を選択します。    
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
   
    **[カスタム ビジュアルのインポート]** を選択します。  
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
3. **警告を確認します**。
   
    カスタム ビジュアルはレポート内のデータにアクセスでき、カスタム ビジュアルを含むレポートを共有すると、同僚がその同じデータにアクセスできる可能性があります。 カスタム ビジュアルを調べて信頼できるソースからのものであることを確認するようにしてください。 Office オンライン ストア、メール、他のソースから入手した特定のカスタム ビジュアルを使ってもよいかどうかわからない場合は、IT 部門に相談することをお勧めします。
   
    ![](media/power-bi-custom-visuals-use/caution.png)
4. カスタム ビジュアルの .pbiviz ファイルを保存した場所に移動して、それを開きます。
5. アイコン ( *テンプレート* とも呼ばれます) が **[視覚化]** ウィンドウに追加されます。
   
    ![](media/power-bi-custom-visuals-use/visualuse.png)
6. [視覚化] ウィンドウで他のテンプレートの場合と同じようにカスタム ビジュアル テンプレートを選択してレポートに追加します。 フィールドとフィルターを追加し、ビジュアルをビルドします。
7. 他のビジュアルと同じように、カスタム ビジュアルの書式を設定します。  **[視覚化]** ウィンドウで、ペイント ローラー アイコンを選びます。 利用可能な書式設定オプションは、ビジュアルのタイプによって異なります。

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
* [PowerPoint へのエクスポート](service-report-subscribe.md)、または*顧客がレポート ページにサブスクライブするときに受け取る電子メール*でカスタム ビジュアルがサポートされるようにするには、Microsoft カスタム ビジュアル認定プロセスに合格した[認定カスタム ビジュアル](service-publish-to-powerpoint.md)として定義される必要があります。  *認定カスタム ビジュアル*の一覧と認定プロセスの詳細については、「[Certified custom visuals](power-bi-custom-visuals-certified.md)」 (認定カスタム ビジュアル) を参照してください。

## <a name="next-steps"></a>次の手順
[Office ストアからカスタム ビジュアルをダウンロードして使用する](service-custom-visuals-office-store.md)  
[カスタム ビジュアルを Power BI サービスのレポートに追加する](power-bi-report-add-custom-visual.md)  
[カスタム ビジュアルを Office ストアに発行する](developer/office-store.md)  
[Power BI でのカスタム ビジュアル](power-bi-custom-visuals.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

