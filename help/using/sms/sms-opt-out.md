---
solution: Journey Optimizer
product: journey optimizer
title: SMS オプトアウトの管理
description: SMS メッセージのオプトアウトを管理する方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 59ea67d9-e90c-4ad0-afb9-d0e0fd868855
source-git-commit: 676e2d6788c8110b76a38e857a62ba9c1be5842c
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 48%

---

# SMS オプトアウトの管理 {#sms-opt-out}

業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。詳しくは、[オプトアウトの管理](../privacy/opt-out.md)を参照してください。

>[!IMPORTANT]
>
>テキストメッセージの通信は、その性質、テキストメッセージの送信元、受信者の場所に応じて、様々な法的遵守要件に従う場合があります。 Adobe Journey Optimizerでは長いコードとフリーダイヤルのメッセージを以下に示すように処理しますが、法務担当者に相談して、テキストメッセージの通信が適用される法律上の要件をすべて満たしていることを確認してください。

## ネイティブインバウンドキーワード{#sms-native-keywords}

デフォルトでは、Adobe Journey Optimizer は、Sinch や Twilio などのネイティブ統合の業界標準に従って、フリーダイヤルメッセージとロングコードメッセージの STOP、UNSTOP、START などの標準の英語の返信メッセージを処理します。

これらのキーワードは通常、サードパーティプロバイダー（Twilio や Sinch など）からの自動標準返信をトリガーします。 これは、プロバイダーまたはドキュメントサイトで直接確認できます。

Adobe Journey Optimizerで SMS オプトアウト機能が機能していることを確認する手順は不要です。応答の STOP、UNSTOP および START が自動的に認識されるからです。 プロファイルのオプトアウトステータスは、Adobe Journey Optimizerでリアルタイムに更新されます。


## ブロックリスト{#sms-blocklists}

Adobe Journey Optimizerは、オプトアウトステータス（Twilio または Sinch との直接統合の場合）に基づいて送信を停止するだけでなく、ほとんどの SMS ゲートウェイプロバイダーブロックリストも、オプトアウトを選択した個人に SMS メッセージが配信されないようにするを保持します。 Sinch または Twilio 以外のプロバイダーを使用し、経由で SMS を送信する場合 [カスタムチャネル](../building-journeys/using-custom-actions.md)を使用する場合は、プロバイダーに確認する必要があります。


## ショートコード {#short-codes}

デフォルトでは、Adobe Journey Optimizerはショートコード番号のオプトアウト、オプトイン、ヘルプのキーワードは処理しません。 ショートコードが、オプトアウト処理に関するすべての業界ルールおよび規制に準拠していることを確認する必要があります。

## 英数字の送信者 ID {#alphanumeric}

英数字の送信者 ID は一方向メッセージ専用であり、受信メッセージを受信できません。その結果、Adobe Journey Optimizer の SMS STOP、START、HELP のキーワードは、アルファ送信者 ID には適用されません。英数字の送信者 ID を介して送信されたメッセージをオプトアウトできるようにするために、サポートチームに手紙を書く、サポートの電話回線に電話する、または別の電話番号またはコードをテキストメッセージで送信するなど、他の手順を指定する必要があります。

## ビデオ {#video-sms}

SMS に対するネイティブ受信キーワードのサポート（START、STOP、UNSTOP）の仕組みについて詳しくは、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)
