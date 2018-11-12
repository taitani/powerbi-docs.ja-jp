---
title: データ記憶域を管理する
description: レポートおよびデータセットを引き続き確実に発行できるように、個々のユーザー、アプリ ワークスペース、データ記憶域を管理する方法について説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: 864d50d8850a8ceed964f128cea71b0daf5d8322
ms.sourcegitcommit: ac63e6a082ca8397909217837e8d98c9389b23ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50736874"
---
# <a name="manage-your-data-storage"></a>データ記憶域を管理する
レポートおよびデータセットを引き続き確実に発行できるように、個々のユーザー、アプリ ワークスペース、データ記憶域を管理する方法について説明します。

ユーザーとアプリ ワークスペースには固有のデータ容量が割り当てられている

* すべてのユーザーが最大 10 GB のデータ ストレージを持っています。
* Power BI Pro ライセンスを所有するユーザーはアプリ ワークスペースを作成することができ、それぞれのデータ ストレージの上限は 10 GB です。

テナント レベルでは、テナント内のすべての Pro ユーザーとアプリ ワークスペースにおいて、総使用量が Pro ユーザー 1 人あたり 10 GB を超えることはできません。

「[Power BI 料金モデル](https://powerbi.microsoft.com/pricing)」のその他の特徴もご覧ください。

データ記憶域には、ユーザー個人のデータセットと Excel レポートに加えて、他のユーザーと共有したデータセットと Excel レポートも含まれます。 データセットとは、アップロードまたは接続しているデータ ソースのことで、これには使用している Power BI Desktop ファイルや Excel ブックも含まれます。 データ容量には以下も含まれます。

* ダッシュボードにピン留めされたExcel の範囲。
* Power BI ダッシュボードにピン留めされた Reporting Services オンプレミス ビジュアル効果。
* アップロードされたイメージ。

共有ダッシュボードのサイズは、ピン留めされている項目に応じて異なります。 たとえば、2 つの異なるデータセットの一部である 2 つのレポートから項目をピン留めした場合は、2 つのデータセットがサイズに含まれます。

<a name="manage"/>

## <a name="manage-items-owned-by-you"></a>所有する項目の管理
Power BI アカウントで使用しているデータ記憶域を確認して、アカウントを管理します。

1. 自分の記憶域を管理するには、左側のナビゲーション ウィンドウの **[マイ ワークスペース]** に移動します。
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. 右上隅にある歯車アイコン ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)、\>[個人の記憶域の管理] **の順にクリックします**。
   
    上部のバーに、記憶域の上限のうちの使用量が表示されます。
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    データセットとレポートは、2 つのタブに分かれています。
   
    **自分の所有:** あなたが自分の Power BI アカウントにアップロードしたレポートやデータセットで、Salesforce や Dynamics CRM などのサービス データセットが含まれます。  
    **他のユーザーの所有:** 他のユーザーから共有を受けたレポートやデータセットです。
3. データセットやレポートを削除するには、ごみ箱のアイコン ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png) をクリックします。

データセットが、自分や他のユーザーが作成したレポートやダッシュボードの基になっている可能性があることにご注意ください。 そのデータセットを削除してしまうと、これらのレポートやダッシュボードは機能しなくなります。

## <a name="manage-your-app-workspace"></a>アプリ ワークスペースの管理
1. **[ワークスペース]**\> の横にある矢印をクリックし、アプリ ワークスペースの名前を選択します。
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. 右上隅にある歯車アイコン ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)、\>[グループの記憶域の管理] **の順にクリックします**。
   
    上部のバーに、グループの記憶域の上限のうちの使用量が表示されます。
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    データセットとレポートは、2 つのタブに分かれています。
   
    **グループの所有:** 自分か他の誰かがグループの Power BI アカウントにアップロードしたレポートやデータセットで、Salesforce や Dynamics CRM などのサービス データセットが含まれます。
    **他のユーザーの所有:** 他のユーザーから自分のグループが共有を受けたレポートやデータセットです。
3. データセットやレポートを削除するには、ごみ箱のアイコン ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png) をクリックします。
   
   > [!NOTE]
   > アプリ ワークスペースのメンバー (編集アクセス許可を持つ) はいずれも、アプリ ワークスペースからデータセットやレポートを削除するアクセス許可を持っています。
   > 
   > 

データセットが、自分かグループ内の他のユーザーが作成したレポートやダッシュボードの基になっている可能性があることにご注意ください。 そのデータセットを削除してしまうと、これらのレポートやダッシュボードは機能しなくなります。

## <a name="dataset-limits"></a>データセットの制限
Power BI にインポートされるデータセットごとに 1 GB の制限があります。 データをインポートするのではなく、Excel でのエクスペリエンスを維持することを選択した場合、データセットは 250 MB に制限されます。

## <a name="what-happens-when-you-hit-a-limit"></a>上限に達したときの動作
利用できるデータ容量の上限に達すると、サービス内にメッセージが表示されます。 

歯車アイコン ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) を選択すると、データ容量の上限を超えていることを示す赤いバーが表示されます。

![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

また、 **[パーソナル ストレージの管理]** 内にも、同様のバーが表示されます。

 ![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 データ容量の上限を超えるアクションを実行しようとすると、上限を超えることを示すメッセージが表示されます。 記憶域を適切に[管理する](#manage)ことで、記憶域のデータ量を削減し、制限に対処することができます。

 ![](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

