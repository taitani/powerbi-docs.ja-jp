---
ms.openlocfilehash: eb7cba03daee47f6772fc46be50419731b41765e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61194141"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Power BI Desktop 内でロールを検証する
ロールを作成したら、Power BI Desktop 内でロールの結果をテストします。

1. **[ロールとして表示]** を選択します。 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    **[ロールとして表示]** に、作成したロールが表示されます。

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. 作成したロールを選択し、 **[OK]** を選択して、そのロールを適用します。 レポートでは、そのロールに関連するデータがレンダリングされます。 

4. **その他のユーザー**を選択し、特定のユーザーを指定することもできます。 ユーザー プリンシパル名 (UPN) を、Power BI サービスおよび Power BI Report Server で使用されるものとして指定することをお勧めします。

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. **[OK]** を選択すると、ユーザーに表示される内容に基づいてレポートがレンダリングされます。 

Power BI Desktop の **[その他のユーザー]** には、DAX 式に基づいた動的セキュリティを使用している場合、異なる結果のみが表示されます。 

