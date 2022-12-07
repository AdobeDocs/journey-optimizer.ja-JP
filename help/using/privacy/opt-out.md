---
solution: Journey Optimizer
product: journey optimizer
title: オプトアウトの管理
description: オプトアウトとプライバシーを管理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 74%

---

# オプトアウトの管理 {#consent}

## オプトアウト管理について {#about}

ブランドからの連絡を購読解除する機能を受信者に提供することは、法的要件です。適用される法律について詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target=&quot;_blank&quot;}を参照してください。

**なぜそれが重要なのでしょうか？**

* これらの規制に準拠できないと、ブランドに法規制上のリスクが生じます。
* この機能を使用すると、未承諾の通信を受信者に送信して、メッセージがスパムと見なされたり、ブランドの評判が損なわれたりする危険性を避けることができます。

## Journey Optimizerでのオプトアウト管理 {#opt-out-ajo}

ジャーニーやキャンペーンからメッセージを送信する場合は、顧客が今後のコミュニケーションを購読解除できるようにする必要があります。 登録解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。

While **[!DNL Journey Optimizer]** は、電子メールや SMS メッセージのオプトアウトを管理する方法を提供します。受信者は自分でデバイスを介して登録を解除できるので、お客様側でのアクションは不要です。 例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。同様に、モバイルオペレーティングシステムから通知設定を変更することもできます。

Journey Optimizerの E メールおよび SMS メッセージのオプトアウトを管理する方法については、次の節を参照してください。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../email/email-opt-out.md">
<img alt="リード" src="../assets/do-not-localize/privacy-email-optout.jpeg" width="50%&gt;
&lt;/a&gt;
&lt;div&gt;&lt;a href=" ../email/email-opt-out.md"><strong>電子メールのオプトアウト管理</strong>
</div>
<p>
</td>
<td>
<a href="../sms/sms-opt-out.md">
<img alt="低頻度" src="../assets/do-not-localize/privacy-sms-opt-out.jpeg" width="50%&gt;
&lt;/a&gt;
&lt;div&gt;
&lt;a href=" ../sms/sms-opt-out.md"><strong>SMS オプトアウト管理</strong></a>
</div>
<p></td>
</tr></table>

>[!NOTE]
>
>[!DNL Journey Optimizer] の場合、同意は Experience Platform [同意スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja)で処理されます{target=&quot;_blank&quot;}。デフォルトでは同意フィールドの値は空で、通信内容の受信に対する同意として扱われます。このデフォルト値は、[ここ](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values)に一覧表示されている値の 1 つにオンボーディングする際に変更できます{target=&quot;_blank&quot;}。