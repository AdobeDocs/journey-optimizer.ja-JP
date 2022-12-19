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
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 100%

---

# SMS オプトアウトの管理 {#sms-opt-out}

業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。詳しくは、[オプトアウトの管理](../privacy/opt-out.md)を参照してください。

デフォルトでは、Adobe Journey Optimizer は、Sinch や Twilio などのネイティブ統合の業界標準に従って、フリーダイヤルメッセージとロングコードメッセージの STOP、UNSTOP、START などの標準の英語の返信メッセージを処理します。これらのキーワードは、通常、サードパーティプロバイダー（Twilio、Sinch など）からの自動標準返信をトリガーします。これは、プロバイダーまたはドキュメントサイトで直接確認できます。

キーワード応答の STOP、UNSTOP および START が自動的に認識されるので、Adobe Journey Optimizer で SMS オプトアウト機能が機能していることを確認する手順は不要です。

オプトアウトステータスに基づいて送信を停止する Adobe Journey Optimizer に加えて（Twilio または Sinch との直接統合の場合）、ほとんどの SMS ゲートウェイプロバイダーはブロックリストも維持しており、オプトアウトを選択した個人に SMS メッセージが配信されないようにします。Sinch または Twilio 以外のプロバイダーを使用していて、[カスタムチャネル](../building-journeys/using-custom-actions.md)経由で SMS を送信している場合は、プロバイダーに確認する必要があります。

>[!IMPORTANT]
>
>テキストメッセージキャンペーンは、テキストメッセージキャンペーンの性質、テキストメッセージの送信元の場所、受信者の場所に応じて、様々な法的順守要件の対象となる場合があります。<br>上記のように、Adobe Journey Optimizer はロングコードとフリーダイヤル番号のメッセージを処理しますが、テキストメッセージキャンペーンが適用されるすべての法的順守要件に準拠していることを確認するには、法務担当者に相談する必要があります。

## ショートコード {#short-codes}

デフォルトでは、Adobe Journey Optimizer はショートコード番号のオプトアウト、オプトイン、ヘルプのキーワードを処理しません。

ショートコードが、オプトアウト処理に関するすべての業界ルールおよび規制に準拠していることを確認する必要があります。

## 英数字の送信者 ID {#alphanumeric}

英数字の送信者 ID は一方向メッセージ専用であり、受信メッセージを受信できません。その結果、Adobe Journey Optimizer の SMS STOP、START、HELP のキーワードは、アルファ送信者 ID には適用されません。英数字の送信者 ID を介して送信されたメッセージをオプトアウトできるようにするために、サポートチームに手紙を書く、サポートの電話回線に電話する、または別の電話番号またはコードをテキストメッセージで送信するなど、他の手順を指定する必要があります。

## ビデオ {#video-sms}

SMS に対するネイティブ受信キーワードのサポート（START、STOP、UNSTOP）の仕組みについて詳しくは、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)
