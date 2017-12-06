---
title: "プライバシー設定を無効にする"
description: "プライバシー設定を更新するためにそれを無効にするための Personal Gateway 内での高速結合の有効化の方法について説明します。"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: a622c3f0402e0f8216f64a93cf687eaa63fd8067
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2017
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Power BI Gateway - Personal でプライバシー設定を無効にする
> [!NOTE]
> Power BI には、**オンプレミス データ ゲートウェイ (個人用モード)** と呼ばれる、新しいバージョンの Personal Gateway があります。 この記事では、**Power BI Gateway - Personal** と呼ばれる以前のバージョンのパーソナル ゲートウェイについて説明します。このゲートウェイは、2017 年 7 月 31 日に廃止され、以降動作しなくなります。 新しいバージョンのインストール方法など、新しいパーソナル ゲートウェイの詳細については、「[**オンプレミス データ ゲートウェイ (個人用モード)**](service-gateway-personal-mode.md)」を参照してください。 新しいバージョンのパーソナル ゲートウェイでは高速結合を使用することもできます。この記事では、この高速結合についても説明しています。
> 
> 

データ ソースのプライバシー設定によっては、Personal Gateway で使用時に次のエラーが表示される場合があります。

> "*データセット内のデータの処理中にエラーが発生しました。*"
> 
> "*[データを結合できません] &lt;query part&gt;/&lt;…&gt;/&lt;…&gt; が、同時に使用できないプライバシー レベルの複数のデータ ソースにアクセスしています。このデータの組み合わせを再構築してください。*
> 
> 

このエラーを解決するには、 **高速結合**を有効にします。 **高速結合** では、異なるデータ ソースを組み合わせるプライバシー設定を無視します。

> [!NOTE]
> プライバシー レベルは、データの結合時に考慮されません。 これには、データの結合時に、別のデータ ソースに機密データを公開してしまう可能性があります。
> 
> 

## <a name="what-is-fast-combine"></a>高速結合とは
プライバシー レベルと高速結合について詳しくは、「[プライバシー レベル](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)」をご覧ください。 既定では、プライバシー レベルは、上記で説明したエラーが発生する可能性のあるプライベートに設定されます。 これは、プライベートの設定がデータ ソースを別のソースと分離するためです。 これが問題となる例は、別のデータ ソースからの入力を取得するパラメーター化されたクエリ値になります。

高速結合を有効にした場合、プライベート設定は無視され、実行が発生します。

## <a name="turn-on-fast-combine"></a>高速結合を有効にする
次の手順を使用すると、Personal Gateway で高速結合に有効にできます。 この設定はオンプレミス データ ゲートウェイにはありません。

1. **ConnectorConfig.xml**を開きます。  これは、コンピューターの次の 2 つのいずれかの場所にあります。  コンピューターの管理者の場合、場所は次になります。
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    管理者でない場合、場所は次になります。
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
2. 構成ファイルに、true の値の **&lt;EnableFastCombine&gt;** 要素を追加します。 この要素を追加すると、 **高速結合** が有効になります。
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. ゲートウェイの構成画面を修了して、再起動します。
4. 高速結合が有効であるという状態が示されます。
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>高速結合を無効にする
1. **ConnectorConfig.xml**を開きます。  これは、コンピューターの次の 2 つのいずれかの場所にあります。  コンピューターの管理者の場合、場所は次になります。
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    管理者でない場合、場所は次になります。
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
2. 構成ファイルから **&lt;EnableFastCombine&gt;** 要素を削除します。 この要素を削除すると、 **高速結合** が無効になります。
3. ゲートウェイの構成画面を修了して、再起動します。
4. **高速結合** が有効であるという状態は示されなくなります。

## <a name="next-steps"></a>次の手順
[オンプレミス データ ゲートウェイ (個人用モード) - 新しいバージョンのパーソナル ゲートウェイ](service-gateway-personal-mode.md)
[プライバシーのレベル](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Power BI Desktop での一般的なクエリ タスク](desktop-common-query-tasks.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

