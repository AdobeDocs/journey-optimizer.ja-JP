---
solution: Journey Optimizer
product: journey optimizer
title: プロファイルエントリ管理
description: プロファイルエントリの管理方法について説明します
feature: Journeys
role: User
level: Intermediate
keywords: 再エントリ, ジャーニー, プロファイル, 繰り返し
exl-id: 8874377c-6594-4a5a-9197-ba5b28258c02
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---


# プロファイルエントリ管理 {#entry-management}

デフォルトでは、新規ジャーニーで再エントリが許可されています。「1 回限り」のジャーニー（例：入店時に 1 度だけギフトをオファーするなど）を作成するには、この再エントリのオプションをオフにします。すると、この例では、顧客がジャーニーに再エントリしてオファーを再度受け取るということがなくなります。

![](assets/journey-re-entrance.png)

ジャーニーが終了すると、そのステータスは&#x200B;**[!UICONTROL クローズ]**&#x200B;になります。新しい個人は、ジャーニーにエントリできなくなります。既にジャーニーにエントリしているユーザーは、通常どおりにジャーニーを終了できます。

デフォルトのグローバルタイムアウトである 30 日が経過すると、ジャーニーは&#x200B;**完了**&#x200B;ステータスに切り替わります。[詳細情報](journey-gs.md#global_timeout)。


## 単一ジャーニー{#entry-unitary}

（イベントまたはオーディエンスの選定で始まる）単一ジャーニーには、同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぐガードレールが含まれています。プロファイルの再エントリは、デフォルトで 5 分間一時的にブロックされます。 例えば、あるイベントが特定のプロファイルのジャーニーを 12:01 にトリガーし、12:03 に別のイベントが到着した場合（それが同じイベントであっても、同じジャーニーをトリガーする別のイベントであっても）、このプロファイルのジャーニーが再び開始されることはありません。

それに加えて：

* 再エントリが有効な場合、プロファイルはジャーニーに何度もエントリできますが、そのジャーニーの以前のインスタンスから完全に離脱するまでは再エントリできません。

* 再エントリが無効な場合、プロファイルは同じジャーニーに何度もエントリすることはできません

## 「オーディエンスを読み取り」ジャーニー{#entry-read-segment}

「オーディエンスを読み取り」ジャーニーの場合：

* 繰り返し発生しないジャーニーの場合：プロファイルはジャーニーに 1 回のみエントリします。

* 繰り返し発生するジャーニーの場合：オーディエンスの想定されるステータスにある場合、プロファイルは繰り返しのたびにジャーニーにエントリします。プロファイルが以前の繰り返し時からジャーニーにまだ留まっていた場合は、ジャーニーを最初からやり直します。

**オーディエンスを読み取り**&#x200B;アクティビティで始まるビジネスイベントジャーニーの場合：このジャーニーがビジネスイベントの受信に基づいていることがわかっているので、想定されるオーディエンスで認定された場合、プロファイルはビジネスイベントを受信するたびにジャーニーにエントリします。つまり、このプロファイルは、同時に同じジャーニーに何度も存在することができますが、それは異なるビジネスイベントのコンテキストの場合に限ります。

<!--
# Profile entry management {#entry-management}

There are two main types of journeys:

* event-based journeys: starting with an event, these journeys are unitary, they are associated to one individual. When the event is received, the individual enters the journey. [Read more](#entry-unitary)
* read segment journeys: starting with a read segment, these are batch journeys. Individuals belonging to the segment all enter the same journey. These journeys can be recurring or one-shot. [Read more](#entry-read-segment)

In both journey types, a profile cannot be present multiple times in the same journey, at the same time.


## Unitary journeys{#entry-unitary}

In unitary journeys, you can enable or disable re-entrance:

* If re-entrance is enabled, a profile can enter a journey several times, but cannot do it until he fully exited that previous instance of the journey.

* If re-entrance is disabled, a profile cannot enter multiple times the same journey

By default, new journeys allow re-entrance. You can uncheck the option for “one shot” journeys, for example if you want to offer a one-time gift when a person enters a shop. In that case, you don't want the customer to be able to re-enter the journey and receive the offer again. When a journey ends, its status is **[!UICONTROL Closed]**. New individuals can no longer enter the journey. Persons already in the journey finish the journey normally. [Learn more](journey-gs.md#entrance)

![](assets/journey-re-entrance.png)

After the default global timeout of 30 days, the journey switches to the **Finished** status. New individuals can no longer enter the journey. Persons already in the journey finish the journey normally.Due to the 30-day journey timeout, when journey re-entrance is not allowed, we cannot make sure the re-entrance blocking will work more than 30 days. Indeed, as we remove all information about persons who entered the journey 30 days after they enter, we cannot know the person entered previously, more than 30 days ago. [Learn more](journey-gs.md#global_timeout).

Unitary journeys (starting with an event or a segment qualification) include a guardrail that prevents journeys from being erroneously triggered multiple times for the same event. Profile re-entrance is temporally blocked by default for 5 minutes. For instance, if an event triggers a journey at 12:01 for a specific profile and another one arrives at 12:03 (whether it is the same event or a different one triggering the same journey) that journey will not start again for this profile.

The key is also used to check that a person is in a journey. Indeed, a person cannot be at two different places in the same journey. As a result, the system does not allow the same key, for example the key CRMID=3224, to be at different places in the same journey.

## Read segment journeys{#entry-read-segment}

In a read segment journey:

* For non-recurring journeys: the profile enters once and only once the journey.

* For recurring journeys: by default, all the profiles belonging to the segment enters the journey on each recurrence. They must finish the journey before they can reenter in another occurrence. 

>[!NOTE]
>
>Two options are available for recurring read segment journeys. The **Force reentrance on recurrence** option makes all the profiles still present in the journey automatically exit it on the next execution. The **Incremental read** option only targets the individuals who entered the segment since the last execution of the journey. Refer to this [section](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

In business event journeys starting with a **Read segment** activity: knowing that this journey is based on the reception of a business event, if the profile is qualified in the expected segment, they will enter the journey for each business event received, meaning that this profile can be multiple times in the same journey, at the same time, but in the context of different business events.
-->