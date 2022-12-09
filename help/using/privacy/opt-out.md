---
solution: Journey Optimizer
product: journey optimizer
title: オプトアウトの管理
description: オプトインおよびプライバシーの管理方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# オプトアウトの管理 {#consent}

## オプトアウトの管理について {#about}

ブランドからの配信を受信中止するために受信者に送信する機能を提供することは、法律上の要件です。 経験プラットフォームのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations) に記載 [ されている法律について詳しくは、target = &quot;_blank&quot;} を参照してください。

**これはなぜ重要なのですか?**

* このような規制に準拠していない場合、法律上の法律上のリスクが発生します。
* これにより、一方的な通信が宛先に送信されるのを防ぐことができます。これにより、受信者は受信したメッセージをスパムとし、評判に害を及ぼすことができます。

## このようなオプトアウトの管理が、旅オプティマイザーによって {#opt-out-ajo}

Journeys またはキャンペーンからメッセージを送信する場合は、常に顧客が今後のコミュニケーションについて購読を中止できるようにする必要があります。 取り消されたプロファイルは、今後のマーケティングメッセージの対象者から自動的に削除されます。

**[!DNL Journey Optimizer]**&#x200B;電子メールや SMS メッセージでオプトアウトを管理する方法が用意されていますが、プッシュ通知を使用すると、受信者がデバイス自身で購読を行うことができないので、ユーザー側では操作を行う必要はありません。例えば、をダウンロードしたり、アプリケーションを使用している場合は、通知を停止するように選択することもできます。 同様に、モバイルオペレーティングシステムを使用して通知設定を変更することもできます。

以下のセクションで、旅オプティマイザーの電子メールや SMS メッセージのオプトアウトを管理する方法について説明します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../email/email-opt-out.md">
<img alt="招き" src="../assets/do-not-localize/privacy-email-optout.jpeg" width="50%&gt;
&lt;/a&gt;
&lt;div&gt;&lt;a href=" ../email/email-opt-out.md"><strong>電子メールのオプトアウト管理</strong>
</div>
<p>
</td>
<td>
<a href="../sms/sms-opt-out.md">
<img alt="ときどき" src="../assets/do-not-localize/privacy-sms-opt-out.jpeg" width="50%&gt;
&lt;/a&gt;
&lt;div&gt;
&lt;a href=" ../sms/sms-opt-out.md"><strong>SMS オプトアウト管理</strong></a>
</div>
<p></td>
</tr></table>

>[!NOTE]
>
>で [!DNL Journey Optimizer] は、同意はプラットフォーム [ の同意スキーマ ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html) {target = &quot;_blank&quot;} によって処理されます。 初期設定では、「同意」フィールドの値は空白なので、通信の受信には同意したものとして扱われます。 このデフォルト値を変更するには、次 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html#choice-values) のいずれかの値 [ をオンにします ({target = &quot;_blank&quot;})。