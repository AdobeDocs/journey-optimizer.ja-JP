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
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 100%

---


# 再試行 {#retries}

一時的な&#x200B;**ソフトバウンス**&#x200B;または&#x200B;**無視**&#x200B;のエラーによってメッセージの送信に失敗した場合は、再試行が実行されます。エラーが 1 つ発生すると、エラーカウンターを 1 つ増やします。このカウンターがしきい値の制限に達すると、アドレスが抑制リストに追加されます。

デフォルト設定<!--so can you edit this setting or not?? contradictory information was given-->では、エラー数のしきい値は 3 つです。

* 同じ配信の場合、3 回目に発生したエラーでアドレスが抑制されます。

* 異なる配信があり、2 つのエラーが 24 時間以上の間隔で発生した場合は、エラーが発生するたびにエラーカウンターを増加し、アドレスは 3 回目の試行で抑制されます。

再試行後に配信が成功すると、そのアドレスのエラーカウンターは初期化されます。

しきい値の制限は、**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL 一般]**&#x200B;メニューの&#x200B;**[!UICONTROL 編集]**&#x200B;ボタンを使用して変更できます。<!--currently you can edit this in staging // now I see in UI: Suppression rule > Bounce days??? > 4-->

![](../assets/retries-edition.png)

## メッセージの再試行期間 {#retry-duration}

再試行は、メッセージがメールのキューに入ってから **3.5 日間**&#x200B;実行されます。

再試行間の最小遅延と再試行の最大実行回数は、<!--managed by the Enhanced MTA,-->過去および現在における、そのドメインでの IP のパフォーマンスに基づきます。

3.5 日が経過すると、再試行キュー内のメッセージはキューから削除され、バウンスとして返されます。<!--???-->