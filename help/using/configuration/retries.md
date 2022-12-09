---
solution: Journey Optimizer
product: journey optimizer
title: 再送
description: 抑制リストにアドレスを送信する前に再試行が実行されるしくみについて説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 05564a99-da50-4837-8dfb-bb1d3e0f1097
source-git-commit: 021cf48ab4b5ea8975135a20d5cef8846faa5991
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# 再送 {#retries}

一時的 **なソフトバウンス** エラーによって電子メールメッセージが失敗した場合は、数回試行が実行されます。 各エラーでは、エラーカウンターが増加します。 このカウンターが制限しきい値に達したときに、アドレスが抑制リストに追加されます。

>[!NOTE]
>
>「配信エラータイプ ](../reports/suppression-list.md#delivery-failures) 」セクションに [ あるエラーの種類について詳しくは、こちらを参照してください。

デフォルトの設定では、閾値は5エラーに設定されています。

* 同じ配信については、再試行期間 ](#retry-duration) 内 [ に5番目のエラーが発生すると、アドレスは表示されません。

* 別のメッセージが表示され、少なくとも24時間の間に2つのエラーが発生した場合は、エラーカウンターがエラーごとに加算されます。また、5回目の試行時にもエラーカウンターが表示されます。

再実行後に配信が成功した場合は、アドレスのエラーカウンターが再初期化されます。

## リトライしきい値のエディション {#edit-retry-threshold}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list_bounces"
>title="リトライしきい値の更新"
>abstract="デフォルト値が要件に適合しない場合は、連続するソフトバウンスの許可回数を変更することができます。 Retry カウンターが特定の電子メールアドレスのエラーしきい値に達すると、このアドレスが抑制リストに追加されます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/deliverability/suppression-list.html" text="Suppresion リストについて"

デフォルト値5がニーズに適合しない場合は、以下の手順に従ってエラーのしきい値を修正できます。

1. > **[!UICONTROL Email configuration]** > **[!UICONTROL Suppression list]** を **[!UICONTROL Channels]** 参照してください。

1. **[!UICONTROL Edit suppression rules]**&#x200B;ボタンを選択します。

   ![](assets/suppression-list-edit-retries.png)

1. 必要に応じて、連続するソフトバウンスの回数を編集することもできます。

   ![](assets/suppression-list-edit-soft-bounces.png)

   1 ~ 20 の整数値を入力する必要があります。これは、リトライの最小回数は1、最大数は20です。

   >[!CAUTION]
   >
   >10より大きい値を指定すると、deliverability 評判の問題が発生する場合があります。また、Isp によって IP スロットルやブロックリストが表示されることもあります。 [Deliverability について詳しくは、](../reports/deliverability.md)

## 再試期間 {#retry-duration}

**リトライ時間** は、配信に一時的なエラーまたはソフトバウンスが発生したことを示す電子メールメッセージが再送されるタイムフレームです。

デフォルトでは、メッセージを電子メールキューに追加した時点から、リトライは3.5 日 **(または** 84 時間 **) に** 実行されます。

ただし、不要になったときにリトライが実行されないようにするには、この設定を必要に応じて変更します。これにより、チャネルサーフェス ](channel-surfaces.md) (メッセージプリセット) を作成または編集 [ するときに、電子メールチャンネルに適用できます。

例えば、パスワードをリセットするというトランザクションについては、再試が24時間に設定されています。また、1日あたりのリンクが有効になっています。 同様に、深夜のセールについては、6時間のリトライ時間を定義することもできます。

>[!NOTE]
>
>再試行の間隔は84時間を超えることはできません。 電子メールで送信する場合は、少なくとも6分の時間がかかります。

この節 ](channel-surfaces.md#create-channel-surface) で [ は、チャネルサーフェスを作成する際に電子メール再実行パラメーターを調整する方法について説明します。

