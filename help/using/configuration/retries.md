---
title: 再試行
description: アドレスを抑制リストに送信する前に再試行を実行する方法を説明します
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
ht-degree: 40%

---


# 再試行 {#retries}

一時的な&#x200B;**ソフトバウンス**&#x200B;または&#x200B;**無視**&#x200B;のエラーが原因でメッセージが失敗した場合は、いくつかの再試行が実行されます。 各エラーは、エラーカウンターを1つ増やします。 このカウンタが制限しきい値に達すると、アドレスが抑制リストに追加されます。

デフォルトの設定<!--so can you edit this setting or not?? contradictory information was given-->では、しきい値は次の3つのエラーに設定されます。

* 同じ配信の場合、3番目に発生したエラーでは、アドレスが抑制されます。

* 異なる配信があり、2 つのエラーの間隔が 24 時間以上離れて発生した場合、エラーが発生するたびにエラーカウンターは増加し、アドレスも 3 回目の試行で抑制されます。

再試行後に配信が成功した場合は、アドレスのエラーカウンターが再初期化されます。

制限しきい値は、**[!UICONTROL チャネル]** / **[!UICONTROL Eメール設定]** / **[!UICONTROL 一般]**&#x200B;メニューの&#x200B;**[!UICONTROL 編集]**&#x200B;ボタンを使用して変更できます。<!--currently you can edit this in staging // now I see in UI: Suppression rule > Bounce days??? > 4-->

![](../assets/retries-edition.png)

## メッセージの再試行時間{#retry-duration}

再試行は、メッセージがEメールキューに追加されてから3.5日&#x200B;**間実行されます。**

再試行間の最小遅延と再試行の最大実行回数は、<!--managed by the Enhanced MTA,-->過去および現在における、そのドメインでの IP のパフォーマンスに基づきます。

3.5 日が経過すると、再試行キュー内のメッセージはキューから削除され、バウンスとして返されます。<!--???-->