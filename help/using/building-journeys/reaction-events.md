---
solution: Journey Optimizer
product: journey optimizer
title: 反応イベント
description: 反応イベントについて学ぶ
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: ジャーニー, イベント, 反応, トラッキング, Platform
exl-id: 235384f3-0dce-4797-8f42-1d4d01fa42d9
source-git-commit: 343e7bbebf35711259d2f3392f1ce5658865599a
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 100%

---

# 反応イベント {#reaction-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_reaction"
>title="反応イベント"
>abstract="このアクティビティを使用すると、同じジャーニーの中で送信したメッセージに関するトラッキングデータに反応することができます。この情報は、Adobe Experience Platform と共有した時点でリアルタイムに取り込まれます。"

パレットに表示される多数のイベントアクティビティの中に、ビルトインの&#x200B;**[!UICONTROL 反応]**イベントがあります。
このアクティビティを使用すると、同じジャーニーの中で送信したメッセージに関するトラッキングデータに反応することができます。この情報は、Adobe Experience Platform と共有した時点でリアルタイムに取り込まれます。

クリックされたメッセージや開封されたメッセージに反応することができます。

このしくみを使用して、メッセージに対する反応がない場合にアクションを実行することもできます。これには、反応アクティビティと並行して 2 つ目のパスを作成し、待機アクティビティを追加します。待機アクティビティで定義した期間に反応がない場合は、2 つ目のパスが選択されます。例えば、フォローアップメッセージを送信することもできます。

なお、キャンバスで反応アクティビティを使用できるのは、先にチャネルアクションアクティビティ（メールおよびプッシュ）がある場合のみです。

[アクションアクティビティについて](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

![](assets/journey45.png)

反応イベントは様々な手順で設定できます。

1. 反応に&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します。この手順はオプションです。
1. ドロップダウンリストから、反応するアクションアクティビティを選択します。パスの中で前のステップに配置されている任意のアクションアクティビティを選択できます。
1. 選択したアクションに応じて、反応する対象を選択します。
1. イベントタイムアウト（40 秒 ～ 90 日）とタイムアウトパスを定義できます。これにより、定義した期間内に反応しなかった人物に対して 2 つ目のパスが作成されます。反応イベントを使用するジャーニーをテストする場合、テストモードの&#x200B;**[!UICONTROL 待機時間]**&#x200B;のデフォルト値は最小値である 40 秒です。[この節](../building-journeys/testing-the-journey.md)を参照してください。

>[!NOTE]
>
>
>反応イベントでは、別のジャーニーで送信されるメッセージをトラッキングすることはできません。
>
>反応イベントは、「トラッキング対象」タイプのリンクのクリックを追跡します。購読解除とミラーページのリンクは考慮しません。

>[!IMPORTANT]
>
>Gmail などのメールクライアントでは、画像がブロックされる可能性があります。メールの開封は、メールに組み込まれた 0 ピクセルの画像を使用してトラッキングされます。画像がブロックされると、メールの開封は考慮されません。
