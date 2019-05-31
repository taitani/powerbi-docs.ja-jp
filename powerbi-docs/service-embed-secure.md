---
title: セキュリティで保護されたポータルまたは Web サイトにレポートを埋め込む
description: Power BI では、機能することにより、ユーザーを簡単に埋め込むし、安全に内部の web ポータルでレポートを埋め込みます。
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
LocalizationGroup: Share your work
ms.openlocfilehash: bf9d7bcdf6ddaf7d0063843a5314233989b2dadd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222234"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>セキュリティで保護されたポータルまたは Web サイトにレポートを埋め込む

新しい**埋め込み**埋め込むことができます簡単かつ安全にレポートの内部の web ポータルで、Power BI 用のオプションを報告します。 これらのポータルは、**クラウド ベース**または**オンプレミスでホストされる**、SharePoint 2019 など。 埋め込みレポートすべての項目のアクセス許可とデータ セキュリティが考慮[行レベル セキュリティ (RLS)](service-admin-rls.md)します。 URL または iFrame を受け取る任意のポータルへのコードなしの埋め込みを提供します。 

**埋め込み**オプション サポート[URL フィルター](service-url-filters.md)と URL の設定。 基本的な HTML と JavaScript の知識のみを要求ローコード アプローチを使用するポータルと統合することができます。

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI レポートをポータルに **[埋め込む]** 方法

1. 新しい **[埋め込む]** オプションは、Power BI サービスのレポートの **[ファイル]** メニューで使用できます。

    ![安全な [埋め込む] オプションのドロップダウン オプション](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. 選択、**埋め込み**オプションを安全にレポートを埋め込む際 iFrame とリンクを提供するダイアログを開きます。

    ![[埋め込む] オプションのダイアログ ボックス](media/service-embed-secure/secure-embed-code-dialog.png)

3. ユーザーが直接、レポートの URL を開くまたは web ポータルに埋め込まれているいずれかであるかどうか、レポートへのアクセスには、認証が必要です。 ユーザーがいないにサインインした Power BI がブラウザー セッションで場合、次の画面が表示されます。 選択したときに**サインイン**、新しいブラウザー ウィンドウまたはタブを開くことでした。 サインインするように求め取得しない場合は、ポップアップ ブロックの確認があります。

    ![サインインしてこのレポートを表示する](media/service-embed-secure/secure-embed-sign-in.png)

4. ユーザーがサインインした後、レポートが開き、データを表示し、ページ ナビゲーションとフィルターの設定を許可すること。 ビューのアクセス許可を持つユーザーのみには、Power BI でレポートを表示できます。 すべて[行レベル セキュリティ (RLS)](service-admin-rls.md)もルールが適用されます。 最後に、ユーザーに正しいライセンスが与えられている必要があります – Power BI Pro ライセンスが必要であるか、またはレポートが Power BI Premium 容量内にあるワークスペースに置かれている必要があります。 ユーザーは、新しいブラウザー ウィンドウを開くたびにサインインする必要があります。 ただし、一度サインインすると、その他のレポートは自動的に読み込みます。

    ![レポートを埋め込む](media/service-embed-secure/secure-embed-report.png)

5. IFrame を使用する場合は、編集する必要があります、**高さ**と**幅**がポータルの web ページに収まるようにします。

    ![高さと幅を設定する](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>レポートへのアクセスを許可

**埋め込み**オプションはレポートを表示するユーザーに自動的にできません。 アクセス許可の表示は、Power BI サービスで設定されます。

Power BI サービスでは、アクセスを必要とするユーザーと埋め込みレポートを共有できます。 Office 365 グループを使用している場合は、アプリ ワークスペースのメンバーとしてユーザーを一覧表示できます。 詳細については、次を参照してください。 方法[Power BI および Office 365 でアプリ ワークスペースの管理](service-manage-app-workspace-in-power-bi-and-office-365.md)します。

## <a name="licensing"></a>ライセンス

埋め込みのレポートを表示するか、Power BI Pro ライセンス ユーザーする必要があります。 または、コンテンツをされているワークスペースである必要があります、 [Power BI Premium 容量 (EM または P SKU)](service-admin-premium-purchase.md)します。

## <a name="customize-your-embed-experience-using-url-settings"></a>URL 設定を使って埋め込みエクスペリエンスをカスタマイズする

埋め込み URL の入力設定を使用して、ユーザー エクスペリエンスをカスタマイズすることができます。 URL を更新する指定の iFrame で**src**設定します。

| プロパティ  | 説明  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | 使用することができます、 **pageName**クエリ文字列パラメーターを設定するレポート ページを開きます。 この値を調べる、レポートの URL の最後に、Power BI サービスでレポートを表示すると次に示すよう。 |  |  |  |
| URL フィルター  | 使用することができます[URL フィルター](service-url-filters.md)埋め込みコンテンツをフィルター処理する Power BI の UI から受信した埋め込み URL にします。 この方法では、基本的な HTML および JavaScript エクスペリエンスのみとのローコードの統合を構築できます。  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>セットの埋め込みレポートのページが表示されます。 

検索することができます、 **pageName** Power BI サービスでレポートを表示するときに、レポートの URL の末尾にある値。

1. Web ブラウザーで Power BI サービスからレポートを開き、アドレス バーの URL をコピーします。

    ![レポート セクション](media/service-embed-secure/secure-embed-report-section.png)

2. **pageName** 設定を URL に追加します。

    ![pageName を追加する](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>URL フィルターを使ってレポートの内容をフィルター処理する 

使用することができます[URL フィルター](service-url-filters.md)別のレポート ビューを提供します。 たとえば、以下の URL では、レポートをフィルター処理してエネルギー業界のデータを表示します。

**pageName** と [URL フィルター](service-url-filters.md)を組み合わせて使うと強力です。 基本的な HTML と JavaScript を使ってエクスペリエンスを構築できます。

たとえば、HTML ページに追加することができます ボタンを示します。

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

選択した場合、ボタンは、iFrame をエネルギー業界フィルターを含む、更新された URL で更新する関数を呼び出します。

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![フィルター](media/service-embed-secure/secure-embed-filter.png)

ボタンを好きなだけ追加して、ローコードのカスタム エクスペリエンスを作成できます。 

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

* Azure の企業間 (B2B) 機能を使った外部ゲスト ユーザーはサポートされません。

* セキュリティで保護された埋め込みは Power BI サービスに公開されたレポートに対して機能します。

* ユーザーは、新しいブラウザー ウィンドウを開くときに、レポートを表示するサインインする必要があります。

* 一部のブラウザーでは、InPrivate または Incognito のモードを使用する場合は特に、サインイン後、ページを更新する必要があります。

* シングル サインオン エクスペリエンスを実現する、SharePoint Online のオプションで埋め込みを使用してを使用してカスタム統合のビルドに、[ユーザー所有データ](developer/embed-sample-for-your-organization.md)メソッドの埋め込み。 

* **[埋め込む]** オプションを使って提供される自動認証機能は、Power BI JavaScript API では動作しません。 Power BI JavaScript API を使用して、[ユーザー所有データ](developer/embed-sample-for-your-organization.md)メソッドの埋め込み。 

## <a name="next-steps"></a>次の手順

* [Power BI で作業を共有する方法](service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL にクエリ文字列パラメーターを使用してレポートをフィルター処理します。](service-url-filters.md)

* [SharePoint Online にレポート web パーツを埋め込む](service-embed-report-spo.md)

* [Power BI から Web に公開します。](service-publish-to-web.md)