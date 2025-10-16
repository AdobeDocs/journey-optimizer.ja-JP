---
solution: Journey Optimizer
product: journey optimizer
title: テキストメッセージのオプトアウト管理
description: SMS／MMS メッセージを使用してオプトアウトを管理する方法を学ぶ
feature: SMS
topic: Content Management
role: User
level: Intermediate
exl-id: 59ea67d9-e90c-4ad0-afb9-d0e0fd868855
source-git-commit: 7b1be144776fd11cd4aa90aa315eee60b1acc40f
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 88%

---

# テキストメッセージのオプトアウト管理 {#sms-opt-out}

業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。[プライバシーおよびオプトアウト管理についての詳細情報](../privacy/opt-out.md)

>[!IMPORTANT]
>
>テキストメッセージ通信は、性質、テキストメッセージの送信元の場所および受信者の場所に応じて、様々な法的遵守要件の対象となる可能性があります。 Adobe Journey Optimizerでは、以下に説明するようにショートコード、ロングコードおよびフリーダイヤル番号でのメッセージを処理しますが、適用されるすべての法的順守要件にテキストメッセージ通信が準拠していることを確認するには、法務担当者に相談する必要があります。
>

## ネイティブ受信キーワード {#sms-native-keywords}

>[!NOTE]
>
> Journey Optimizer で使用する場合、ネイティブキーワードをサポートするのは Sinch と Infobip のみです。

デフォルトでは、Adobe Journey Optimizer はショートコード、フリーダイヤルおよびロングコードメッセージに対して、次の標準の英語の返信メッセージを処理します。

* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **ヘルプ**：HELP

これらのキーワードは通常、お使いのサードパーティプロバイダーから提供される自動標準返信をトリガーします。これについては、プロバイダーまたはドキュメントサイトで直接確認してください。

Infobip を使用する場合は、転送アクションがプル設定に指定されていることを確認してください。

キーワード応答の STOP、UNSTOP、START、QUIT、CANCEL、END および UNSUBSCRIBE が自動的に認識されるので、Adobe Journey Optimizer で SMS オプトアウト機能が機能していることを確認する手順は不要です。プロファイルのオプトアウトステータスは、Adobe Journey Optimizer でリアルタイムに更新されます。

お客様がテキストメッセージに対して STOP と応答した場合、プロバイダーは、それ以降、その特定の送信者 ID（ショートコードまたは長い番号）からのすべての SMS （トランザクションメッセージを含む）をブロックします。トランザクション SMS の配信が中断されないようにするには、以前にオプトアウトされていない別の送信者 ID を使用します。


>[!NOTE]
>
>双方向 SMS（STOP、QUIT などで返信）を使用する予定の場合は、電話番号とプロファイルのマッピングを確立するために、まず 1 つ以上の一方向 SMS を送信していることを確認します。プロバイダーの資格情報の有効期限が切れているか、正しく設定されていない場合、受信キーワードによるユーザープロファイルの更新が妨げられ、その結果、オプトアウトレコードが欠落または遅延します。


## ブロックリスト {#sms-blocklists}

Adobe Journey Optimizer 側でオプトアウトステータスに基づいて送信を停止する（Twilio、Infobip または Sinch との直接統合の場合）だけでなく、ほとんどの SMS ゲートウェイプロバイダーもブロックリストを管理し、オプトアウトを選択した個人に SMS メッセージが配信されないようにしています。Sinch または Twilio 以外のプロバイダーを使用していて、[カスタムチャネル](../building-journeys/using-custom-actions.md)経由で SMS を送信している場合は、この点をプロバイダーに確認する必要があります。


## ショートコード {#short-codes}

デフォルトでは、ショートコード番号のオプトインまたはヘルプキーワードは、Adobe Journey Optimizer では処理しません。オプトアウト処理に関する業界の規制とルールに確実に準拠するには、ショートコードがすべてのガイドラインに準拠していることを確認することが重要です。

ただし、Journey Optimizer では、様々な送信者 ID を持つ受信キーワードに基づくグローバルなオプトアウトをサポートします。

## 英数字の送信者 ID {#alphanumeric}

英数字の送信者 ID は一方向メッセージ専用であり、受信メッセージを受信できません。その結果、Adobe Journey Optimizer の SMS STOP、START、HELP のキーワードは、アルファ送信者 ID には適用されません。英数字の送信者 ID を介して送信されたメッセージをオプトアウトできるようにするために、サポートチームに手紙を書く、サポートの電話回線に電話する、または別の電話番号またはコードをテキストメッセージで送信するなど、他の手順を指定する必要があります。

## ビデオ {#video-sms}

* 次のビデオは、SMS のダブルオプトインを設定する方法を学ぶのに役立ちます。

  +++ こちらのビデオをご覧ください

  >[!VIDEO](https://video.tv.adobe.com/v/3427129/?learn=on)

  +++
