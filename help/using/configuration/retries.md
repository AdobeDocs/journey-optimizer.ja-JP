---
solution: Journey Optimizer
product: journey optimizer
title: 再試行
description: アドレスを抑制リストに送信する前に再試行が行われるしくみを学ぶ
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
keywords: 再試行, バウンス, ソフト, Optimizer, エラー
exl-id: 05564a99-da50-4837-8dfb-bb1d3e0f1097
source-git-commit: 9657862f1c6bdb2399fcf3e6384bb9dec5b8f32b
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---

# 再試行 {#retries}

一時的な&#x200B;**ソフトバウンス**&#x200B;エラーが原因でメールメッセージの送信に失敗した場合は、再試行が数回実行されます。エラーが 1 つ発生すると、エラーカウンターを 1 つ増やします。このカウンターがしきい値の制限に達すると、アドレスが抑制リストに追加されます。

>[!NOTE]
>
>エラーのタイプについて詳しくは、[配信失敗のタイプ](../reports/suppression-list.md#delivery-failures)の節を参照してください。

デフォルト設定では、しきい値は 5 回のエラーに設定されています。

* 同じ配信で[再試行期間](#retry-duration)内に 5 回目のエラーが発生した場合、そのアドレスは抑制されます。

* 異なる配信で 2 つのエラーが 24 時間以上の間隔で発生した場合は、エラーが発生するたびにエラーカウンターが増加し、5 回目の試行失敗で、やはりアドレスが抑制されます。

再試行後に配信が成功すると、そのアドレスのエラーカウンターは再初期化されます。

## 再試行しきい値の編集 {#edit-retry-threshold}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list_bounces"
>title="再試行しきい値を更新"
>abstract="デフォルト値がニーズに合わない場合は、連続ソフトバウンスの許容回数を変更できます。再試行カウンターが特定のメールアドレスのエラーしきい値に達すると、このアドレスは抑制リストに追加されます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/deliverability/suppression-list.html?lang=ja" text="抑制リストについて"

デフォルト値の 5 がニーズに合わない場合は、次の手順に従ってエラーのしきい値を変更できます。

1. **[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL 抑制リスト]**&#x200B;に移動します。

1. 「**[!UICONTROL 抑制ルールを編集]**」ボタンを選択します。

   ![](assets/suppression-list-edit-retries.png)

1. 必要に応じて、連続するソフトバウンスの許容数を編集します。

   ![](assets/suppression-list-edit-soft-bounces.png)

   1～20 の整数値を入力する必要があります。つまり、再試行の最小回数は 1 で、最大回数は 20 です。

   >[!CAUTION]
   >
   >値が 10 を超えると、配信品質の評価の問題や、IP スロットル、ISP によるブロックリストへの登録などにつながる可能性があります。[配信品質の詳細](../reports/deliverability.md)

## 再試行期間 {#retry-duration}

**再試行期間**&#x200B;は、一時的なエラーまたはソフトバウンスが発生した配信のメールメッセージを再試行する期間です。

デフォルトでは、メッセージがメールキューに追加されてから **3.5 日**（**84 時間**）の間、再試行が実行されます。

ただし、再試行が不要になったときにそれ以上実行されないようにするため、メールチャネルに適用する[チャネルサーフェス](channel-surfaces.md)（メッセージプリセットなど）を作成または編集する際に、必要に応じてこの設定を変更できます。

例えば、1 日のみ有効なリンクを含むパスワードリセットに関するトランザクションメールの場合は、再試行期間を 24 時間に設定できます。同様に、真夜中のセールの場合は、再試行期間を 6 時間に設定するとよいでしょう。

>[!NOTE]
>
>再試行期間は 84 時間を超えることはできません。再試行期間の下限は、マーケティングメールの場合は 6 時間、トランザクションメールの場合は 10 分です。

チャネルサーフェスの作成時にメール再試行パラメーターを調整する方法については、[この節](../email/email-settings.md#email-retry)を参照してください。

