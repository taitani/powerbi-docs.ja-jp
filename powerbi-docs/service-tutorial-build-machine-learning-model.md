---
title: チュートリアル:Power BI (プレビュー) での Machine Learning モデルを構築します。
description: このチュートリアルでは、Power BI での Machine Learning モデルを作成します。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61407202"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>チュートリアル:Power BI (プレビュー) での Machine Learning モデルを構築します。

使用するチュートリアルでは、 **Machine Learning の自動**を作成し、Power BI で二項予測モデルを適用します。 チュートリアルには、Power BI のデータ フローを作成するためのガイダンスが含まれます、エンティティを使用してトレーニングし、machine learning の Power BI で直接モデルを検証するデータ フローで定義されています。 使用してそのモデルのスコア付けの予測を生成します。

最初に、二項予測 machine learning のためのオンライン セッション属性のセットに基づいて、オンライン顧客の購入目的の予測モデルを作成します。 この演習では、ベンチマークの machine learning データセットが使用されます。 モデルをトレーニングすると、Power BI はモデルの結果を説明する検証レポートを自動的に生成されます。 検証レポートを確認し、データをスコア付けのためにモデルを適用します。

このチュートリアルは、次の手順から成ります。

> [!div class="checklist"]
> * 入力データで、データ フローを作成します。
> * 作成し、機械学習モデルのトレーニング
> * モデルの検証レポートを確認してください。
> * モデルをデータ フローのエンティティに適用します。
> * Power BI レポートでモデルのスコア付けされた出力の使用

## <a name="create-a-dataflow-with-the-input-data"></a>入力データで、データ フローを作成します。

このチュートリアルの最初の部分では、入力データで、データ フローを作成します。 そのプロセスは、以降のデータの取得では、次のセクションで示すように、いくつかの手順をかかります。

### <a name="get-data"></a>データを取得

データ フローを作成する最初の手順では、準備、データ ソースがあります。 ここでは、購入レディネスうちいくつかのオンライン セッションのセットから machine learning データセットを使用します。 データセットには、これらのセッションでは、使用して、モデルのトレーニングに関する属性のセットが含まれています。

データセットは、UC Irvine web サイトからダウンロードできます。  また、このチュートリアルでは、次のリンクから、この使用がある: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv)します。

### <a name="create-the-entities"></a>エンティティを作成します。

データフローにエンティティを作成するには、Power BI サービスにサインインし、AI プレビューが有効になっている専用容量内のワークスペースに移動します。

ワークスペースがまだしていない場合、1 つを選択して、作成できます**ワークスペース**クリックし、Power BI サービスで、左側のナビゲーション メニューで**アプリ ワークスペースを作成**パネルの下部にします。表示されます。 ワークスペースの詳細を入力する右側のパネルが開きます。 ワークスペース名を入力し、選択**詳細**します。 ワークスペースで、ラジオ ボタンを使用して専用の容量を使用して、オンになって AI プレビューのある専用の容量のインスタンスに代入されることを確認します。 その後、 **[保存]** を選びます。

![ワークスペースを作成する](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

選択することができます、ワークスペースが作成されると、**スキップ**次の図のように、ようこそ画面の右下にします。

![ワークスペースがある場合はスキップします。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

選択、 **(プレビュー) のデータフロー**タブ。選択、**作成**ワークスペースの右方向と選択し、上部にある**データフロー**します。

![データ フローを作成します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

**[新しいエンティティを追加]** を選択します。 これにより、起動、 **Power Query**ブラウザーでのエディター。

![新しいエンティティを追加](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

選択**TEXT/CSV ファイル**をデータ ソースとしては、次の図に示すようにします。

![選択したテキスト/CSF ファイル](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

**データ ソースへの接続**[次へ] が表示されますが、次のリンクを貼り付けます、 *online_shoppers_intention.csv*に、**ファイル パスまたは URL**ボックス、およびを選択します。 **[次へ]** します。

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![ファイルのパス](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power Query のエディターでは、CSV ファイルからのデータのプレビューを示します。 選択**変換テーブル**クリックしてコマンドのリボンで**最初の行を見出しとして使用**表示されるメニューから。 これを追加、_ヘッダーを昇格_クエリにステップ イン、**適用される手順**画面の右側のセクション。 値を変更するわかりやすい名前に、クエリを変更すること、**名前**ボックス右側のウィンドウにあります。 クエリ名を変更するなど、_オンライン ビジター_します。

![表示名を変更します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

このデータセット内の属性のデータ型のいくつか_数値_または_ブール_これらを文字列として解釈されますが、 **Power Query**します。 次の種類を以下に示す列を変更するには、各列ヘッダーの上部にある属性の種類のアイコンを選択します。

* **10 進数:** Administrative_Duration;Informational_Duration;ProductRelated_Duration;BounceRates;ExitRates;PageValues;SpecialDay
* **True または False。** 週末;収益

![データ型を変更する](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

**二項予測**モデルをトレーニングするには、過去の観測値から結果を識別するラベルとしてブール型フィールドが必要です。 このデータセットで、_収益_属性、購入を示し、この属性はブール値として使用可能な既にします。 そのため、ラベルの計算列を追加する必要はありません。 その他のデータセットはブール型の列に既存のラベルの属性を変換する必要があります。

選択、**完了**Power Query エディターを閉じるボタンをクリックします。 エンティティの一覧が表示されます、_オンライン訪問者_データを追加しました。 選択**保存**右上隅にある、データ フローの名前を指定し、 **[保存]** ダイアログで次の図のようにします。

![データ フローを保存します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>データフローを更新する

通知が表示されているデータ フローの結果、保存、データ フローが保存されていることを示します。 選択**今すぐ更新**データ フローに、ソースからデータを取り込みます。

![今すぐ更新](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

右上隅にある **[閉じる]** を選択し、データフローの更新が完了するまで待ちます。

使用して、データ フローを更新することも、**アクション**コマンド。 データ フローは、更新が完了したときのタイムスタンプを示しています。

![更新のタイムスタンプ](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>作成し、機械学習モデルのトレーニング

更新が完了した後は、データ フローを選択します。 機械学習モデルを追加するには、選択、**適用の ML モデル**ボタン、**アクション**、トレーニング データとラベル情報を含む基本エンティティを一覧表示し、**追加、機械学習モデル**します。

![機械学習モデルの追加](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

機械学習モデルを作成するための最初の手順では、予測するラベル フィールドを含む履歴データを特定します。 このデータから学習することにより、モデルが作成されます。

これは、データセットを使用している場合、**収益**フィールド。 選択**収益**として選択し、'履歴の結果フィールド' 値**次**します。

![履歴データを選択します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

次に、機械学習を作成するモデルの種類を選択します。 Power BI では、識別した履歴の結果フィールドの値を分析し、そのフィールドを予測するために作成できる機械学習モデルの型を予測します。

この場合、かどうかをユーザーと、購入かどうかのバイナリの結果を予測しましたしているために選択**二項予測**モデルの種類、および次の順に選択します。

![選択したバイナリの予測](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

次に、Power BI は、データの準備のスキャンを実行し、モデルが使用できる入力を提案します。 モデルに使用される入力フィールドをカスタマイズするオプションがあります。 精選されたデータセット内のすべてのフィールドを選択するエンティティ名の横にあるチェック ボックスを選択します。 選択**次**入力を受け入れるようにします。

![[次へ] のチェック ボックスを選択します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

最後の手順で、私たちのモデルの名前およびモデルの検証の結果の要約が自動的に生成されたレポートで使用される結果のわかりやすいラベルを提供する必要があります。 モデルに名前を次にある_購入目的とした予測_と同様に true と false ラベル_購入_と_いいえ購入_します。 その後、 **[保存]** を選びます。

![モデルを保存します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

マイクロソフトの機械学習モデルは、トレーニングの準備ができました。 選択**今すぐ更新**をモデルのトレーニングを開始します。

![今すぐ更新](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

サンプリング、履歴データの正規化とデータセットを 2 つの新しいエンティティに分割して、トレーニング プロセスが開始されます*購入目的とした予測のトレーニング データ*と*購入目的とした予測のテストデータ*します。

に応じて、データセットのサイズ、トレーニング プロセス任意の場所数分からにかかる 2 ~ 3 時間です。 この時点でのモデルを表示、**機械学習モデル**のデータ フロー タブ。 _準備_状態は、モデルがトレーニングのキューにまたはトレーニングのことを示します。

![トレーニングのための準備完了](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

モデルはトレーニングが、表示またはデータ フローを編集することはできません。 モデルがされていることを確認するトレーニングされ、データ フローの状態を検証します。 これで進行中のデータの更新として表示されます、**データフロー**ワークスペースのタブ。

![プロセスで](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

モデルのトレーニングが完了すると、データ フローには、更新された更新時刻が表示されます。 移動して、モデルをトレーニングすることを確認することができます、**機械学習モデル**データ フロー タブ。 作成したモデルとして状態を表示する必要があります**を養成**と**最後トレーニング済み**時刻が更新されます。

![最後のトレーニング](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>モデルの検証レポートを確認してください。

モデルの検証レポートを確認する、**機械学習モデル、s**選択、**パフォーマンス レポートを表示し、モデルを適用**ボタン、**アクション**モデルの列. このレポートでは、機械学習モデルが実行する方法について説明します。

**モデル パフォーマンス**選択、レポートのページ**主要な影響元**モデルの最上位の予測子を表示します。 結果の分布がどのようにその予測に関連付けられているを表示する予測子のいずれかを選択できます。

![モデルのパフォーマンス](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

使用することができます、**確率しきい値**スライサー モデルのパフォーマンス ページで、モデルの精度と再現率には、その影響を確認します。

![確率しきい値](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

レポートの他のページには、モデルの統計のパフォーマンス メトリックについて説明します。

レポートには、機能が入力値、および使用される最終的なモデルのハイパーパラ メーターから抽出された方法、実行されたさまざまなイテレーションを説明するトレーニングの詳細ページも含まれています。

## <a name="apply-the-model-to-a-dataflow-entity"></a>モデルをデータ フローのエンティティに適用します。

選択、**適用モデル**をデータ フローが更新されたときに、このモデルを呼び出すレポートの上部にあるボタンをクリックします。 **適用**ダイアログ ボックスで、モデルの適用先となるソース データのあるターゲット エンティティを指定することができます。

![モデルを適用します](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

必要な入力を求められたら**更新**モデルの結果をプレビューするためにデータフローです。

サフィックスを持つ新しいエンティティを作成、モデルを適用することは**拡充 < model_name >** モデルを適用するエンティティに追加されます。 ここでは、モデルを適用する、 **OnlineShoppers**エンティティが作成されます**OnlineShoppers 購入目的とした予測の拡充**、モデルから予測の出力が含まれています。

予測結果、確率スコアでは、最上位のレコードに固有な影響元の予測と 3 つの列を追加する二項予測モデルを適用する、指定された列名のプレフィックスそれぞれします。

![結果の 3 つの列](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

既知の問題により、強化されたエンティティでスコア付けされた出力列では Power BI Desktop からアクセスできるのみです。 これらのサービスをプレビューするには、特別なプレビュー エンティティを使用する必要があります。

データ フローの更新が完了するを選択できます、 **OnlineShoppers 購入目的とした予測のプレビューの拡充**結果を表示するエンティティ。

![結果を表示します。](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Power BI レポートでモデルのスコア付けされた出力の使用

機械学習モデルのスコア付けされた出力を使用するには、ことができますから接続する、データ フローに、Power BI desktop では、データフロー コネクタを使用します。 **OnlineShoppers 購入目的とした予測の拡充**エンティティを Power BI レポートでのモデルから予測を組み込む使用できます。

## <a name="next-steps"></a>次の手順

このチュートリアルで作成され、次の手順を使用して Power BI で二項予測モデルを適用しました。

* 入力データで、データ フローを作成します。
* 作成し、機械学習モデルのトレーニング
* モデルの検証レポートを確認してください。
* モデルをデータ フローのエンティティに適用します。
* Power BI レポートでモデルのスコア付けされた出力の使用

Power BI での Machine Learning 自動化の詳細については、次を参照してください。 [Power BI (プレビュー) での Machine Learning の自動](service-machine-learning-automated.md)します。
