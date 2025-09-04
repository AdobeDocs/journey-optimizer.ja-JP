---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのアクティビティの基本を学ぶ
description: ジャーニーのアクティビティの基本を学ぶ
feature: Journeys, Activities, Overview
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: ジャーニー, アクティビティ, 開始, イベント, アクション
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 94%

---

# ジャーニーのアクティビティの基本を学ぶ {#about-journey-activities}

様々なイベント、オーケストレーション、アクションなどのアクティビティを組み合わせて、複数のステップから成るクロスチャネルのシナリオを構築します。

## イベントアクティビティ {#event-activities}

パーソナライズされたジャーニーは、オンライン購入などのイベントによってトリガーされます。プロファイルがジャーニーにエントリすると、それらのプロファイルは個人として移動します。異なる個人が同じ速度や同じパスを進むことはありません。イベントでジャーニーを開始する場合は、イベントを受信したときにジャーニーがトリガーされます。ジャーニーの各ユーザーは、ジャーニーで定義された次のステップを個別にたどります。

技術ユーザーが設定したイベント（[このページ](../event/about-events.md)を参照）はすべて、画面左側のパレットの最初のカテゴリに表示されます。次のイベントアクティビティを使用できます。

* [一般イベント](../building-journeys/general-events.md)
* [反応](../building-journeys/reaction-events.md)
* [オーディエンスの選定](../building-journeys/audience-qualification-events.md)

![ジャーニー designer のイベントアクティビティパレット](assets/journey43.png)

ジャーニーを開始するには、イベントアクティビティをドラッグ＆ドロップします。ダブルクリックでも開始できます。

![ジャーニー designer のイベントアクティビティのドラッグ＆ドロップ](assets/journey44.png)

## オーケストレーションアクティビティ {#orchestration-activities}

オーケストレーションアクティビティは、ジャーニーの次のステップを決定するのに役立つ様々な条件です。これらの条件には、未完了のサポートケースがあるかどうか、現在地の天気予報、購入を完了したかどうか、10,000 ロイヤルティポイントに到達したかどうかなどが含まれます。

画面左側にあるパレットで、次のオーケストレーションアクティビティを使用できます。

<!--* [Optimize](optimize.md)-->
* [オーディエンスを読み取り](read-audience.md)
* [待機](wait-activity.md)
* [コンテンツの決定](content-decision.md)

![ジャーニー designer のオーケストレーションアクティビティパレット](assets/journey-orchestration-activities.png)

## アクションアクティビティ {#action-activities}

アクションは、メッセージの送信など、何らかのトリガーの結果として発生させるもので、顧客が体験するジャーニーの一部です。

画面左側にあるパレットの「**[!UICONTROL イベント]**」と「**[!UICONTROL オーケストレーション]**」の下には、**[!UICONTROL アクション]**&#x200B;カテゴリがあります。次のアクションアクティビティを使用できます。

* [ビルトインのチャネルアクション](../building-journeys/journeys-message.md)
* [カスタムアクション](../building-journeys/using-custom-actions.md)
* [ジャンプ](../building-journeys/jump.md)

![ジャーニー designer のアクションアクティビティパレット](assets/journey58.png)

これらのアクティビティは、様々な通信チャネルを表します。これらを組み合わせて、クロスチャネルシナリオを作成できます。

また、メッセージを送信する特定のアクションを設定することもできます。

* サードパーティシステムを使用してメッセージを送信する場合は、特定のカスタムアクションを作成できます。[詳細情報](../action/action.md)

* Campaign と Journey Optimizer の連携について詳しくは、次の節を参照してください。

   * [[!DNL Journey Optimizer] と Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] と Campaign Standard](../action/acs-action.md)
   * [[!DNL Journey Optimizer] と Marketo Engage](../action/marketo-engage.md)

## ベストプラクティス {#best-practices}

### ラベルの追加

ほとんどのアクティビティでは、**[!UICONTROL ラベル]**&#x200B;を定義できます。これにより、キャンバスのアクティビティの下に表示される名前にサフィックスが追加されます。これは、ジャーニーで同じアクティビティを複数回使用し、より簡単に識別したい場合に便利です。また、エラーが発生した場合のデバッグも容易になり、レポートも読みやすくなります。また、オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を追加することもできます。

![ジャーニーアクティビティプロパティの「ラベル」および「説明」フィールド](assets/journey-action-label.png)

>[!NOTE]
>
>一部のアクティビティでは、その ID もパネルに表示されます。この ID は、変更される可能性があるラベルよりも安定したキーとしてレポートに使用できます。

### 詳細パラメーターの管理 {#advanced-parameters}

ほとんどのアクティビティには、変更できない多数の詳細なパラメーターや技術的なパラメーターが表示されます。

![ジャーニーアクティビティプロパティの詳細パラメーターフィールド](assets/journey-advanced-parameters.png)

読みやすくするために、右側のパネルの上部にある **[!UICONTROL 読み取り専用フィールドを非表示にする]** ボタンを使用して、これらのパラメーターを非表示にします。

![ジャーニーアクティビティプロパティの読み取り専用フィールドを非表示アイコン](assets/journey-hide-read-only-fields.png)

一部のコンテキストでは、特定の用途でこれらのパラメーターの値を上書きできます。値を強制的に指定するには、フィールドの右側にある「**[!UICONTROL パラメーターの上書きを有効にする]**」アイコンをクリックします。[詳細情報](../configuration/primary-email-addresses.md#journey-parameters)

![メールアクティビティプロパティの「パラメーターの上書きを有効にする」オプション](assets/journey-enable-parameter-override.png)

>[!NOTE]
>
>詳細設定パラメーターが非表示の場合は、「**[!UICONTROL 読み取り専用フィールドを表示]**」ボタンをクリックします
>
>![ ジャーニーアクティビティプロパティの「読み取り専用フィールドを表示」アイコン ](assets/journey-show-read-only-fields.png){width=60%}

### 代替パスの追加

アクションまたは条件でエラーが発生すると、個人のジャーニーは停止します。続行するには、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスをオンにするだけです。[この節](../building-journeys/using-the-journey-designer.md#paths)を参照してください。

![条件アクティビティプロパティの「代替パスを追加」オプション](assets/journey42.png)

## トラブルシューティング {#troubleshooting}

ジャーニーをテストおよび公開する前に、すべてのアクティビティが正しく設定されていることを確認します。システムでエラーが検出される場合は、テストまたは公開を実行できません。

アクティビティとジャーニーでのエラーのトラブルシューティング方法について詳しくは、[このページ](troubleshooting.md)を参照してください。
