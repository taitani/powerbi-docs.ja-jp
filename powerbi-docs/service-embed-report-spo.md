---
title: "SharePoint Online にレポート Web パーツを埋め込む"
description: "Power BI の新しい SharePoint Online 用レポート Web パーツでは、対話型の Power BI レポートを SharePoint Online のページに簡単に埋め込むことができます。"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/01/2017
ms.author: asaxton
ms.openlocfilehash: bb3ab7c8f9791aa535e86b8c9b21361c95e4389b
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>SharePoint Online にレポート Web パーツを埋め込む
Power BI の新しい SharePoint Online 用レポート Web パーツでは、対話型の Power BI レポートを SharePoint Online のページに簡単に埋め込むことができます。

新しい **[SharePoint Online に埋め込む]** オプションを使うと、埋め込まれたレポートは完全に安全なので、簡単にセキュリティで保護された内部ポータルを作成できます。

## <a name="requirements"></a>要件
**[SharePoint Online に埋め込む]** レポートが機能するためには、いくつかの要件があります。

* SharePoint Online の Power BI (プレビュー) Web パーツには、[最新式のページ](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)が必要です。

## <a name="embed-your-report"></a>レポートを埋め込む
SharePoint Online にレポートを埋め込むには、最初にレポートの URL を取得し、SharePoint Online 内の新しい Power BI (プレビュー) Web パーツでその URL を使う必要があります。

### <a name="get-a-url-to-your-report"></a>レポートの URL を取得する
1. Power BI サービスでレポートを表示します。
2. **[ファイル]** メニュー項目を選びます。
3. **[SharePoint Online に埋め込む (プレビュー)]** を選びます。
   
    ![](media/service-embed-report-spo/powerbi-file-menu.png)
4. ダイアログ ボックスから URL をコピーします。
   
    ![](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)
   
   > [!NOTE]
   > また、レポートを表示したときに Web ブラウザーのアドレス バーに表示される URL を使うこともできます。 その URL には、現在表示しているレポート ページが含まれます。 別のページを使いたい場合は、URL からレポート セクションを削除する必要があります。
   > 
   > 

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Power BI レポートを SharePoint Online のページに追加する
1. SharePoint Online で目的のページを開き、**[編集]** を選びます。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)
   
    または、SharePoint Online で **[+ 新規]** を選んで、最新式のサイト ページを新しく作成します。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)
2. **[+]** を選び、**[Power BI (プレビュー)]** Web パーツを選びます。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)
3. **[レポートの追加]** を選びます。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)
4. レポートの URL をプロパティ ウィンドウに貼り付けます。 これは、前の手順でコピーした URL です。 レポートが自動的に読み込まれます。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)
5. SharePoint Online のユーザーに変更が表示されるようにするには、**[発行]** を選びます。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>レポートへのアクセスを許可する
SharePoint Online にレポートを埋め込んだだけで、レポートを表示するアクセス許可が自動的にユーザーに与えられることはありません。 レポートを表示するアクセス許可は、Power BI サービスで設定します。

> [!IMPORTANT]
> Power BI サービスでレポートを表示できるユーザーを確認し、一覧に含まれないユーザーにアクセスを許可します。
> 
> 

Power BI サービスでレポートへのアクセスを許可するには 2 つの方法があります。 Office 365 グループを使用して SharePoint Online のチーム サイトを構築している場合は、Power BI サービス内でアプリ ワークスペースのメンバーとしてユーザーをリストします。 このようにすると、ユーザーはそのグループのコンテンツを表示できるようになります。 詳細については、「[Power BI でのアプリの作成および配布](service-create-distribute-apps.md)」を参照してください。

または、次のようにしてレポートへのアクセスをユーザーに許可することもできます。

1. レポートからダッシュボードにタイルを追加します。
2. レポートへのアクセスを必要とするユーザーとダッシュボードを共有します。 詳しくは、「[同僚や他のユーザーとダッシュボードやレポートを共有する](service-share-dashboards.md)」をご覧ください。
   
    セキュリティ グループでダッシュ ボードを共有する場合、ユーザーがレポートにアクセスできるように少なくとも 1 回 Power BI にサインインする必要があります。

## <a name="allowing-free-users-access-to-reports"></a>無料ユーザーにレポートへのアクセスを許可する
無料ユーザーは、SharePoint Online の Power BI Web パーツで埋め込まれているレポートを表示できます。 上の「[レポートへのアクセスを許可する](#granting-access-to-reports)」で説明されているように、Pro ユーザーの場合と同じ方法で無料ユーザーにアクセスを付与します。 レポートが保存されるワークスペースにも、Power BI Premium 容量が必要です。 

たとえば、アプリのワークスペースにレポートがある場合、アプリのワークスペースを Power BI Premium 容量に割り当てる必要があります。 無料ユーザーを、そのアプリのワークスペースのメンバー一覧に追加する必要もあります。

## <a name="web-part-settings"></a>Web パーツの設定
以下では、SharePoint Online 用の Power BI Web パーツに対して調整できる設定について説明します。

![](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| プロパティ | 説明 |
| --- | --- |
| ページ名 |Web パーツによって表示される既定のページを設定します。 ドロップダウンから値を選びます。 ドロップダウンにページが表示されない場合は、レポートが 1 ページであるか、または貼り付けた URL にページ名が含まれています。 特定のページを選ぶには、URL からレポート セクションを削除します。 |
| 表示 |レポートを SharePoint Online のページ内に適合させる方法を調整するオプションです。 |
| ナビゲーション ウィンドウの表示 |ページ ナビゲーション ウィンドウの表示と非表示を切り替えます。 |
| Show Filter Pane (フィルター ウィンドウの表示) |フィルター ウィンドウの表示と非表示を切り替えます。 |

## <a name="multi-factor-authentication"></a>多要素認証
Power BI 環境で多要素認証を使ったサインインが必要な場合は、ID 確認のためにセキュリティ デバイスでのサインインを求められることがあります。 これは、ユーザーが多要素認証を使わずに SharePoint Online にサインインしているのに、Power BI 環境がセキュリティ デバイスによって検証されたアカウントを要求する場合に発生します。

> [!NOTE]
> Azure Active Directory 2.0 では、多要素認証はまだサポートされていません。 ユーザーは、*エラー*を示すメッセージを受け取ります。 ユーザーがセキュリティ デバイスを使って SharePoint Online に再度サインインした場合、レポートを表示できることがあります。
> 
> 

## <a name="reports-that-do-not-load"></a>読み込まれないレポート
レポートが Power BI (プレビュー) Web パーツに読み込まれず、次のメッセージが表示されることがあります。

*このコンテンツは使用できません。*

![](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

このメッセージには 2 つの一般的な理由があります。

1. レポートへのアクセス許可がありません。
2. レポートが削除されました。

問題を解決するには、SharePoint Online のページの所有者に連絡する必要があります。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項
* SharePoint Online 用の Power BI (プレビュー) Web パーツは、スクリーン リーダーまたはキーボード ナビゲーションをサポートしていません。
* **エラー: "エラーが発生しました。ログアウトしてから再度ログインして、このページに再びアクセスしてください。関連付け ID: 未定義、http の応答の状態: 400、サーバー エラー コード 10001、メッセージ: 更新トークンが見つかりません"**
  
  このエラーが返された場合は、次のいずれかを試してください。
  
  1. SharePoint をサインアウトしてから再度サインインします。 再度サインインする前に、必ずすべてのブラウザー ウィンドウを閉じてください。
  2. ユーザー アカウントが Multi-Factor Authentication (MFA) を必要としている場合は、必ず Multi-Factor Authentication デバイス (電話アプリやスマート カードなど) を使用して SharePoint にサインインします。
* Power BI (プレビュー) Web パーツを追加する場合は、サインインを求められますが、それを行うことはできません。 このような状況では、次のいずれかに類似したエラー メッセージが表示されます。
  
  * *サインインし直す必要があります。それを行うと、ここに戻ることができます*
  * *エラーが発生しました。ログアウトしてから再度ログインして、このページに再びアクセスしてください。*
  
  この問題を解決するには、この記事の前半の「**要件**」セクションで説明したように、テナントが*すべてのユーザーを対象にした先行リリース*に設定されていることを確認してください。 シングル サインオン (SSO) を有効にするために、Power BI Web パーツは SharePoint によって指定された*認証 API* に依存します。これは、*すべてのユーザーを対象にした先行リリース*が選択されている場合にのみ利用できます。
* Power BI は、SharePoint Online と同じローカライズされた言語をサポートしていません。 そのため、埋め込みのレポートが適切にローカライズされていない可能性があります。
* この問題は Internet Explorer 10 を使用する場合に発生する可能性があります。 [Power BI](service-browser-support.md) および [Office 365](https://products.office.com/office-system-requirements#Browsers-section) でサポートされているブラウザーをご確認ください。

## <a name="next-steps"></a>次の手順
[Office 365 で標準または先行リリース オプションを設定する](https://support.office.com/article/Set-up-the-Standard-or-First-Release-options-in-Office-365-3B3ADFA4-1777-4FF0-B606-FB8732101F47)  
[エンドユーザーによる最新式のサイト ページの作成を許可または禁止する](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[Power BI でのアプリの作成および配布](service-create-distribute-apps.md)  
[同僚や他のユーザーとダッシュボードやレポートを共有する](service-share-dashboards.md)  
[Power BI Premium とは](service-premium.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

