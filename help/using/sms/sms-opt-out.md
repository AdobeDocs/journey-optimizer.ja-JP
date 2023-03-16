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
source-git-commit: 63237c02f632d289dba845acdcd0859f2d6de9c9
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 69%

---

# SMS オプトアウトの管理 {#sms-opt-out}

業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。詳しくは、[オプトアウトの管理](../privacy/opt-out.md)を参照してください。

>[!IMPORTANT]
>
>テキストメッセージ通信は、性質、テキストメッセージの送信元の場所および受信者の場所に応じて、様々な法的遵守要件の対象となる可能性があります。下記のように、Adobe Journey Optimizer ではロングコードやフリーダイヤル番号でのメッセージを処理しますが、適用されるすべての法的遵守要件にテキストメッセージ通信が準拠していることを確認するには、法務担当者に相談する必要があります。

## ネイティブ受信キーワード{#sms-native-keywords}

デフォルトでは、Adobe Journey Optimizerはフリーダイヤルおよびロングコードメッセージに対して、次の標準の英語の返信メッセージを処理します。停止、停止、開始、終了、キャンセル、終了、配信停止。 Journey Optimizerで使用する場合、Sinch ではネイティブキーワードのみがサポートされます。

これらのキーワードは、通常、サードパーティプロバイダーからの自動標準返信をトリガーします。 これについては、プロバイダーまたはドキュメントサイトで直接確認してください。

STOP、UNSTOP、START、QUIT、CANCEL、END、UNSUBSCRIBE の各キーワード応答が自動的に認識されるので、Adobe Journey Optimizerで SMS オプトアウト機能が動作するようにする手順は必要ありません。 プロファイルのオプトアウトステータスは、Adobe Journey Optimizer でリアルタイムに更新されます。


## ブロックリスト{#sms-blocklists}

Adobe Journey Optimizer 側でオプトアウトステータスに基づいて送信を停止する（Twilio や Sinch との直接統合の場合）だけでなく、ほとんどの SMS ゲートウェイプロバイダーもブロックリストを維持管理しており、オプトアウトを選択した個人に SMS メッセージが配信されないようにしています。Sinch または Twilio 以外のプロバイダーを使用していて、[カスタムチャネル](../building-journeys/using-custom-actions.md)経由で SMS を送信している場合は、この点をプロバイダーに確認する必要があります。


## ショートコード {#short-codes}

デフォルトでは、ショートコード番号のオプトインまたはヘルプキーワードは、Adobe Journey Optimizerでは処理されません。 業界の規制やオプトアウト処理ルールへの準拠を確保するには、ショートコードがすべてのガイドラインに従っていることを確認する必要があります。

ただし、Journey Optimizerでは、異なる送信者 ID を持つ受信キーワードに基づくグローバルなオプトアウトをサポートしています。

## 英数字の送信者 ID {#alphanumeric}

英数字の送信者 ID は一方向メッセージ専用であり、受信メッセージを受信できません。その結果、Adobe Journey Optimizer の SMS STOP、START、HELP のキーワードは、アルファ送信者 ID には適用されません。英数字の送信者 ID を介して送信されたメッセージをオプトアウトできるようにするために、サポートチームに手紙を書く、サポートの電話回線に電話する、または別の電話番号またはコードをテキストメッセージで送信するなど、他の手順を指定する必要があります。

## ビデオ {#video-sms}

SMS に対するネイティブ受信キーワードのサポート（START、STOP、UNSTOP）の仕組みについて詳しくは、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)
