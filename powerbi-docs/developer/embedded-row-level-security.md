---
title: "Power BI の埋め込みコンテンツで行レベルのセキュリティを使用する"
description: "ここでは、アプリケーション内に Power BI コンテンツを埋め込むために必要な手順について説明します。"
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
ms.date: 10/09/2017
ms.author: asaxton
ms.openlocfilehash: 1ab1590146f8b9714a27735cd556dd0203ecc6bf
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2017
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Power BI の埋め込みコンテンツで行レベルのセキュリティを使用する
行レベル セキュリティ (RLS) を使うと、レポートまたはデータセット内のデータへのユーザー アクセスを制限でき、同じレポートで異なるユーザーに異なるデータを表示することができます。 Power BI からレポートを埋め込むときに、RLS を利用できます。

Power BI 以外のユーザー (アプリ所有データ) のために埋め込む場合は (一般に ISV のシナリオ)、この記事をお読みください。 ユーザーおよびロールを考慮するために埋め込むトークンを構成する必要があります。 方法については後で説明します。

組織内の Power BI ユーザー (ユーザー所有データ) のために埋め込む場合は、RLS は Power BI サービスで直接使う場合と同じように動作します。 アプリケーションではそれ以上何も行う必要ありません。 詳しくは、「[Power BI での行レベルのセキュリティ (RLS)](../service-admin-rls.md)」をご覧ください。

![行レベル セキュリティに含まれる項目。](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

RLS を利用するには、ユーザー、ロール、ルールの 3 つの主要な概念を理解することが重要です。 それぞれについて詳しく説明します。

**ユーザー** – レポートを表示する実際のエンドユーザーです。 Power BI Embedded では、ユーザーは埋め込みトークンのユーザー名プロパティによって識別されます。

**ロール** – ユーザーはロールに属しています。 ロールはルールのコンテナーであり、"*営業マネージャー*" や "*営業担当者*" のような名前を付けます。ロールは Power BI Desktop で作成します。 詳しくは、「[Power BI Desktop での行レベルのセキュリティ (RLS)](../desktop-rls.md)」をご覧ください。

**ルール** – ロールにはルールが割り当てられ、それらのルールはデータに適用される実際のフィルターです。 ルールは、"Country = USA" のような単純なものもあれば、もっと動的なものもあります。
以降では、RLS を作成し、埋め込みアプリケーション内でそれを使う方法の例を説明します。 この例では、[小売の分析のサンプル](http://go.microsoft.com/fwlink/?LinkID=780547)の PBIX ファイルを使います。

![レポートの例](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Power BI Desktop でのロールの追加
小売りの分析のサンプルでは、小売チェーンのすべての店舗の売上が表示されます。 RLS を使わないと、どの地域のマネージャーがサインインしてレポートを表示しても、同じデータが表示されます。 各マネージャーが自分の管理する店舗の売上のみを見ることができるようにする場合は、RLS を使って実現できます。

RLS は Power BI Desktop で作成します。 データセットとレポートを開いた後は、ダイアグラム表示に切り替えてスキーマを見ることができます。

![Power BI Desktop のダイアグラム表示](media/embedded-row-level-security/powerbi-embedded-schema.png)

このスキーマについては注意することがいくつかあります。

* **Total Sales** などのすべてのメジャーは、**Sales** ファクト テーブルに格納されます。
* 他に **Item**、**Time**、**Store**、**District** の 4 つの関連ディメンション テーブルがあります。
* リレーションシップの線の矢印は、テーブル間でフィルターが適用される方向を示します。 たとえば、現在のスキーマの **Time[Date]** にフィルターを設定すると、**Sales** テーブルの値だけにフィルターが適用されます。 リレーションシップを示す線のすべての矢印は Sales テーブルを向いており、逆向きはないので、このフィルターによって他のテーブルは影響を受けません。
* **District** テーブルは、各地域のマネージャーを示します。
  
    ![Disctrict テーブル内の行](media/embedded-row-level-security/powerbi-embedded-district-table.png)

このスキーマを基にすると、**District** テーブルの **District Manager** 列にフィルターを適用し、そのフィルターがレポートを表示しているユーザーと一致した場合、そのフィルターはさらに **Store** テーブルと **Sales** テーブルにも適用されて、その地域マネージャーのデータだけが表示されます。

次にその方法を示します。

1. **[モデリング]** タブで **[ロールの管理]** を選びます。
   
    ![Power BI Desktop の [モデリング] タブ](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. **Manager** という名前の新しいロールを作成します。
   
    ![新しいロールを作成する](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. **District** テーブルに、「**[District Manager] = USERNAME()**」という DAX 式を入力します。
   
    ![RLS ルールの DAX ステートメント](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. ルールが動作することを確認するには、**[モデリング]** タブで **[ロールとして表示]** を選び、作成した **Manager** ロールと **[その他のユーザー]** の両方を選びます。 ユーザーとして「**Andrew Ma**」と入力します。
   
    ![[ロールとして表示] ダイアログ](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    レポートには、**Andrew Ma** としてサインインした場合のデータが表示されます。

ここでのフィルター適用方法では、**District**、**Store**、**Sales** の各テーブルのすべてのレコードがフィルター処理されます。 ただし、リレーションシップでのフィルターの向きのため、**Sales** テーブルから **Time** テーブル、**Sales** テーブルから **Item** テーブル、**Item** テーブルから **Time** テーブルには、フィルターは適用されません。 双方向のクロス フィルター処理について詳しくは、「[Bidirectional cross-filtering in SQL Server Analysis Services 2016 and Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)」(SQL Server Analysis Services 2016 と Power BI Desktop での双方向クロス フィルター処理) ホワイトペーパーをダウンロードしてご覧ください。

## <a name="applying-user-and-role-to-an-embed-token"></a>埋め込みトークンへのユーザーとロールの適用
Power BI Desktop でロールを構成したので、ロールを利用するための処理がアプリケーションに必要です。

ユーザーはアプリケーションによって認証および承認され、特定の Power BI Embedded レポートへのアクセスを、埋め込みトークンを使って許可されます。 Power BI Embedded は、ユーザーについての具体的な情報を持っていません。 RLS が機能するためには、埋め込みトークンの一部として、ID の形式で追加コンテキストを渡す必要があります。 これを行うには、[GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) API を使います。

[GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) API は、ID とそれに関連するデータセットを示す値を受け取ります。 現在は、指定できる ID は 1 つのみです。 将来、複数のデータセットのサポートがダッシュボードの埋め込みに追加されます。 RLS が機能するには、ID の一部として次の値を渡す必要があります。

* **ユーザー名 (必須)** – RLS ルールを適用するときにユーザーの識別に使うことができる文字列です。 指定できるユーザーは 1 人だけです。
* **ロール (必須)** – 行レベル セキュリティのルールを適用するときに選択するロールを含む文字列です。 複数のロールを渡す場合は、文字列の配列として渡す必要があります。
* **データセット (必須)** – 埋め込むレポートで使われるデータセットです。 データセットの一覧で指定できるデータセットは 1 つだけです。 複数のデータセットは、将来のダッシュボードの埋め込みでサポートされるようになります。

**PowerBIClient.Reports** で **GenerateTokenInGroup** メソッドを使って、埋め込みトークンを作成できます。 現在は、レポートのみがサポートされています。

たとえば、[PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) サンプルを変更できます。 "*Home\HomeController.cs の 76 および 77 行目*" は次のようになっています。

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

これを次のように変更します。

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

REST API を呼び出すと、更新された API は、ユーザー名、ロール文字列のリスト、データセット文字列のリストを含む **identities** という名前の追加 JSON 配列を受け取ります。次はその例です。

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

すべてがそろったので、ユーザーがアプリケーションにログインしてこのレポートを表示すると、行レベル セキュリティによる定義に従い、見ることを許可されているデータだけが表示されます。

## <a name="working-with-analysis-services-live-connections"></a>Analysis Services ライブ接続を使用する
行レベルのセキュリティをオンプレミス サーバーの Analysis Services ライブ接続と併用できます。 この種類の接続を利用するには、いくつかの概念を理解しておく必要があります。

ユーザー名プロパティとして有効な ID は、Analysis Services サーバーのアクセス許可を持つ Windows ユーザーです。

**オンプレミス データ ゲートウェイ構成**

[オンプレミス データ ゲートウェイ](../service-gateway-onprem.md)は、Analysis Services ライブ接続の使用時に利用されます。 埋め込みトークンの生成時、ID が一覧表示された状態で、マスター アカウントをゲートウェイの管理者として一覧表示する必要があります。 マスター アカウントが一覧表示されない場合、行レベルのセキュリティがデータに正しく適用されません。 ゲートウェイの管理者ではないユーザーは役割を与えることができますが、有効な ID として自分のユーザー名を指定する必要があります。

**役割の使用**

役割は、埋め込みトークンの ID で与えられます。 役割が与えられない場合、与えられたユーザー名を利用し、関連する役割が解決されます。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
* Power BI サービス内でのロールへのユーザーの割り当ては、埋め込みトークンを使ったときの RLS には反映されません。
* Power BI サービスでは RLS の設定は管理者および編集アクセス許可を持つメンバーには適用されませんが、埋め込みトークンで ID を指定すると、データに適用されます。
* GenerateToken を呼び出すときに ID 情報を渡すことができるのは、レポートの読み取り/書き込みの場合だけです。 他のリソースのサポートは将来的に追加されます。
* オンプレミス サーバー向けの Analysis Services ライブ接続がサポートされています。
* Azure Analysis Services のライブ接続はサポートされていません。
* 基になるデータセットで RLS が必要ない場合、GenerateToken 要求に有効な ID が含まれていては**なりません**。
* 基になるデータセットがクラウド モデル (キャッシュされたモデルまたは DirectQuery) の場合は、有効な ID に少なくとも 1 つのロールが含まれている必要があります。 含まれていない場合、ロールの割り当ては行われません。
* ID の一覧で指定できる ID は 1 つだけです。 将来的にはダッシュボードの埋め込みに対して複数 ID のトークンが有効になるため、今から一覧を使っています。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

