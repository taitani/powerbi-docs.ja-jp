---
title: Power BI と Office 365 でアプリ ワークスペースを管理する
description: Power BI のアプリ ワークスペースは、Office 365 グループ上に構築されたコラボレーション エクスペリエンスです。 Power BI および Office 365 でアプリ ワークスペースを管理します。
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/02/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d900d8622f086ef28f39ee050e9e9f1639dfd53d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61231578"
---
# <a name="manage-your-app-workspace-in-power-bi-and-office-365"></a>Power BI と Office 365 でアプリ ワークスペースを管理する
Office 365 または [Power BI でのアプリ ワークスペース](service-create-distribute-apps.md)の作成者または管理者として、Power BI でワークスペースの一部の側面を管理します。 その他の側面は、Office 365 で管理します。 

> [!NOTE]
> 新しいワークスペース エクスペリエンス プレビューでは、Power BI ワークスペースと Office 365 グループ間の関係が変わります。 新しいワークスペースのいずれかを作成するたびに、Office 365 グループが自動的に作成されることはありません。 新しいワークスペース (プレビュー) の作成については、[こちら](service-create-the-new-workspaces.md)を参照してください。

**Power BI** では、次のことができます。

* アプリ ワークスペース メンバーを追加または削除します (ワークスペース メンバーを管理者にすることもできます)。
* アプリ ワークスペース名を編集します。
* アプリ ワークスペースを削除します。

**Office 365** では、次のことができます。

* アプリ ワークスペースのグループ メンバーを追加または削除します (メンバーを管理者にする操作も含まれます)。
* グループ名、画像、説明、およびその他の設定を編集します。
* グループの電子メール アドレスを参照します。
* グループを削除します。

アプリ ワークスペースの管理者またはメンバーになるには、[Power BI Pro](service-features-license-type.md) ライセンスが必要です。 アプリ ワークスペースが Power BI Premium 容量にない場合は、アプリ ユーザーにも Power BI Pro ライセンスが必要です。 詳しくは、[Power BI Premium](service-premium-what-is.md) に関するページをご覧ください。

## <a name="edit-your-app-workspace-in-power-bi"></a>Power BI でアプリ ワークスペースを編集する
1. Power BI サービスで、 **[ワークスペース]** の横にある矢印を選択し、目的のワークスペース名の横にある省略記号 ( **…** ) を選択して、 **[ワークスペースの編集]** を選択します。 
   
   ![Power BI でのワークスペースの編集](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-ellipsis.png)
   
   > [!NOTE]
   > アプリ ワークスペース管理者の場合は、 **[Edit workspace (ワークスペースの編集)]** のみが表示されます。
   > 
   > 
2. ここでは、メンバーの名前を変更したり、メンバーを追加または削除したり、アプリ ワークスペースを削除したりできます。 
   
   ![[ワークスペースの編集] ダイアログ ボックス](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-edit-workspace.png)
3. **[保存]** または **[キャンセル]** を選びます。

## <a name="edit-power-bi-app-workspace-properties-in-office-365"></a>Office 365 で Power BI アプリ ワークスペースのプロパティを編集する
1. Power BI サービスで、 **[ワークスペース]** の横にある矢印を選択し、目的のワークスペース名の横にある省略記号 ( **…** ) を選択して、 **[メンバー]** を選択します。 
   
   ![Power BI でのワークスペースの編集](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-ellipsis.png)
   
   サインインすると、アプリ ワークスペースの Outlook for Office 365 グループ ビューが開きます。
   
   会社のアカウントにサインインする必要があります。
2. メンバーの名前の横にある省略記号 ( **[...]** ) をタップして、メンバーを管理者にしたり、メンバーをアプリ ワークスペースから削除したりできます。 
   
   ![Office 365 でのグループの編集](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_managegroupo365.png)

## <a name="add-an-image-and-set-other-workspace-properties-in-the-office-365-group"></a>イメージを追加して Office 365 グループでその他のワークスペースのプロパティを設定する
アプリ ワークスペースからアプリを配布するときに、ここで追加したイメージは、アプリのイメージになります。 [新しいワークスペースの作成](service-create-workspaces.md)に関する記事の[アプリへのイメージの追加](service-create-workspaces.md#add-an-image-to-your-office-365-app-workspace-optional)についてのセクションを参照してください。

1. アプリ ワークスペースの Outlook for Office 365 ビューで、グループ ワークスペース プロパティを編集するグループ イメージを選択します。
   
   ![[グループの編集] アイコン](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_editgroupo365.png)
2. ここで名前、説明、言語を編集し、イメージを追加し、その他のプロパティを設定できます。
   
   ![[グループの編集] ダイアログ ボックス](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_editgrpo365dialog.png)
3. **[保存]** または **[破棄]** を選択します。

## <a name="next-steps"></a>次の手順
* [Power BI でダッシュボードとレポートを含むアプリを発行する](service-create-distribute-apps.md)
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

