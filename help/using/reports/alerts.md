---
solution: Journey Optimizer
product: journey optimizer
title: システムアラートへのアクセスと購読
description: システムアラートへのアクセスと購読方法を学ぶ
feature: Journeys, Alerts
topic: Administration
role: User
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: da2fb137a8af82a8487638dc3d762377dd5dc506
workflow-type: ht
source-wordcount: '654'
ht-degree: 100%

---

# システムアラートへのアクセスと購読 {#alerts}

ジャーニーとキャンペーンを作成する場合は、「**アラート**」ボタンを使用してエラーを確認および解決してから、実行または公開します。ジャーニーをトラブルシューティングする方法について詳しくは、[このページ](../building-journeys/troubleshooting.md)を参照してください。キャンペーンをレビューする方法について詳しくは、[このページ](../campaigns/review-activate-campaign.md)を参照してください。

また、このページで詳しく説明されているように、Adobe Journey Optimizer システムアラートを購読することもできます。

## アラートへのアクセスと購読 {#alerting-capabilities}

エラーが発生した場合は、Journey Optimizer 通知センター（アプリ内アラート）でシステムアラートを受信したり、メールを受信したりできます。

**アラート**&#x200B;メニューから、使用可能なアラートを表示して購読できます。操作の特定の条件（システムがしきい値に達した場合に問題が発生する可能性があるなど）に達すると、その条件を購読している組織内のユーザーにアラートメッセージが配信されます。

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

Adobe Experience Platform のアラートについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=ja){target="_blank"}を参照してください。

左側のメニューの&#x200B;**管理**&#x200B;で、「**アラート**」をクリックします。Journey Optimizer では、[ジャーニーカスタムアクションエラー](#alert-custom-actions)アラートと[オーディエンスを読み取りのトリガー失敗](#alert-read-audiences)アラートの、2 つの事前設定アラートが使用可能です。次に、これらのアラートについて詳しく説明します。

**アラート**&#x200B;ダッシュボードから「**購読**」オプションを選択すると、ユーザーインターフェイスから各アラートを個別に購読できます。登録解除する場合も同じ方法を使用します。

![](assets/alert-subscribe.png)

また、[I/O イベント通知](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html?lang=ja){target="_blank"}を通じてアラートを購読することもできます。アラートルールは、様々な購読パッケージに整理されます。特定の Journey Optimizer アラートに対応するイベント購読については、以下で詳しく説明します。

予期しない動作が発生した場合は、購読者にアラート通知が送信されます。ユーザーの環境設定に基づいて、アラートはメールで送信されるか、ユーザーインターフェイスの右上隅にある Journey Optimizer 通知センター内で直接送信されます。デフォルトでは、アプリ内アラートのみが有効になっています。メールアラートを有効にするには、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html?lang=ja#enable-email-alerts){target="_blank"}を参照してください。

アラートが解決されると、購読者に「解決済み」通知が届きます。

>[!CAUTION]
>
>Adobe Journey Optimizer に特定のアラートは、**ライブ**&#x200B;ジャーニーにのみ適用されます。 テストモードのジャーニーでは、アラートはトリガーされません。

## ジャーニーカスタムアクションエラー {#alert-custom-actions}

このアラートは、カスタムアクションが失敗した場合に警告を表示します。過去 5 分間に特定のカスタムアクションで 1％以上のエラーが発生した場合、エラーが発生したとみなします。これは 30 秒ごとに評価されます。

![](assets/alerts-custom-action.png)

カスタムアクションに関するアラートは、過去 5 分間ににわたり次の場合に解決されます。

* そのカスタムアクションに関するエラー（または 1％のしきい値を下回るエラー）が発生していない。

* または、そのカスタムアクションに到達したプロファイルがない。

カスタムアクションアラートに対応する I/O イベント登録名は、**ジャーニーカスタムアクションエラー**&#x200B;です。

## オーディエンストリガーの読み取りが失敗しました {#alert-read-audiences}

このアラートは、スケジュールされた実行時間から 10 分経過しても、「**オーディエンスを読み取り**」アクティビティでプロファイルを処理されなかった場合に警告します。このエラーは、技術的な問題やオーディエンスが空であることが原因で発生する可能性があります。このエラーが技術的な問題によって発生した場合、問題のタイプに応じて、再試行が引き続き行われる可能性があります（例：書き出しジョブの作成に失敗した場合、最大 1 時間、10 分ごとに再試行されます）。

![](assets/alerts1.png)

「**オーディエンスを読み取り**」アクティビティに関するアラートは、繰り返しジャーニーにのみ適用されます。**1 回**&#x200B;または&#x200B;**できるだけ早く**&#x200B;実行するスケジュールが設定されているライブジャーニーの「**オーディエンスを読み取り**」アクティビティは無視されます。

**オーディエンスを読み取り**&#x200B;に関するアラートは、プロファイルが&#x200B;**オーディエンスを読み取り**&#x200B;ノードにエントリすると解決されます。

**オーディエンスを読み取りのトリガー失敗**&#x200B;アラートに対応する I/O イベント購読名は、**ジャーニーのオーディエンスを読み取りの遅延、失敗およびエラー**&#x200B;です。

## トラブルシューティング {#alert-troubleshooting}

**オーディエンスの読み取り**&#x200B;アラートのトラブルシューティングをするには、Experience Platform インターフェイスでオーディエンス数を確認します。

![](assets/alert-troubleshooting-0.png)

![](assets/alert-troubleshooting-1.png)

**カスタムアクション**&#x200B;アラートのトラブルシューティングをするには:

* 別のジャーニーでテストモードを使用してカスタムアクションを確認：

  ![](assets/alert-troubleshooting-2.png)

* ジャーニーレポートを調べて、アクションに関するエラー理由を確認します。

  ![](assets/alert-troubleshooting-3.png)

* ジャーニーの stepEvents で「failureReason」の詳細を確認します。

* カスタムアクション設定を確認し、認証が正常であることを検証します。例えば、Postman で手動チェックを実行します。
