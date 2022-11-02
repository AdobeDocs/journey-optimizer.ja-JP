---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーアクティビティの概要
description: ジャーニーアクティビティの概要
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
source-git-commit: ca423c25d39162838368b2242c1aff99388df768
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 49%

---

# ジャーニーアクティビティの概要 {#about-journey-activities}

様々なイベント、オーケストレーション、アクションなどのアクティビティを組み合わせて、複数のステップから成るクロスチャネルのシナリオを構築します。

## イベントアクティビティ {#event-activities}

イベントとは、オンライン購入など、パーソナライズされたジャーニーをトリガーにしたものです。 誰かがジャーニーに入ると、一人の人物として進み、同じ速度で、または同じパスに沿って進む 2 人の人物はいません。 イベントでジャーニーを開始すると、イベントを受け取るとジャーニーがトリガーされます。 次に、ジャーニーの各ユーザーは、ジャーニーで定義された次の手順に個別に従います。

技術ユーザーが設定したイベント ( [このページ](../event/about-events.md)) はすべて、パレットの最初のカテゴリの画面左側に表示されます。 次のイベントアクティビティを使用できます。

* [一般イベント](../building-journeys/general-events.md)
* [反応](../building-journeys/reaction-events.md)
* [セグメントの選定](../building-journeys/segment-qualification-events.md)

![](assets/journey43.png)

ジャーニーを開始するには、イベントアクティビティをドラッグ＆ドロップします。ダブルクリックでも開始できます。

![](assets/journey44.png)

## オーケストレーションアクティビティ {#orchestration-activities}

オーケストレーションアクティビティは、ジャーニーの次のステップを決定するのに役立つ様々な条件です。 サポートケースがオープンかどうか、現在の場所での天気予報（購入を完了したかどうか、10,000 ロイヤルティポイントに達したかどうか）が該当します。

画面左側にあるパレットで、次のオーケストレーションアクティビティを使用できます。

* [条件](../building-journeys/condition-activity.md)
* [待機](../building-journeys/wait-activity.md)
* [セグメントの読み取り](../building-journeys/read-segment.md)

![](assets/journey49.png)

## アクションアクティビティ {#action-activities}

アクションとは、メッセージの送信など、何らかのトリガーの結果として発生したいものです。 顧客が体験するジャーニーの一部です。

パレットの画面左側、下 **[!UICONTROL イベント]** および **[!UICONTROL Orchestration]**&#x200B;を使用する場合、 **[!UICONTROL アクション]** カテゴリ。 次のアクションアクティビティを使用できます。

* [メール、SMS、プッシュ](../building-journeys/journeys-message.md)
* [カスタムアクション](../building-journeys/using-custom-actions.md)
* [ジャンプ](../building-journeys/jump.md)

![](assets/journey58.png)

これらのアクティビティは、様々な通信チャネルを表します。これらを組み合わせて、クロスチャネルシナリオを作成できます。

カスタムアクションを設定した場合は、それらもここに表示されます。 [詳細情報](../building-journeys/using-custom-actions.md)).

## ベストプラクティス {#best-practices}

ほとんどのアクティビティでは、**[!UICONTROL ラベル]**&#x200B;を定義できます。これにより、キャンバスのアクティビティの下に表示される名前にサフィックスが追加されます。これは、ジャーニーで同じアクティビティを複数回使用し、より簡単に識別したい場合に便利です。また、エラーが発生した場合のデバッグも容易になり、レポートも読みやすくなります。また、オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を追加することもできます。

![](assets/journey59bis.png)

アクションまたは条件でエラーが発生すると、個人のジャーニーが停止します。この処理を続行する唯一の方法は、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスにチェックを付けることです。詳しくは、[この節](../building-journeys/using-the-journey-designer.md#paths)を参照してください。

![](assets/journey42.png)
