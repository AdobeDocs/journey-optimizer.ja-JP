---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツ実験の作成
description: キャンペーンでのコンテンツ実験の作成方法について説明します。
feature: A/B Testing
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: bd35ae19-8713-4571-80bc-5f40e642d121
source-git-commit: ef838945e0c3595de8ad920203b278bb51671d16
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 0%

---

# コンテンツ実験の作成 {#content-experiment}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment"
>title="コンテンツの実験"
>abstract="配信の内容、件名、またはセンダーを変更することにより、複数の配信の治療を定義して、ユーザーに最適な組み合わせを決定することができます。"

>[!AVAILABILITY]
>
>コンテンツ実験 **機能は、** 現在のところ、組織のセットに対してのみ使用することができます (利用可能な機能が限られています)。詳しくは、アドビの担当者にお問い合わせください。

旅のオプティマイザーコンテンツを使用して、複数の配信処理を定義します。 関心のある対象者は、各処理に無作為に割り当てられ、どの測定基準によって最適に実行されるかを判断できます。 配信の内容、件名、または送信者を変更することもできます。

>[!NOTE]
>
>コンテンツの実験を開始する前に、カスタムデータセットのレポート設定が設定されていることを確認してください。 詳しくは、ここを [ ](reporting-configuration.md) 参照してください。

次の例では、配信先が2つのグループに分割され、それぞれが対象となる人口の45% を表し、10% の予約グループが表示されています。

対象となる視聴ユーザーは、1つのバージョンの電子メールを受信し、件名行には次のいずれかのメッセージが表示されます。

* 1つは、新しいコレクションとイメージについて、10% の提供を直接促進することです。
* 他の1つはイメージなしで10% のオフを指定せずに、特別なオファーを提供します。

ここでの目的は、受信者が受信した実験に応じて電子メールとやり取りすることを確認することです。 したがって、このコンテンツ実験において、1つの目的として選択 **[!UICONTROL Email Opens]** することになります。

![](assets/content_experiment.png)

## キャンペーンの作成 {#campaign-experiment}

1. **[!UICONTROL Campaigns]**&#x200B;ページでをクリック **[!UICONTROL Create campaign]** します。

   ![](assets/content_experiment_1.png)

1. この配信に使用するチャンネル **[!UICONTROL Surface]** を選択します。 詳細については、チャンネルの [ 「サーフェス ](../configuration/channel-surfaces.md) 」ページを参照してください。

   ![](assets/content_experiment_2.png)

1. をクリック **[!UICONTROL Create]** します。

1. **[!UICONTROL Properties]**&#x200B;配信の設定:
   * **[!UICONTROL Title]**
   * **[!UICONTROL Description]**
   * **[!UICONTROL Category]**: **[!UICONTROL Marketing]** / **[!UICONTROL Transactional]**

1. コンテンツの実験を開始するには **[!UICONTROL Content experiment]** 、このオプションをオンにします。 **[!UICONTROL Content experiment]**&#x200B;メニューが表示されます。

   ![](assets/content_experiment_3.png)

1. 対象ユーザーを定義します。 これを行うには、このボタンをクリックし **[!UICONTROL Select audience]** て、使用可能な Adobe エクスペリエンスプラットフォームセグメントのリストを表示します。 [セグメントに関する詳細情報](../segment/about-segments.md)

   **[!UICONTROL Identity namespace]**「」フィールドで、選択した区分の個人を識別するために使用する名前空間を選択します。[詳細情報](get-started-experiment.md#content-experiment-work)

1. 特定の日付または定期的な頻度でキャンペーンを実行するには、「スケジュール」セクションを設定します。 [詳細情報](create-campaign.md)

1. クリックし **[!UICONTROL Edit content]** て、違う **[!UICONTROL Treatments]** 内容をお客様によってカスタマイズします。

   ![](assets/content_experiment_4.png)

## 処置の作成 {#treatment-experiment}

1. **[!UICONTROL Edit content]**&#x200B;ウィンドウで、治療をカスタマイズします。

   この処理については、題名行に直接特別なオファーリングを指定します。

   ![](assets/content_experiment_5.png)

1. 最初の処理をデザインした後、 **[!UICONTROL More actions]** ボタンをクリック **[!UICONTROL Duplicate]** します。

   また、新しい処理を開始する場合は、ボタン ![](assets/content_experiment_16.png) をクリック **[!UICONTROL Content experiment]** して詳細オプション **[!UICONTROL Add treatment]** にアクセスすることもできます。

   ![](assets/content_experiment_7.png)

1. **[!UICONTROL Title]**&#x200B;適切な扱いになるように変更します。

   ![](assets/content_experiment_8.png)

1. 必要に応じて、2番目の処置を行います。

   ここでは、 **[!UICONTROL Subject line]** でオファーを指定しないことを選択します。

   ![](assets/content_experiment_9.png)

処置がパーソナライズされると、コンテンツ実験の設定を開始できます。

## コンテンツ実験の設定 {#configure-experiment}

1. 両方の配信が個人用に選択されて **[!UICONTROL Edit content]** いる場合は、ウィンドウからを選択 **[!UICONTROL Configure content experiment]** します。

   ![](assets/content_experiment_10.png)

1. 実験に設定する目標を選択します。

   ここでは、プロモーションコードが題名行にある場合に、受信者が電子メールを開くかどうかを選択し **[!UICONTROL Email open]** ます。

   ![](assets/content_experiment_11.png)

1. 配信にグループを追加 **[!UICONTROL Holdout]** するかどうかを選択します。 このグループには、このキャンペーンの内容は反映されません。

   切り替えバーで切り替えた場合は、自動的に最大10% の人口が表示されますが、必要に応じてこの比率を調整することもできます。

   ![](assets/content_experiment_12.png)

1. 次に、各 **[!UICONTROL Treatment]** 機能に対して、または切り替え先に切り替えて、切り替えバーに対して **[!UICONTROL Distribute evenly]** 正確な割合を割り当てることができます。

   ![](assets/content_experiment_13.png)

1. 設定が設定されているときにをクリックし **[!UICONTROL Save]** ます。

1. コンテンツ実験の準備ができたら、クリックし **[!UICONTROL Review to activate]** てキャンペーンの概要を表示することができます。 いずれかのパラメーターが間違っているか、存在しない場合は、警告が表示されます。

   ![](assets/content_experiment_15.png)

1. キャンペーンが正しく設定されていることを確認し、をクリック **[!UICONTROL Activate]** して、再起動します。

   ![](assets/content_experiment_14.png)

実験とキャンペーンの設定が完了したら、キャンペーンレポートを使用して配信を成功させることができます。

## 目標レポート {#objectives-global}

>[!AVAILABILITY]
>
>コンテンツ実験機能は、現在のところ、組織のセットに対してのみ使用することができます (利用可能な機能が限られています)。 詳しくは、アドビの担当者にお問い合わせください。

![](assets/performance_report.gif)

キャンペーンレポートのタブを使用すると、 **[!UICONTROL Objectives]** 1 つの特定の測定基準を指定することによって、配信のレポートをより詳細に調整できます。

リストには、 **[!UICONTROL Objectives]** 追加情報を取得するためにシステムへの接続を定義するに **[!UICONTROL Datasets]** リンクされています。 組み込み **[!UICONTROL Objectives]** のリストを使用できますが、新規 **[!UICONTROL Dataset]** に追加することで、独自のリストを追加することもできます。 詳細な手順については、次 [ の項 ](reporting-configuration.md) を参照してください。

目標を選択した後は、2つ **[!UICONTROL Performance overview]** の widget と **[!UICONTROL Campaign objective]** widget を使用して、配送のパフォーマンスについて詳しく説明します。

**[!UICONTROL Campaign objective]**&#x200B;この widget を使用して、主な目的を別の測定単位と比較することもできます。

各 widget については、必要に応じて、サイズ変更および削除することができます。 詳細については、ここを [ ](../reports/global-report.md#modify-dashboard) 参照してください。

## 実験レポート {#experimentation-global}

>[!AVAILABILITY]
>
>コンテンツ実験機能は、現在のところ、組織のセットに対してのみ使用することができます (利用可能な機能が限られています)。 詳しくは、アドビの担当者にお問い合わせください。

![](assets/experimentation_report_3.png)

キャンペーン **[!UICONTROL Global report]** から、このタブに **[!UICONTROL Experimentation]** は、各バリエーションの状況と、最良の実行者があるかどうかを示す重要な情報が表示されます。

最適な実行可能ファイルを定義するには時間がかかることがあります。これは、このアイコン ![](assets/experimentation_report_1.png) で示されます。

Widget は **[!UICONTROL Experiment result]** 、各バリアントのパフォーマンスを詳細に設定します。 ドロップダウンリストから **[!UICONTROL Baseline]** いずれかの操作を選択して、ベースラインを変更することができます。 最適な処理が星のアイコンで表示されます。

テーブルには、次のようにメトリックが表示されます。

* **[!UICONTROL Profiles]**: この処理の対象となるプロファイルの数。

* **[!UICONTROL Unique outbound clicks]**: アウントバウンドチャンネル全体のクリックの合計数。

* **[!UICONTROL Count per profile]**: 実験目的の数値の合計値を、複数のプロファイルの数で割ります。

* **[!UICONTROL Confidence interval]**: 基準として最適な処理を行うことができます。 [詳しく ](../campaigns/experiment-calculations.md#confidence-intervals) は、こちらを参照してください。

* **[!UICONTROL Average lift]**: ベースラインでの指定された処理の変換レートの改善率。 [詳細情報](../campaigns/experiment-calculations.md#understand-lift)

* **[!UICONTROL Confidence]**: 指定された処置がベースラインの処理と同じであることを示しています。 [詳細情報](../campaigns/experiment-calculations.md#understand-confidence)

このような結果について詳しくは、このページ ](../campaigns/get-started-experiment.md#interpret-results) を [ 参照してください。
