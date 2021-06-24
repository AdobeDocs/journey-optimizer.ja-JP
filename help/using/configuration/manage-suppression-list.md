---
title: 抑制リストの管理
description: 'Journey Optimizer 抑制リストにアクセスして管理する方法を学ぶ '
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 100%

---


# 抑制リストの管理 {#manage-suppression-list}

[!DNL Journey Optimizer] を使用すると、次のようにジャーニーでの送信から自動的に除外されるすべてのメールアドレスを監視できます。

* 無効なメールアドレス（ハードバウンス）、または一貫したソフトバウンスで、配信先に入れ続けるとメールの評判に悪影響を与える可能性があるメールアドレス。
* いずれかのメールメッセージに対して何らかのスパム報告を発行する受信者。

<!--Profiles who unsubscribe from your sendings. Learn more on [opting-out](../consent.md). NOT TRUE as confirmed by eng.: "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

このようなメールアドレスは、Journey Optimizer の&#x200B;**抑制リスト**&#x200B;に自動的に収集されます。詳しくは、[この節](../suppression-list.md)を参照してください。

## 抑制リストへのアクセス {#access-suppression-list}

除外されたメールアドレスの詳細なリストにアクセスするには、**[!UICONTROL チャネル]**／**[!UICONTROL E メール設定]**／**[!UICONTROL 一般]**&#x200B;メニューを開き、「**[!UICONTROL 抑制リストを表示]**」リンクをクリックします。

![](../assets/suppression-list-link.png)

リストの参照に役立つフィルターを使用できます。

![](../assets/suppression-list-filters.png)

<!--suppression date,  category and reason, but on staging, only creation date filter is available-->

<!--You can also download the list as a CSV file for analysis and reporting purpose. Won't be available.-->

## 抑制のカテゴリと理由 {#suppression-categories-and-reasons}

メッセージをメールアドレスに配信できない場合、Journey Optimizer は配信が失敗した理由を特定し、抑制カテゴリに関連付けます。

抑制のカテゴリは次のとおりです。

* **ハード**：メールアドレスは、即座に抑制リストに送信されます。

* **ソフト**：ソフトエラーは、エラーカウンターが制限しきい値に達すると、アドレスを抑制リストに送信します。[再試行の詳細情報](retries.md)

* **無視**：
   * 有効なメールアドレスに対してエラーが発生しても、接続の失敗や一時的な技術上の問題など、一時的であることがわかっている場合、エラーカウンターが制限しきい値に達すると、メールアドレスが抑制リストに追加されます。 [再試行の詳細情報](retries.md)。
   * エラーがスパム報告の結果として発生している場合、スパムを報告した受信者のメールアドレスが直ちに抑制リストに送信されます。

<!--**Manual**: You can also manually add an email address to the suppression list. => Manual category will be available when manually adding an address to the suppression list (via API)-->

>[!NOTE]
>
>ソフトバウンスとハードバウンスの詳細については、[配信エラーのタイプ](../suppression-list.md#delivery-failures)セクションを参照してください。

表示される各メールアドレスについて、**[!UICONTROL 理由]** をチェックして除外し、抑制リストに追加された日時を確認することもできます。

![](../assets/suppression-list-temp.png)
<!--to replace with suppression-list.png when Manual category is available (through API)-->

配信エラーの理由として考えられるものを以下に示します。

| 理由 | 説明 | 抑制カテゴリ |
---------|----------|--------- |
| **[!UICONTROL 未確定]** | 受信者ドメインメッセージ転送エージェント（MTA）から受け取ったバウンスの理由を識別できませんでした。 | 無視 |
| **[!UICONTROL 無効な受信者]** | 受信者が無効、または存在しません。 | ハード |
| **[!UICONTROL ソフトバウンス]** | メッセージソフトは、この表に示すソフトエラー以外の理由（ISP が推奨する許可率を超えた場合など）でバウンスしました。 | ソフト |
| **[!UICONTROL DNS エラー]** | DNS エラーが原因でメッセージがバウンスされました。 | ソフト |
| **[!UICONTROL メールボックス容量超過]** | 受信者のメールボックスがいっぱいになり、追加のメッセージを受け入れられなかったため、メッセージがバウンスされました。 | ソフト |
| **[!UICONTROL 大きすぎる]** | 受信者に対して大きすぎるため、メッセージがバウンスされました。 [再試行](retries.md) が実行されます。メッセージサイズを編集し、配信用に再挿入できます。 | 無視 |
| **[!UICONTROL タイムアウト]** | メッセージがタイムアウトしてソフトバウンスされ、メッセージの再試行制限（3.5日）に到達しました。 | 無視 |
| **[!UICONTROL 管理エラー]** | 送信側のシステム管理者が設定したポリシーに従って、メッセージが失敗しました。<!--For example, if emails are blackholed at the global, domain or binding level using the "blackhole" directive, this bounce code is used.--> | 無視 |
| **[!UICONTROL 一般的なバウンス：RCPT なし]** | メッセージの受信者を特定できませんでした。 | 無視 |
| **[!UICONTROL 一般的なバウンス]** | メッセージは、不特定の理由で失敗しました。 | 無視 |
| **[!UICONTROL メールブロック]** | メッセージが受信者（受信者 MTA など）によってブロックされました。 | 無視 |
| **[!UICONTROL スパムブロック]** | メッセージは、既知のスパム送信元から送信されたものとして受信者にブロックされました。 例えば、送信元 IP ブロックを指定できます。 | 無視 |
| **[!UICONTROL スパムコンテンツ]** | メッセージの内容が受信者（受信者MTA）にスパムとしてブロックされました。 | 無視 |
| **[!UICONTROL 禁止された添付ファイル]** | メッセージに添付ファイルが含まれているため、受信者によってブロックされました。 | 無視 |
| **[!UICONTROL リレー拒否]** | リレーが許可されていないため、受信者によってメッセージがブロックされました。 | ソフト |
| **[!UICONTROL 自動応答]** | メッセージは自動返信／休暇メールです。 | 無視 |
| **[!UICONTROL 一時的なエラー]** | メッセージの送信が一時的に遅れました。 | 無視 |
| **[!UICONTROL チャレンジレスポンス]** | このメッセージはチャレンジレスポンスプローブです。 | ソフト |

>[!NOTE]
>
>購読を解除したユーザーは [!DNL Journey Optimizer] からのメールを受信しないので、そのメールアドレスを抑制リストに送信することはできません。 選択は、Experience Platform レベルで処理されます。詳しくは、[オプトアウト](../consent.md)を参照してください。

<!--
Removed from the table provided by SparkPost/Momentum:
| **[!UICONTROL Subscribe]** | The message is a subscribe request. | Ignored |
| **[!UICONTROL Unsubscribe]** | The message is an unsubscribe request. | Hard |
-->

<!--Note to add eventually: If a user is subscribed and [!DNL Journey Optimizer] fails to send emails to their subscribed email address, they will get added to the suppression list. (not sure it's possible to subscribe through AJO or need to find reference to Experience Platform doc?)-->


