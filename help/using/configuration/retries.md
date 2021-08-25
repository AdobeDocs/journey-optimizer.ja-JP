---
title: 再試行
description: アドレスを抑制リストに送信する前に再試行が行われるしくみを学ぶ
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
source-git-commit: 79c3c47eb6978f377bf4dc49f787e9a509aa3f61
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 38%

---


# 再試行 {#retries}

一時的な&#x200B;**ソフトバウンス**&#x200B;または&#x200B;**無視**&#x200B;のエラーが原因で電子メールメッセージが失敗した場合は、いくつかの再試行が実行されます。 エラーが 1 つ発生すると、エラーカウンターを 1 つ増やします。このカウンターがしきい値の制限に達すると、アドレスが抑制リストに追加されます。

>[!NOTE]
>
>エラーのタイプについて詳しくは、[配信エラーのタイプ](../suppression-list.md#delivery-failures)の節を参照してください。

デフォルト設定では、エラー数のしきい値は 3 つです。

* 同じ配信の場合、3 回目に発生したエラーでアドレスが抑制されます。

* 異なる配信があり、2 つのエラーが 24 時間以上の間隔で発生した場合は、エラーが発生するたびにエラーカウンターを増加し、アドレスは 3 回目の試行で抑制されます。

再試行後に配信が成功すると、そのアドレスのエラーカウンターは初期化されます。

しきい値の制限は、**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL 一般]**&#x200B;メニューの&#x200B;**[!UICONTROL 編集]**&#x200B;ボタンを使用して変更できます。

![](../assets/retries-edition.png)

<!--The minimum delay between retries and the maximum number of retries to be performed are based on how well an IP is performing, both historically and currently, at a given domain.-->

## 再試行期間 {#retry-duration}

**再試行期間**&#x200B;は、一時的なエラーまたはソフトバウンスが発生した配信のEメールメッセージを再試行する期間です。

デフォルトでは、メッセージが電子メールキューに追加されてから3.5日&#x200B;**（または** 84時間&#x200B;**）再試行が実行されます。**

ただし、不要になったときに再試行が実行されないようにするには、Eメールチャネルに適用する[メッセージプリセット](message-presets.md)を作成または編集する際に、必要に応じてこの設定を変更します。

例えば、パスワードのリセットに関連し、1日のみ有効なリンクを含むトランザクションEメールの再試行期間を24時間に設定できます。 同様に、真夜中のセールの場合は、再試行期間を6時間に設定する必要があります。

>[!NOTE]
>
>再試行期間は84時間を超えることはできません。 最小再試行期間は、マーケティングEメールの場合は6時間、トランザクションEメールの場合は10分です。

[この節](message-presets.md#create-message-preset)でメッセージプリセットを作成する際のEメールの再試行パラメーターの調整方法を説明します。

<!--After 3.5 days, any message in the retry queue will be removed from the queue and sent back as a bounce.-->