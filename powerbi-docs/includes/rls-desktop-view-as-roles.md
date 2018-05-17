## <a name="validating-the-role-within-power-bi-desktop"></a>Power BI Desktop 内でのロールの検証
ロールの作成後、Power BI Desktop 内でロールの結果をテストできます。 これを行うには、**[ロールとして表示]** を選択します。

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

**[ロールとして表示]** ダイアログでは、その特定のユーザーまたはロールに対して表示されるビューを変更できます。 作成したロールを表示できます。

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

作成したロールを選択し、**[OK]** を選択すると、そのロールが表示内容に適用されます。 レポートには、そのロールに関連するデータのみが表示されます。

**その他のユーザー**を選択し、特定のユーザーを指定することもできます。 Power BI サービスで使用されるユーザー プリンシパル名 (UPN) を指定することをお勧めします。 **[OK]** を選択すると、ユーザーに表示される内容に基づいてレポートがレンダリングされます。 

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

> [!NOTE]
> Power BI Desktop 内では、DAX 式に基づいて動的セキュリティを使用している場合、異なる結果のみが表示されます。
> 
> 

