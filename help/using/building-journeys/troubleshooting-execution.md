---
solution: Journey Optimizer
product: journey optimizer
title: ライブジャーニー実行のトラブルシューティング
description: ライブジャーニー実行でのエラーのトラブルシューティング方法について説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: トラブルシューティング, ジャーニー, チェック, エラー
source-git-commit: 61498b61f7f05e0553fe575c980fd1bee08500a3
workflow-type: ht
source-wordcount: '702'
ht-degree: 100%

---

# ライブジャーニー実行のトラブルシューティング {#troubleshooting-execution}

この節では、ジャーニーイベントのトラブルシューティングを行う方法と、プロファイルがジャーニーにエントリしたかどうか、プロファイルがジャーニーをどのように移動したか、メッセージが送信されたかどうかを確認する方法について説明します。

また、ジャーニーをテストまたは公開する前に、エラーのトラブルシューティングを行うこともできます。方法について詳しくは、[このページ](troubleshooting.md)を参照してください。

インバウンドアクションを使用している場合、トラブルシューティングを行う方法について詳しくは、[このページ](troubleshooting-inbound.md)を参照してください。

## イベントが適切に送信されているかを確認 {#checking-that-events-are-properly-sent}

ジャーニーの開始点は常にイベントです。Postman などのツールを使用してテストを実行できます。

これらのツールを介して送信する API 呼び出しが正しく送信されているかどうかを確認できます。エラーが返された場合は、呼び出しに問題があるということです。ペイロード、ヘッダー（特に組織 ID）、宛先の URL を再度確認します。ヒットするのに適した URL を管理者に問い合わせることができます。

イベントは、ソースからジャーニーに直接プッシュされるわけではありません。ジャーニーは、Adobe Experience Platform のストリーミング取得 API に依存しています。結果として、イベントに関する問題が発生した場合は、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=ja){target="_blank"}で Streaming ingestion API のトラブルシューティングを参照してください。

ジャーニーでエラー `ERR_MODEL_RULES_16` が発生してテストモードを有効にできない場合は、チャネルアクションを使用する際に、使用するイベントに [ID 名前空間](../audience/get-started-identity.md)が含まれていることを確認してください。

ID 名前空間は、テストプロファイルを一意に識別するために使用されます。例えば、メールを使用してテストプロファイルを識別する場合は、ID 名前空間の&#x200B;**メール**&#x200B;を選択する必要があります。一意の識別子が電話番号の場合は、ID 名前空間の&#x200B;**電話**&#x200B;を選択する必要があります。

## ジャーニーへのエントリを確認 {#checking-if-people-enter-the-journey}

ジャーニーレポートでは、ジャーニーへのエントリをリアルタイムで測定します。

イベントが正常に送信されたにもかかわらず、ジャーニーへのエントリが確認できない場合、ジャーニーのイベント送信とイベント受信の間に何か問題があるということです。

次の質問に従って、トラブルシューティングを開始できます。

* イベントを受信するジャーニーが、テストモードまたはライブになっているか。
* ペイロードプレビューからペイロードをコピーする前にイベントを保存したか。
* イベントペイロードにイベント ID が含まれているか。
* 正しい URL をヒットしたか。
* イベント設定ペインのペイロード構造プレビューを使用して、ストリーミング取り込み API のペイロード構造に従ったか。[このページ](../event/about-creating.md#preview-the-payload)を参照してください。
* イベントのヘッダーで正しいキーと値のペアを使用しましたか？

  ```
  X-gw-ims-org-id - your organization's ID
  Content-type - application/json
  ```

## ジャーニーの進行状況を確認 {#checking-how-people-navigate-through-the-journey}

ジャーニーレポートは、ジャーニーでの個人の進行状況を測定します。ユーザーがどこで、なぜ停止したのかを容易に特定できます。

以下に、確認すべき点をいくつか示します。

* 停止の原因が、該当するユーザーを除外する条件であるか。例えば、条件が「性別 = 男性」で、ユーザーが女性の場合。このチェックは、条件が複雑すぎない場合、ビジネスユーザーが実行できます。
* データソースへの呼び出しが応答しないためか。この情報は、ジャーニーのテスト中にテストモードログに表示されます。このジャーニーがライブになると、管理者はデータソースへの直接呼び出しをテストし、受け取った回答を確認できます。管理者は、このジャーニーを複製してテストすることもできます。

## メッセージが正常に送信されたかを確認 {#checking-that-messages-are-sent-successfully}

個人がジャーニーを適切に進んでいるのに、受信すべきメッセージが届いていない場合は、以下の点を確認します。

* [!DNL Journey Optimizer] がメッセージの送信リクエストを正しく認識している。ビジネスユーザーは、送信すべきメッセージにアクセスできます。また、最新の実行時刻がジャーニーの実行時刻と一致するかどうかを確認できます。また、受け取った最新の API 呼び出しやイベントも確認できます。
* [!DNL Journey Optimizer] が正常にメッセージを送信している。ジャーニーレポートを調べ、エラーがないことを確認します。

カスタムアクションを介して送信されたメッセージの場合、ジャーニーテストで確認できるのは、カスタムアクションのシステムを呼び出すことでエラーが発生するかどうかだけです。カスタムアクションに関連付けられた外部システムへの呼び出しがエラーにならず、それでもメッセージが送信されない場合は、外部システム側で調査する必要があります。
