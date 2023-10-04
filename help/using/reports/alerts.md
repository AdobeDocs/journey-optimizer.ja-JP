---
solution: Journey Optimizer
product: journey optimizer
title: アラート
description: アラートの管理方法について学ぶ
feature: Alerts
topic: Administration
role: Admin
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: 4f4912530f6d39ba937b346f9eaccceff4b974dd
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 15%

---

# アラートの基本を学ぶ {#alerts}

## アラート機能 {#alerting-capabilities}

ユーザーインターフェイスからシステムアラートにアクセスしたり、エラーが発生した場合に E メールを受け取ったりできます。 次から： **アラート** メニューで、使用可能なアラートを表示し、それらを購読できます。 操作が一定の条件に達すると（システムがしきい値に達した場合に問題が発生する可能性があるなど）、アラートメッセージは、組織内でその条件を購読しているユーザーに配信されます。

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

Adobe Experience Platformのアラートの詳細については、 [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=ja){target="_blank"}.

左側のメニューの&#x200B;**管理**&#x200B;で、「**アラート**」をクリックします。Journey Optimizerの事前設定済みアラートには、次の 2 つがあります。 [ジャーニーのカスタムアクションエラー](#alert-custom-actions) 警告と [セグメント読み取りトリガー失敗](#alert-read-audiences) アラート。 これらのアラートの詳細は以下のとおりです。

ユーザーインターフェイスで **購読** オプションを **アラート** ダッシュボード。 同じ方法を使用して購読を解除します。

![](assets/alert-subscribe.png)

また、を通じてアラートを購読することもできます [I/O イベントの通知](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html?lang=ja){target="_blank"}ただし、アラートルールは、異なるサブスクリプションパッケージに整理されます。

予期しない動作が発生した場合は、購読者にアラート通知が送信されます。 ユーザーの環境設定に基づいて、アラートは E メールで、またはJourney Optimizer通知センター内（ユーザーインターフェイスの右上隅）に直接送信されます。

アラートが解決されると、購読者は「解決済み」通知を受け取ります。

>[!WARNING]
>
>Adobe Journey Optimizer固有のアラートは、次の場合にのみ適用されます： **live** ジャーニー。 テストモードのジャーニーに対しては、アラートはトリガーされません。

## ジャーニーのカスタムアクションエラー {#alert-custom-actions}

このアラートは、カスタムアクションが失敗した場合に警告を表示します。過去 5 分間に特定のカスタムアクションで 1％以上のエラーが発生した場合、エラーが発生したとみなします。これは 30 秒ごとに評価されます。

![](assets/alerts-custom-action.png)

カスタムアクションに関するアラートは、過去 5 分間に次の場合に解決されます。

* そのカスタムアクションに関するエラー（または 1%しきい値を下回るエラー）はありません。

* または、そのカスタムアクションに到達したプロファイルはありません。

カスタムアクションアラートに対応する I/O イベントのサブスクリプション名は次のとおりです。 **ジャーニーのカスタムアクションエラー**.

## セグメント読み取りトリガー失敗 {#alert-read-audiences}

このアラートは、 **オーディエンスの閲覧** アクティビティは、スケジュールされた実行時間の後、10 分間プロファイルを処理していません。 このエラーは、技術的な問題が原因で発生しているか、オーディエンスが空であることが原因で発生しています。

![](assets/alerts1.png)

アラート： **オーディエンスの閲覧** アクティビティは、繰り返しジャーニーにのみ適用されます。 **オーディエンスの閲覧** 実行スケジュールを持つライブジャーニー内のアクティビティ **1 回** または **できるだけ早く** は無視されます。

アラート： **オーディエンスの閲覧** は、プロファイルが **オーディエンスの閲覧** ノード。

に対応する I/O イベントのサブスクリプション名 **セグメント読み取りトリガー失敗** アラートは次のとおりです。 **ジャーニー読み取りセグメントの遅延、エラー、エラー**.
