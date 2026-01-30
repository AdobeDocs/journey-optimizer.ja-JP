---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーレポート
description: ジャーニーレポートからダイレクトデータを使用する方法について説明します
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 6fae8beb-ca40-40a1-8939-c309fbf46c4f
source-git-commit: 7945ab9369498f23685aa2f727542c7367c2d830
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 92%

---

# ダイレクトメールジャーニーレポート {#journey-global-report}

>[!BEGINSHADEBOX]

ダイレクトメールジャーニーレポートにアクセスするには、ジャーニー内の「**[!UICONTROL レポートを表示]**」ボタンをクリックします。[詳細情報](report-gs-cja.md)

![](assets/report-access-jo.png)

>[!ENDSHADEBOX]

## 送信統計 {#sending-statistics-directmail}

![](assets/cja-direct-sending-stat.png)

**[!UICONTROL 送信統計]**&#x200B;テーブルでは、ダイレクトメールジャーニーのパフォーマンスに関するインサイトを得ることができます。ターゲット受信者の数や、正常に配信されたメールの数などの主要指標を確認します。これらはメールのリーチと効果を測定するのに役立ちます。

+++ 詳しくは、送信統計指標を参照してください

* **[!UICONTROL ユーザー]**：メッセージのターゲットプロファイルに適格な、ユーザープロファイルの数。

* **[!UICONTROL ターゲット]**：除外、抑制または同意削除が適用される前にオーディエンスに対して選定されたプロファイルの数。 再エントリを有効にしたジャーニーでは、プロファイルが複数回ターゲット化される場合があります。

* **[!UICONTROL 送信数]**：ダイレクトメールメッセージ用の送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に送信されたダイレクトメールメッセージの数。

* **[!UICONTROL アウトバウンドエラー数]**：送信プロセス中に発生し、プロファイルにメッセージを送信できなかったエラーの合計数。

* **[!UICONTROL アウトバウンド除外数]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

## 配信ステータス {#delivery-status-directmail}

![](assets/cja-direct-delivery-status.png)

**[!UICONTROL 配信ステータス]**&#x200B;のグラフには、ジャーニーの送信されたダイレクトメールメッセージに関するデータの包括的な見解が表示され、配信済みメールとエラー数などの主要指標に関するインサイトを得ることができます。これにより、ダイレクトメールメッセージ送信プロセスの詳細な分析が可能になり、ジャーニーの効率とパフォーマンスに関する重要な情報を得ることができます。

+++ 配信ステータス指標についての詳細情報

* **[!UICONTROL 配信済み]**：送信されたダイレクトメールメッセージの合計数に対する、正常に送信されたダイレクトメールメッセージの数。

* **[!UICONTROL アウトバウンドエラー数]**：送信プロセス中に発生し、プロファイルにダイレクトメールメッセージを送信できなかったエラーの合計数。

* **[!UICONTROL アウトバウンド除外数]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

## エラーの理由 {#error-reasons-directmail}

**[!UICONTROL エラーの理由]**&#x200B;のテーブルを使用すると、ダイレクトメールメッセージの送信プロセス中に発生した特定のエラーを識別し、発生した問題を徹底的に分析できるようになります。

## 除外された理由 {#exclude-reasons-directmail}

[&#128279;](assets/cja-direct-excluded.png)

**[!UICONTROL 除外された理由]**&#x200B;のテーブルには、ターゲットオーディエンスからユーザープロファイルを除外した結果、ダイレクトメールメッセージを受信できない原因となった様々な要因を視覚的に表示します。

除外理由の包括的なリストについては、[このページ](exclusion-list.md)を参照してください。
