---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーへのビルトインのチャネルアクションの追加
description: ジャーニーにビルトインのチャネルアクションを追加する方法について説明します。
feature: Journeys, Activities, Channels Activity
topic: Content Management
role: User
level: Intermediate
keywords: ジャーニー, メッセージ, プッシュ, sms, メール, アプリ内, web, コンテンツカード, コードベースのエクスペリエンス
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: db3c87d10469550eb30224c932344ff1e3ae1767
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 100%

---

# ビルトインのチャネルアクションの使用 {#add-a-message-in-a-journey}

>[!CONTEXTUALHELP]
>id="ajo_message_activity"
>title="ビルトインのチャネルアクション"
>abstract="Journey Optimizer には、ビルトインのチャネルアクション機能が含まれています。メッセージ（メール、テキストメッセージ（SMS/MMS）、プッシュ）またはインバウンドエクスペリエンス（アプリ内、web、コードベースのエクスペリエンス、コンテンツカード）アクティビティをジャーニーに追加し、設定とコンテンツを定義するだけです。その後、アクティビティはジャーニーのコンテキストで実行および送信されます。"

[!DNL Journey Optimizer] には、メッセージの送信に使用されるビルトインのチャネルアクション機能が備わっています。プロファイルがこのアクティビティにエントリすると、メッセージが送信されます。

ビルトインのチャネルアクションをジャーニーに追加するには、チャネルアクティビティをドラッグ＆ドロップし、その設定とコンテンツを定義します。その後、アクティビティはジャーニーのコンテキストで実行および送信されます。

>[!NOTE]
>
>また、[!DNL Journey Optimizer] でメッセージを送信するカスタムアクションを設定することもできます。[詳細情報](#recommendation)

## ジャーニーでのメッセージの追加  {#add-msg-in-journey}

ビルトインのチャネルアクションを使用すると、アウトバウンドまたはインバウンドメッセージを設定できます。サポートされるインバウンドチャネルは、メール、テキストメッセージ（SMS／MMS）およびプッシュ通知です。サポートされるアウトバウンドチャネルは、アプリ内、web、コードベースのエクスペリエンスおよびコンテンツカードです。

ジャーニーにビルトインのチャネルアクションを追加するには、次の手順に従います。

1. ジャーニーを[イベント](general-events.md)または[オーディエンスを読み取り](read-audience.md)アクティビティで開始します。

1. パレットの「**アクション**」セクションから、チャネルアクティビティをキャンバスにドラッグ＆ドロップします。

   ![](assets/journey-web-activity.png)


1. アクティビティを設定します。設定ガイドラインについて詳しくは、以下のリンクを参照してください。

   * アウトバウンドアクションを作成する方法を次に説明します。

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../email/create-email.md">
      <img alt="リード" src="../assets/do-not-localize/email.jpg">
      </a>
      <div><a href="../email/create-email.md"><strong>メールの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../push/create-push.md">
      <img alt="低頻度" src="../assets/do-not-localize/push.jpg">
      </a>
      <div>
      <a href="../push/create-push.md"><strong>プッシュ通知の作成<strong></a>
      </div>
      <p>
      </td>
      <td>
      <a href="../sms/create-sms.md">
      <img alt="検証" src="../assets/do-not-localize/sms.jpg">
      </a>
      <div>
      <a href="../sms/create-sms.md"><strong>テキストメッセージ（SMS／MMS）の作成</strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

   * インバウンドアクションを作成する方法を次に説明します。

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../in-app/create-in-app.md">
      <img alt="リード" src="../assets/do-not-localize/in-app.jpg">
      </a>
      <div><a href="../in-app/create-in-app.md"><strong>アプリ内メッセージの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../web/create-web.md">
      <img alt="リード" src="../assets/do-not-localize/web-create.jpg">
      </a>
      <div><a href="../web/create-web.md"><strong>Web エクスペリエンスの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../content-card/create-content-card.md">
      <img alt="リード" src="../assets/do-not-localize/sms-config.jpg">
      </a>
      <div><a href="../content-card/create-content-card.md"><strong>コンテンツカードの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../code-based/create-code-based.md">
      <img alt="低頻度" src="../assets/do-not-localize/web-design.jpg">
      </a>
      <div>
      <a href="../code-based/create-code-based.md"><strong>コードベースのエクスペリエンスの作成<strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

>[!NOTE]
>
>* 各インバウンドエクスペリエンスアクティビティには、3 日間の&#x200B;**待機**&#x200B;アクティビティが付属しています。[詳細情報](wait-activity.md#auto-wait-node)
>
>* メールおよびプッシュ通知の場合、送信時間の最適化を有効にできます。[詳細情報](send-time-optimization.md)



## ライブコンテンツの更新 {#update-live-content}

ライブジャーニーでビルトインのチャネルアクションのコンテンツを更新できます。

それには、ライブジャーニーを開き、チャネルアクティビティを選択して、「**コンテンツを編集**」をクリックします。

![](assets/add-a-message2.png)

ただし、パーソナライゼーションで使用されている属性は、プロファイル属性であるかコンテキストデータ（イベントプロパティまたはジャーニープロパティから得られるもの）であるかにかかわらず、変更できません。

コンテキストデータを変更すると、次のエラーメッセージが表示されます：`ERR_AUTHORING_JOURNEYVERSION_201`

プロファイル属性を変更すると、次のエラーメッセージが表示されます：`ERR_AUTHORING_JOURNEYVERSION_202`

アプリ内アクティビティの場合、ジャーニーのライブ中にコンテンツを変更できますが、アプリ内トリガーは変更できません。

## カスタムアクションを使用した送信 {#recommendation}

ビルトインのメッセージ機能を使用する代わりに、カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。

* サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを作成できます。[詳細情報](../action/action.md)

* Adobe Campaign を操作する場合は、次の節を参照してください。

   * [[!DNL Journey Optimizer] と Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] と Campaign Standard](../action/acs-action.md)