---
title: オンプレミスとクラウド データ ソースのマージまたはアペンド
description: オンプレミス データ ゲートウェイを使用し、オンプレミスとクラウドのデータ ソースを同じクエリでマージまたはアペンドします。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7b863af882604be8c2c59fd21f26cd8441f9e170
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54272653"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>オンプレミスとクラウド データ ソースのマージまたはアペンド

オンプレミス データ ゲートウェイを使用すると、オンプレミスとクラウドのデータ ソースを同じクエリでマージまたはアペンドできます。 これは、別個のクエリを使用せず、複数のソースからのデータをマッシュアップするときに便利です。

## <a name="prerequisites"></a>前提条件

- ローカル コンピューターに[ゲートウェイがインストールされている](service-gateway-install.md)こと。
- オンプレミスとクラウドのデータ ソースを結合するクエリを含む Power BI Desktop ファイル。

1. Power BI サービスの右上にある歯車アイコン ![[設定] 歯車アイコン](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **[ゲートウェイの管理]** の順に選択します。

    ![ゲートウェイの管理](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. 構成するゲートウェイを選択します。

3. **[ゲートウェイ クラスターの設定]** で **[Allow user's cloud data sources to refresh through this gateway cluster]\(このゲートウェイ クラスターでユーザーのクラウド データ ソースを更新することを許可します\)** > **[適用]** の順に選択します。

    ![このゲートウェイ クラスターで更新する](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. このゲートウェイ クラスターの下で、クエリで使用される[オンプレミス データ ソース](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source)があれば、それを追加します。 ここではクラウド データ ソースを追加する必要がありません。

5. オンプレミスとクラウドのデータ ソースを結合するクエリを含む Power BI Desktop ファイルを Power BI サービスにアップロードします。

6. 新しいデータセットの **[データセットの設定]** ページで:

   - オンプレミス ソースの場合、このデータ ソースに関連付けられているゲートウェイを選択します。

   - **[データ ソースの資格情報]** の下で、必要に応じてクラウド データ ソースの資格情報を編集します。

     ![データセットの設定](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. クラウドの資格情報が設定されたので、**[今すぐ更新]** オプションを利用してデータセットを更新できるようになりました。あるいは、定期的に更新するようにスケジュールを設定できます。


## <a name="next-steps"></a>次の手順

ゲートウェイのデータ更新の詳細については、[更新のスケジュール設定にデータ ソースを使用する](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh)方法に関するページを参照してください。