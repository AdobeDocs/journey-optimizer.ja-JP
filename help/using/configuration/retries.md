---
solution: Journey Optimizer
product: journey optimizer
title: 再試行
description: アドレスを抑制リストに送信する前に再試行が行われるしくみを学ぶ
feature: Deliverability, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: 再試行, バウンス, ソフト, Optimizer, エラー
exl-id: 05564a99-da50-4837-8dfb-bb1d3e0f1097
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: ht
source-wordcount: '578'
ht-degree: 100%

---

# 再試行 {#retries}

特定のアドレスに対する一時的な&#x200B;**ソフトバウンス**&#x200B;エラーが原因でメールメッセージの送信に失敗した場合は、再試行が数回実行されます。エラーが 1 つ発生すると、エラーカウンターを 1 つ増やします。このカウンターがしきい値の制限に達すると、メールアドレスが抑制リストに追加されます。

>[!NOTE]
>
>エラーのタイプについて詳しくは、[配信失敗のタイプ](../reports/suppression-list.md#delivery-failures)の節を参照してください。

デフォルト設定では、しきい値は 5 回のエラーに設定されています。

* 同じ配信で[再試行期間](#retry-duration)内に 5 回目のエラーが発生した場合、そのアドレスは抑制されます。

* 異なる配信で 2 つのエラーが 24 時間以上の間隔で発生した場合は、エラーが発生するたびにエラーカウンターが増加し、5 回目の試行失敗で、やはりアドレスが抑制されます。エラーは、各アドレスに対して累積されます。

再試行後に配信が成功すると、そのアドレスのエラーカウンターは再初期化されます。

例：

* 月曜日に、再試行期間を 24 時間に設定してメールを送信するとします。emma.jones@mail.com アドレスは配信に失敗します。メールは最大 3 回再試行され、24 時間の再試行期間に到達すると再試行が停止します。

* 水曜日に別のメールを送信するとします。既にエラー数が 3 件カウントされている emma.jones@mail.com もターゲットにされ、再び 2 回配信に失敗します。さらに 2 件のエラーが計上されます。

これら 2 つのメール間に他の配信が試行されて成功しなかった場合、3 + 2 エラーの累積的な影響を考慮して、emma.jones@mail.com アドレスが抑制リストに追加されます。

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

ただし、再試行が不要になったときにそれ以上実行されないようにするため、メールチャネルに適用する[チャネル設定](channel-surfaces.md)（メッセージプリセットなど）を作成または編集する際に、必要に応じてこの設定を変更できます。

例えば、1 日のみ有効なリンクを含むパスワードリセットに関するトランザクションメールの場合は、再試行期間を 24 時間に設定できます。同様に、真夜中のセールの場合は、再試行期間を 6 時間に設定するとよいでしょう。

>[!NOTE]
>
>再試行期間は 84 時間を超えることはできません。再試行期間の下限は、マーケティングメールの場合は 6 時間、トランザクションメールの場合は 10 分です。

チャネル設定の作成時にメール再試行パラメーターを調整する方法については、[この節](../email/email-settings.md#email-retry)を参照してください。

