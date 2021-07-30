---
title: 抑制リスト
description: 抑制リストの内容、目的、および含まれる内容について説明します。
feature: 配信品質
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 100%

---

# 抑制リスト {#suppression-list}

抑制リストは、これらのメールアドレスに送信すると、送信者の評判や配信率が低下する可能性があるなどの理由により、配信から除外するメールアドレスで構成されます。

[!DNL Journey Optimizer] 抑制リストは、独自の環境レベルで管理されます。

単一のクライアント環境（サンドボックス ID に関連付けられた IMS 組織 ID に固有の環境）で、すべてのメーリングをまたいで抑制されるメールアドレスとドメインを収集します。

<!--It gathers spam complaints, hard bounces, and soft bounces that occur consistently.-->

## 抑制リストを使用する理由 {#why-suppression-list}

インボックスの所有者が受信するメールメッセージを制御し、希望するメッセージだけを受信できるようにするために、インターネットサービスプロバイダー（ISP）と商用スパムフィルターは、メール送信者が使用する IP アドレスと送信ドメインに基づいて、メール送信者の全体的な評判を追跡する独自のアルゴリズムを持っています。

フィードバック（スパムの苦情やバウンスなど）を考慮しなければ、評価が下がります。抑制リストは、ISP のフィードバックを尊重するのに役立ちます。

メールアドレスが抑制されている受信者は、メッセージ配信から自動的に除外されます。エラー率は配信速度に大きな影響を与えるため、こうすることで配信が迅速になります。

## 抑制リストには何が含まれますか？  {#what-s-on-suppression-list}

メールアドレスは、次のように抑制リストに追加されます。

* すべての&#x200B;**ハードバウンス**&#x200B;および&#x200B;**スパム通報**&#x200B;は、1 回発生した後、対応するメールアドレスを抑制リストに自動的に送信します。

* **ソフトバウンス**&#x200B;や一時的に&#x200B;**無視**&#x200B;されたエラーでは、直ちにメールアドレスが抑制リストに送られることはありませんが、エラーカウンターが増加します。その後、再試行が複数回実行され、エラーカウンターがしきい値に達すると、アドレスが抑制リストに追加されます。 詳しくは、[再試行](configuration/retries.md)を参照してください。

<!--You can also manually add an address to the suppression list. Manual category will be available when ability to manually add an address to the suppression list (via API) is released.-->

>[!NOTE]
>
>購読を解除したユーザーのアドレスは、[!DNL Journey Optimizer] からのメールを受信していないので、抑制リストに送信できません。選択は、Experience Platform レベルで処理されます。詳しくは、[オプトアウト](../using/consent.md)を参照してください。
<!--Email addresses of recipients who **unsubscribe** from your sendings are NOT sent to the suppression list. Confirmed by eng.: "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

各アドレスについて、抑制される基本的な理由と抑制カテゴリ（ソフト、ハードなど） が抑制リストに表示されます。 抑制リストへのアクセスと管理について詳しくは、[この節](configuration/manage-suppression-list.md)を参照してください。

<!--Once a message is sent, the message logs allow you to view the delivery status for each recipient and the associated failure type and reason. [Learn more about monitoring message execution](monitoring.md). NO ACCESS TO LOGS YET-->

### 配信エラー {#delivery-failures}

配信が失敗したときのエラーには次の 3 つのタイプがあります。

* **ハードバウンス**.ハードバウンスは、無効な メールアドレス（存在しないメールアドレスなど）を示します。これには、「不明なユーザー」など、アドレスが無効であることを明示的に示す受信側のメールサーバーからのバウンスメッセージが含まれます。
* **ソフトバウンス**。これは、有効なメールアドレスに対して発生した一時的なメールバウンスです。
* **無視**。有効なメールアドレスに対して発生し、接続試行の失敗、一時的なスパム関連の問題（メールの評判）、一時的かつ技術的な問題など、一時的なものであることがわかっているメールのバウンスです。<!--does it exist in CJM?-->

**ハードバウンス**&#x200B;は、メールアドレスを抑制リストに自動的に追加します。

何度も繰り返し再試行した後に、**ソフトバウンス**&#x200B;または&#x200B;**無視**&#x200B;されたエラーが何度も発生し、そのメールアドレスは抑制リストに送信されます。[再試行の詳細情報](configuration/retries.md)

これらのアドレスへの送信を継続すると、メールアドレスリストのメンテナンスのベストプラクティスに従っていない可能性があるため、信頼できる送信者ではない可能性があると ISP に認識され、配信率に影響が及ぶ可能性があります。

### スパムの苦情数 {#spam-complaints}

抑制リストは、こちらから送信したメッセージをスパムとしてマークするメールアドレスを収集します。例えば、メールを二度と受け取りたくないという要望がカスタマーサービスに寄せられた場合、そのユーザーのメールアドレスはインスタンス全体で抑制され、そのアドレスに配信できなくなります。

受信者がスパムとして通報した後に受信者に送信すると、望まないメールを送信している、または受信者の意見に耳を傾けないといった報告が ISP に寄せられ、送信の評価に大きな影響を与える可能性があります。

これによって、IP アドレスや送信ドメインがブロックされる可能性がありますが、これらのアドレスが抑制リストに入っていれば、この状況を回避できます。

<!--### Unsubscriptions {#unsubscriptions}

Every email sent to recipients must include an unsubscribe link. Upon clicking this link, if a recipient confirms [opting out](consent.md), the corresponding email address is immediately sent to the suppression list. This user must not receive communication from your brand until subscribed again.
NOT TRUE > "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

<!--MOVED to Configuration/Retries section

The threshold is set at three errors:
* For the same delivery, at the third attempt, the address is suppressed.
* If there are different deliveries and two errors occur at least 24 hours apart, the error counter is incremented upon each error and the address is also suppressed at the third attempt.
When a delivery is successful after a retry, the error counter of the address is reinitialized.

### Retries {#retries}

If a message fails due to a temporary bounce of the **Ignored** type, retries will be performed for **3.5 days** from the time the message was added to the email queue.

The minimum delay between retries and the maximum number of retries to be performed are ///managed by the Enhanced MTA/// based on how well an IP is performing, both historically and currently at a given domain.

After 3.5 days, any message in the retry queue will be removed from the queue and sent back as a bounce.-->
