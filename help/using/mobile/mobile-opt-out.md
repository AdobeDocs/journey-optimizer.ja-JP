---
solution: Journey Optimizer
product: journey optimizer
title: モバイルメッセージのオプトアウト管理
description: SMS/RCS/MMS メッセージによるオプトアウトを管理する方法について説明します
feature: SMS
topic: Content Management
role: User
level: Intermediate
exl-id: 59ea67d9-e90c-4ad0-afb9-d0e0fd868855
TQID: https://experienceleague.adobe.com/mQVaZ8jb-hBBPxDnztkayDEI4vj0KvMTREI0KxOgAf0
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: b3b09fe1-10f1-4793-9f6b-1ca0269eebe7id: a9cf78bf-e9e4-4836-85a5-b6b3cf93bf56
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 674
ht-degree: 80%

---

# モバイルメッセージのオプトアウト管理 {#sms-opt-out}

業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。 [プライバシーおよびオプトアウト管理についての詳細情報](../privacy/opt-out.md)

>[!IMPORTANT]
>
>モバイルメッセージコミュニケーションは、その性質、モバイルメッセージを送信する場所、受信者の場所に応じて、さまざまな法的コンプライアンス要件の対象となる場合があります。 Adobe Journey Optimizerでは、ショートコード、ロングコード、フリーダイヤル番号に関するメッセージを次の詳細に従って処理しますが、弁護士に相談して、モバイルメッセージが適用されるすべての法的コンプライアンス要件に準拠していることを確認してください。
>

## ネイティブ受信キーワード {#sms-native-keywords}

>[!NOTE]
>
> Journey Optimizer で使用する場合、ネイティブキーワードをサポートするのは Sinch と Infobip のみです。

デフォルトでは、Adobe Journey Optimizer はショートコード、フリーダイヤルおよびロングコードメッセージに対して、次の標準の英語の返信メッセージを処理します。

* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **ヘルプ**：HELP

これらのキーワードは通常、お使いのサードパーティプロバイダーから提供される自動標準返信をトリガーします。 これについては、プロバイダーまたはドキュメントサイトで直接確認してください。

Infobip を使用する場合は、転送アクションがプル設定に指定されていることを確認してください。

キーワード応答の STOP、UNSTOP、START、QUIT、CANCEL、END および UNSUBSCRIBE が自動的に認識されるので、Adobe Journey Optimizer で SMS オプトアウト機能が機能していることを確認する手順は不要です。 プロファイルのオプトアウトステータスは、Adobe Journey Optimizer でリアルタイムに更新されます。

SMS API 資格情報でカスタムのオプトアウトキーワードを定義すると、上記のデフォルトのインバウンドキーワードが上書きされます。 STOP、QUIT、CANCEL、END、UNSUBSCRIBE など、デフォルトのキーワードが機能するように保持するには、カスタムのキーワードと共に、SMS 設定の「オプトアウトキーワード」フィールドに明示的に含めます。 それ以外の場合は、カスタムのキーワードのみが認識され、デフォルトのキーワードではオプトアウトアクションがトリガーされなくなります。

顧客がモバイルメッセージに対してSTOPを応答した場合、プロバイダーは、トランザクションメッセージを含む、その特定の送信者ID （ショートコードまたは長い番号）からの後続のすべてのSMSをブロックすることに注意してください。 トランザクション SMS の配信が中断されないようにするには、以前にオプトアウトされていない別の送信者 ID を使用します。


>[!NOTE]
>
>双方向 SMS（STOP、QUIT などで返信）を使用する予定の場合は、電話番号とプロファイルのマッピングを確立するために、まず 1 つ以上の一方向 SMS を送信していることを確認します。 プロバイダーの資格情報の有効期限が切れているか、正しく設定されていない場合、受信キーワードによるユーザープロファイルの更新が妨げられ、その結果、オプトアウトレコードが欠落または遅延します。 インバウンド応答は、_AJO Inbound Activity Event Dataset_ システム データセットに保存されます。 [詳細情報](../data/get-started-datasets.md#system-datasets)


## ブロックリスト {#sms-blocklists}

Adobe Journey Optimizer 側でオプトアウトステータスに基づいて送信を停止する（Twilio、Infobip または Sinch との直接統合の場合）だけでなく、ほとんどの SMS ゲートウェイプロバイダーもブロックリストを管理し、オプトアウトを選択した個人に SMS メッセージが配信されないようにしています。 Sinch または Twilio 以外のプロバイダーを使用していて、[カスタムチャネル](../building-journeys/using-custom-actions.md)経由で SMS を送信している場合は、この点をプロバイダーに確認する必要があります。


## ショートコード {#short-codes}

デフォルトでは、ショートコード番号のオプトインまたはヘルプキーワードは、Adobe Journey Optimizer では処理しません。 オプトアウト処理に関する業界の規制とルールに確実に準拠するには、ショートコードがすべてのガイドラインに準拠していることを確認することが重要です。

ただし、Journey Optimizer では、様々な送信者 ID を持つ受信キーワードに基づくグローバルなオプトアウトをサポートします。

## 英数字の送信者 ID {#alphanumeric}

英数字の送信者 ID は一方向メッセージ専用であり、受信メッセージを受信できません。 その結果、Adobe Journey Optimizer の SMS STOP、START、HELP のキーワードは、アルファ送信者 ID には適用されません。 英数字の送信者 ID を介して送信されたメッセージをオプトアウトできるようにするために、サポートチームに手紙を書く、サポートの電話回線に電話する、または別の電話番号またはコードをテキストメッセージで送信するなど、他の手順を指定する必要があります。

## ビデオ {#video-sms}

* 次のビデオは、SMS のダブルオプトインを設定する方法を学ぶのに役立ちます。

  +++ こちらのビデオをご覧ください

  >[!VIDEO](https://video.tv.adobe.com/v/3427129/?learn=on)

  +++
