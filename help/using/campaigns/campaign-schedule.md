---
solution: Journey Optimizer
product: journey optimizer
title: アクションキャンペーンのスケジュール設定
description: アクションキャンペーンのスケジュールを設定する方法を説明します。
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: 作成, Optimizer, キャンペーン, サーフェス, メッセージ
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 32%

---


# アクションキャンペーンのスケジュール設定 {#action-campaign-schedule}

「**[!UICONTROL スケジュール]**」タブでは、キャンペーンスケジュールを定義できます。

デフォルトでは、アクションキャンペーンは手動でアクティブ化すると開始され、メッセージが 1 回送信されるとすぐに終了します。 アクティブ化直後にキャンペーンを実行しない場合は、「**[!UICONTROL キャンペーン開始]**」オプションを使用して、メッセージを送信する日時を指定することができます。

「**[!UICONTROL キャンペーン終了]**」オプションを使用すると、キャンペーンの実行を停止するタイミングを指定できます。 指定した日付以外は、キャンペーンは実行されません。

![](assets/create-campaign-schedule.png)

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer] でキャンペーンをスケジュールする場合は、開始日時が目的の最初の配信に合っていることを確認します。繰り返しキャンペーンで、最初にスケジュールした時間が既に過ぎている場合、キャンペーンは繰り返しルールに従って、次に使用可能な時間スロットに繰り越されます。

キャンペーンチャネルに応じて、次のような追加のスケジュールオプションを使用できます。

* **頻度** （メール、SMS、プッシュアクション）

  キャンペーンのメッセージを送信する頻度を定義できます。これを行うには、キャンペーンの作成画面にある「**[!UICONTROL アクショントリガー]**」オプションを使用して、キャンペーンの実行頻度を日単位、週単位または月単位のいずれにするかを指定します。

* **IP ウォームアッププランのアクティベーション** （メール）

  メールキャンペーンの場合は、特定の IP ウォームアッププランのアクティベーションキャンペーンを作成できます。 キャンペーンスケジュールは、関連付けられる IP ウォームアッププランによって決定されます。つまり、スケジュールはキャンペーン自体では定義されません。 [IP ウォームアップキャンペーンの作成方法を説明します ](../configuration/ip-warmup-campaign.md)。

## 次の手順 {#next}

キャンペーンスケジュールの準備が整ったら、キャンペーンをレビューしてアクティブ化できます。 [詳細情報](review-activate-campaign.md)
