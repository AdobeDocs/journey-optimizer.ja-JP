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
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 63%

---

# ジャーニーのアクティビティの基本を学ぶ {#about-journey-activities}

様々なイベント、オーケストレーション、アクションなどのアクティビティを組み合わせて、複数のステップから成るクロスチャネルのシナリオを構築します。

## イベントアクティビティ {#event-activities}

パーソナライズされたジャーニーは、オンライン購入などのイベントによってトリガーされます。プロファイルがジャーニーにエントリすると、個人として移動します。異なる個人が同じ速度や同じパスを進むことはありません。 イベントでジャーニーを開始した場合、ジャーニーはイベントを受信するとトリガーになります。 ジャーニーの各ユーザーは、ジャーニーで定義された次のステップを個別にたどります。

技術ユーザーが設定したイベント（[このページ](../event/about-events.md)を参照）はすべて、画面左側のパレットの最初のカテゴリに表示されます。次のイベントアクティビティを使用できます。

* [一般イベント](../building-journeys/general-events.md)
* [反応](../building-journeys/reaction-events.md)
* [オーディエンスの選定](../building-journeys/audience-qualification-events.md)

![ ジャーニーデザイナーのイベントアクティビティパレット ](assets/journey43.png)

ジャーニーを開始するには、イベントアクティビティをドラッグ&amp;ドロップします。 ダブルクリックでも開始できます。

![ ジャーニーデザイナーでのイベントアクティビティのドラッグ&amp;ドロップ ](assets/journey44.png)

## オーケストレーションアクティビティ {#orchestration-activities}

オーケストレーションアクティビティは、ジャーニーの次のステップを決定するのに役立つ様々な条件です。これらの条件には、オープンなサポートケースの有無、現在地の天気予報、購入の完了、10,000 ロイヤルティポイントへの到達などが含まれます。

画面左側にあるパレットで、次のオーケストレーションアクティビティを使用できます。

* [条件](../building-journeys/condition-activity.md)
* [待機](../building-journeys/wait-activity.md)
* [オーディエンスを読み取り](../building-journeys/read-audience.md)

![ ジャーニーデザイナーのオーケストレーションアクティビティパレット ](assets/journey49.png)

## アクションアクティビティ {#action-activities}

アクションとは、メッセージの送信など、何らかのトリガーの結果として発生させるもので、 顧客が体験するジャーニーの一部です。

画面左側にあるパレットの「**[!UICONTROL イベント]**」と「**[!UICONTROL オーケストレーション]**」の下には、**[!UICONTROL アクション]**&#x200B;カテゴリがあります。次のアクションアクティビティを使用できます。

* [組み込みのチャネルアクション](../building-journeys/journeys-message.md)
* [カスタムアクション](../building-journeys/using-custom-actions.md)
* [ジャンプ](../building-journeys/jump.md)

![ ジャーニーデザイナーのアクションアクティビティパレット ](assets/journey58.png)

これらのアクティビティは、様々な通信チャネルを表します。これらを組み合わせて、クロスチャネルシナリオを作成できます。

<!--If you have configured custom actions, they also appear here. [Learn more](../building-journeys/using-custom-actions.md)-->

また、メッセージを送信する特定のアクションを設定することもできます。

* サードパーティのシステムを使用してメッセージを送信する場合は、特定のカスタムアクションを作成できます。 [詳細情報](../action/action.md)

* Campaign と Journey Optimizer の連携について詳しくは、次の節を参照してください。

   * [[!DNL Journey Optimizer] と Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] と Campaign Standard](../action/acs-action.md)
   * [[!DNL Journey Optimizer] とMarketo Engage](../action/marketo-engage.md)

## ベストプラクティス {#best-practices}

### ラベルの追加

ほとんどのアクティビティでは、**[!UICONTROL ラベル]**&#x200B;を定義できます。これにより、キャンバスのアクティビティの下に表示される名前にサフィックスが追加されます。 これは、ジャーニーで同じアクティビティを複数回使用し、より簡単に識別したい場合に便利です。また、エラーが発生した場合のデバッグも容易になり、レポートも読みやすくなります。 また、オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を追加することもできます。

![](assets/journey-action-label.png)

>[!NOTE]
>
>一部のアクティビティでは、その ID もパネルに表示されます。この ID は、変更される可能性があるラベルよりも安定したキーとしてレポートに使用できます。

### 詳細パラメーターの管理 {#advanced-parameters}

ほとんどのアクティビティには、変更できない多数の詳細なパラメーターや技術的なパラメーターが表示されます。

![](assets/journey-advanced-parameters.png)

読みやすくするために、「**[!UICONTROL 読み取り専用フィールドを非表示]** ボタンを使用して、これらのパラメーターを非表示にします。

![](assets/journey-hide-read-only-fields.png)

一部のコンテキストでは、特定の用途でこれらのパラメーターの値を上書きできます。値を強制的に指定するには、フィールドの右側にある「**[!UICONTROL パラメーターの上書きを有効にする]**」アイコンをクリックします。[詳細情報](../configuration/primary-email-addresses.md#journey-parameters)

![](assets/journey-enable-parameter-override.png)

### 代替パスの追加

アクションまたは条件でエラーが発生すると、個人のジャーニーは停止します。続行するには、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスをオンにするだけです。詳しくは、[この節](../building-journeys/using-the-journey-designer.md#paths)を参照してください。

![](assets/journey42.png)
