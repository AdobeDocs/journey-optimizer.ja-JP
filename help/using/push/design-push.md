---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知のデザイン
description: Journey Optimizerでプッシュ通知をデザインする方法を説明します
feature: Push
topic: Content Management
role: User
level: Beginner
exl-id: 6f6d693d-11f2-48b7-82a8-171829bf8045
TQID: https://experienceleague.adobe.com/YOE-hCnG978CvBHe2WeFekMjx4oBlsv4hBbSVaUjgWA
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 2122
ht-degree: 0%

---

# プッシュ通知のデザイン {#design-push-notification}

プッシュ通知を作成したら、そのコンテンツをiOS、Android、およびWeb プラットフォーム用にデザインできます。 このページでは、メッセージの作成、クリック時の動作の設定、メディアとボタンの追加、高度なオプションの設定を通じて、オーディエンスの共感を呼ぶ魅力的なプッシュ通知を作成する方法を説明します。

## タイトルと本文 {#push-title-body}

>[!CONTEXTUALHELP]
>id="ajo-message-push-compose"
>title="プッシュ通知のパーソナライズ。"
>abstract="メッセージを作成するには、**タイトル**&#x200B;および&#x200B;**本文** フィールドにコンテンツを入力します。 パーソナライゼーショントークンを含めるには、パーソナライゼーションダイアログを開きます。"

![](assets/title-body.png)

メッセージを作成するには、**[!UICONTROL タイトル]**&#x200B;および&#x200B;**[!UICONTROL 本文]** フィールドをクリックします。 パーソナライゼーションエディターを使用して、コンテンツを定義し、データをパーソナライズして、動的コンテンツを追加します。 [&#x200B; パーソナライゼーション &#x200B;](../personalization/personalize.md)と[動的コンテンツ &#x200B;](../personalization/get-started-dynamic-content.md)の詳細については、パーソナライゼーションエディターを参照してください。

デバイスプレビューセクションを使用して、iOS、Android、およびWebでのプッシュ通知の表示方法を視覚化します。

AI アシスタントを使用してコンテンツ制作を高速化し、テキスト生成用に[AI アシスタント &#x200B;](../content-management/generative-text.md)を使用して魅力的なプッシュ通知テキストを生成するか、完全なコンテンツ生成用に[AI アシスタント &#x200B;](../content-management/generative-full-content.md)を使用して完全なプッシュ通知を作成します。

## クリック時の動作 {#on-click-behavior}

>[!CONTEXTUALHELP]
>id="ajo-message-push-onclick"
>title="クリック時の動作について"
>abstract="受信者がプッシュ通知の本文をクリックしたときの動作を選択します。"

受信者がプッシュ通知の本文をタップしたときに発生するアクションを設定します。 次のオプションから選択します。

![](assets/title-body-push.png)

* **[!UICONTROL アプリを開く]**：通知に関連付けられているアプリケーションを起動します。 アプリは、[&#x200B; チャネル設定](../configuration/channel-surfaces.md) （メッセージプリセット）で指定されます。
* **[!UICONTROL ディープリンク]**：特定のビュー、ページセクション、タブなど、アプリ内の特定のコンテンツにユーザーを誘導します。 指定されたフィールドにディープリンク URLを入力します。
* **[!UICONTROL Web URL]**: ユーザーを外部Web ページに誘導します。 指定したフィールドに宛先URLを入力します。

  >[!NOTE]
  >
  >プッシュ通知に、iOSでユニバーサルリンクとして設定されたURLが含まれている場合、選択した&#x200B;**[!UICONTROL Web URL]** アクションに関係なく、インストールすると関連するアプリがプッシュで開きます。 ブラウザーを強制的に開くには、ユニバーサルリンク用に設定されていないドメインを使用するか、ドメインのユニバーサルリンク登録を削除します。
  >Adobe SDKでのディープリンクとユニバーサルリンクの処理方法について詳しくは、[Adobe Experience Platform モバイルSDK ドキュメント &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer/push-notifications){target="_blank"}を参照してください。

## メディアを追加 {#add-media-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-media"
>title="プッシュ通知にメディアを追加"
>abstract="通知内に表示される画像、ビデオ、GIFを追加できます。"

ビジュアルメディアを追加して、プッシュ通知を強化しましょう。 使用可能なメディアの種類と実装方法は、以下のタブで詳しく説明しているように、オペレーティングシステムによって異なります。

>[!BEGINTABS]

>[!TAB Android]

Androidの場合は、画像アイコンと、展開された通知用の画像のみを追加できます。

![](assets/push-config-add-media.png)

次のいずれかの方法を使用してメディアを追加できます。

* **[!UICONTROL Add media]** ボタン：[Adobe Experience Manager Assets](../integrations/assets.md)からアセットを選択するか、AI アシスタントにアクセスして、プッシュ通知用に[魅力的な画像](../content-management/generative-image.md)を生成します。

* **[!UICONTROL メディアを追加]** フィールド：メディア URLを直接入力します。 パーソナライゼーショントークンをURLに含めることができます。

追加すると、通知本文の右側にメディアが表示されます。

>[!NOTE]
>
>プッシュ通知ペイロードにメディアの添付ファイル（`adb_media`などのカスタムデータフィールドの画像など）を含める場合、モバイルアプリケーションは、デバイスでレンダリングする画像に対して特定のクライアントサイド処理を実装する必要があります。 ペイロードからの画像の添付ファイルを処理するには、アプリで[自動表示および追跡ワークフロー](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/push-notification/android/automatic-display-and-tracking){target="_blank"}を実装する必要があります。

>[!TAB iOS]

IOSの場合、通知内に表示する画像、ビデオ、GIFを追加できます。

![](assets/push-config-add-media-ios.png)

次のいずれかの方法を使用してメディアを追加できます。

* **[!UICONTROL メディアを追加]** ボタン：**[!DNL Adobe Experience Manager Assets]**&#x200B;からアセットを選択します。 **[!DNL Adobe Experience Manager Assets]**&#x200B;の使用について詳しくは、[このページ &#x200B;](../integrations/assets.md)を参照してください。

* **[!UICONTROL メディアを追加]** フィールド：メディア URLを直接入力します。 パーソナライゼーショントークンをURLに含めることができます。

追加すると、通知本文の右側にメディアが表示されます。

>[!NOTE]
>
>プッシュ通知ペイロードにメディアの添付ファイル（`adb_media`などのカスタムデータフィールドの画像など）を含める場合、モバイルアプリケーションは、デバイスでレンダリングする画像に対して特定のクライアントサイド処理を実装する必要があります。 ペイロードからメディアコンテンツをダウンロードして処理するには、アプリで[通知サービス拡張機能](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications){target="_blank"}を実装する必要があります。 さらに、[詳細オプション &#x200B;](#advanced-options-push) セクションで、**[!UICONTROL 可変コンテンツフラグを追加]** オプションを有効にする必要があります。

>[!TAB Web]

「**[!UICONTROL メディアを追加]**」フィールドにメディア URLを入力します。 また、URLにパーソナライゼーショントークンを含めて、各ユーザーのコンテンツをカスタマイズすることもできます。

「![AI アシスタントを使用してテキストを編集](assets/do-not-localize/Smock_ImageAdd_18_N.svg)」をクリックすると、Journey Optimizer AI アシスタントを使用してメディアをすばやく生成できます。

![](assets/web-media.png)

>[!ENDTABS]

## ボタンを追加 {#add-buttons-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-buttons"
>title="ユーザーがプッシュ通知を操作するためのボタンを追加します。"
>abstract="このセクションから、call-to-action ボタンをメッセージに追加します。 Apple iOSの場合は、通知カテゴリ IDを指定します。 Google Androidの場合は、各ボタンにカスタムテキストとターゲットを含めることができます。"

プッシュコンテンツにボタンを追加して、アクションにつながる通知を作成。 オペレーティングシステムに応じて、以下のタブを参照してください。

デバイス画面がロックされている場合、これらのボタンは表示されません。通知の&#x200B;**タイトル**&#x200B;と&#x200B;**メッセージ**&#x200B;のみが表示されます。 デバイスのロックが解除されている場合、受信者にはボタンが表示されます。

>[!BEGINTABS]

>[!TAB Android]

Androidの場合は、最大3つのボタンを追加できます。

1. 「**[!UICONTROL 追加」ボタン]**&#x200B;を使用して、ラベルと関連するアクションの設定を定義します。 考えられるアクションは、[&#x200B; クリック時の動作](#on-click-behavior)と同じです。

   ![](assets/push_buttons.png)

1. 中央のプレビュー画像の下にある「**[!UICONTROL ビューを展開]**」アイコンを使用して、パーソナライズされたボタンをプレビューします。

>[!TAB iOS]

![](assets/push_buttons-ios.png)

IOSの場合、通知カテゴリ IDが指定されます。 通知カテゴリは、表示するボタンと実行されるアクションを定義するiOS アプリで事前設定する必要があります。 詳しくは、[Apple ドキュメント &#x200B;](https://developer.apple.com/documentation/usernotifications/declaring_your_actionable_notification_types)を参照してください。

>[!TAB Web]

![](assets/push_buttons-web.png)

各ボタンのラベルと関連アクションを定義するには、**[!UICONTROL ボタンを追加]** オプションを使用します。詳細は次のとおりです。

* **[!UICONTROL 詳細]**: アプリ内の特定のビュー、セクション、またはタブにユーザーをリダイレクトします。 関連するフィールドにディープリンク URLを入力します。

* **[!UICONTROL Web URL]**: ユーザーを外部Web ページにリダイレクトします。 関連付けられたフィールドにURLを入力します。

>[!ENDTABS]

## サイレント通知を送信 {#silent-notification}

>[!CONTEXTUALHELP]
>id="ajo_message_push_silent_notification"
>title="サイレント通知について"
>abstract="ユーザーに影響を与えずに通知を送信すると、通知センターまたは通知バーに通知が表示されません。"

>[!AVAILABILITY]
>
>Journey OptimizerのWeb プッシュ通知は、**サイレント通知**&#x200B;機能をサポートしていません。

サイレントプッシュ通知（またはバックグラウンド通知）は、アプリケーションに配信される非表示の指示です。 例えば、新しいコンテンツの可用性についてアプリケーションに通知したり、バックグラウンドでダウンロードを開始したりするために使用されます。

「**[!UICONTROL サイレント通知]**」オプションを選択して、アプリケーションにサイレント通知を送信します。この場合、通知はアプリケーションに直接転送されます。 デバイス画面にアラートは表示されません。

「**[!UICONTROL カスタムデータ]**」セクションを使用して、キーと値のペアを追加します。

## カスタムデータ {#custom-data}

>[!CONTEXTUALHELP]
>id="ajo-message-push-custom"
>title="プッシュ通知のカスタムデータを設定します。"
>abstract="モバイルアプリケーション設定に応じて、カスタム変数をペイロードに追加します。"

「**[!UICONTROL カスタムデータ]**」セクションでは、モバイルアプリケーションの設定に応じて、ペイロードにカスタム変数を追加できます。 Adobe Experience Platformでのプッシュ通知の設定方法について詳しくは、[この節](push-gs.md)を参照してください

## 意思決定によるパーソナライゼーション {#decisioning-push}

**Decisioning**&#x200B;を使用すると、プッシュ通知のコンテンツをパーソナライズおよび最適化できます。 この機能により、優先順位スコア、数式、AI モデルを使用して、顧客に最適なコンテンツを動的に選択して表示できます。

プッシュ通知で決定ポリシーを作成および使用する方法について詳しくは、[この節](../experience-decisioning/create-decision.md)を参照してください。

## 詳細設定オプション {#advanced-options-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-advanced"
>title="プッシュ通知の詳細オプションを設定します。"
>abstract="このセクションでは、プッシュ通知のパーソナライゼーションを強化するのに役立ちます。"

プッシュ通知に&#x200B;**[!UICONTROL 詳細オプション]**&#x200B;を設定できます。 使用可能なパラメーターを以下に示します。

| パラメーター | 効果 |
|---------|---------|
| **[!UICONTROL 折りたたみ可能]** （iOS / Android） | 折りたたみ可能なメッセージとは、古くなった場合に新しいメッセージに置き換えられるメッセージのことです。 折りたたみ可能なメッセージの一般的なユースケースは、モバイルアプリにサーバーからのデータを同期するように指示するために使用されるメッセージです。 たとえば、スポーツアプリで、最新のスコアをユーザーに知らせるというものです。 最新のメッセージのみが関連しています。 一方、折りたたみ不可能なメッセージでは、すべてのメッセージがクライアントアプリにとって重要であり、配信する必要があります。 |
| **[!UICONTROL カスタムサウンド]** （iOS / Android） | 通知を受け取ったときに携帯端末が再生する音。 サウンドはアプリにバンドルする必要があります。 |
| **[!UICONTROL バッジ]** （iOS / Android） | バッジを使用して、新しい未読の情報の数をアプリケーションアイコンに直接表示します。 <br/> バッジの値は、ユーザーがアプリケーションで新しいコンテンツを開いたり読んだりするとすぐに消えます。 デバイスで通知を受信すると、関連するアプリのバッジ値を更新または追加できます。<br/>例えば、顧客の未読の記事の数を保存する場合、パーソナライゼーションを活用して、各顧客に一意の未読の記事バッジ値を送信できます。 詳細なパーソナライゼーションについては、[このセクション &#x200B;](../personalization/personalize.md)を参照してください。 |
| **[!UICONTROL 通知グループ]** （iOSのみ） | プッシュ通知に通知グループを関連付けます。<br/>iOS 12以降、通知グループを使用すると、メッセージのスレッドと通知トピックをスレッド IDに統合できます。 例えば、1つのグループ IDの下にマーケティング通知を送信する一方で、1つ以上の異なるIDの下に運用タイプの通知を保持する場合があります。<br/>これを示すには、groupID: 123 「新しいスプリングセーターのコレクションをチェックアウト」とgroupID: 456 「パッケージが配信されました」通知グループを設定できます。 この例では、すべての配信通知はグループ ID:456にバンドルされます。 |
| **[!UICONTROL 通知チャネル]** （Androidのみ） | プッシュ通知に通知チャネルを関連付けます。<br/>Android 8.0 （API レベル 26）以降、表示するには、すべての通知をチャネルに割り当てる必要があります。 詳しくは、[Android開発者向けドキュメント &#x200B;](https://developer.android.com/guide/topics/ui/notifiers/notifications#ManageChannels)を参照してください。 |
| **[!UICONTROL コンテンツ可用性フラグを追加]** （iOSのみ） | プッシュペイロードでコンテンツ利用可能フラグを送信して、アプリがプッシュ通知を受信するとすぐに起動できるようにします。つまり、アプリはペイロードデータにアクセスできるようになります。<br/> これは、アプリがバックグラウンドで実行されており、ユーザーの操作（プッシュ通知のタップなど）を必要としない場合でも機能します。 ただし、アプリが実行されていない場合は適用されません。 詳しくは、[Apple開発者向けドキュメント &#x200B;](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)を参照してください。 |
| **[!UICONTROL 可変コンテンツフラグを追加]** （iOSのみ） | 可変コンテンツフラグをプッシュペイロードに送信し、iOS SDKで提供されるnotification service application extensionによってプッシュ通知コンテンツを変更できるようにします。 詳しくは、[Apple開発者向けドキュメント &#x200B;](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)を参照してください。<br/>次に、モバイルアプリの拡張機能を活用して、[!DNL Journey Optimizer]から送信された着信プッシュ通知のコンテンツまたはプレゼンテーションをさらに変更できます。 例えば、このオプションを使用して、データの復号化、通知の本文またはタイトルテキストの変更、スレッド IDの通知への追加などができます。<br/>**重要**：このフラグは、iOS デバイスでレンダリングするために、ペイロードフィールド（`adb_media`など）を介してメディアの添付ファイル（画像、ビデオ）を含める場合に有効にする必要があります。 また、アプリは、ペイロードからメディアコンテンツをダウンロードして処理するための通知サービス拡張機能を実装する必要があります。 |
| **[!UICONTROL プッシュの有効期限を追加]** （iOSのみ） | プッシュの有効期限の&#x200B;**日付と時刻**&#x200B;を選択します。 IOSでは、通知の有効期限はハードストップとして適用されます。つまり、有効期限が切れた後にApple プッシュ通知サービス（APNS）に到達したメッセージは配信されないため、古い通知や無関係な通知が顧客に届くことはありません。 詳しくは、[Apple開発者向けドキュメント &#x200B;](https://developer.apple.com/documentation/usernotifications/sending-notification-requests-to-apns)を参照してください。 |
| **[!UICONTROL 通知の表示]** （Androidのみ） | プッシュ通知の表示を定義します。 <br/><b> プライベート </b>は、すべてのロック画面に通知を表示しますが、機密情報や個人情報は安全なロック画面に隠します。 <br/><b> パブリック </b>はすべてのロック画面に通知を完全に表示します。 <br/><b> シークレット </b>は、セキュリティで保護されたロック画面で通知の一部を表示しません。 <br/>詳しくは、[Android開発者向けドキュメント &#x200B;](https://developer.android.com/reference/android/app/Notification)を参照してください。 |
| **[!UICONTROL 通知の優先度]** （Androidのみ） | プッシュ通知の重要度を「低」から「最大」に定義します。 これにより、プッシュ通知の配信時の「侵入性」が決まります。 詳しくは、[Android開発者ドキュメント &#x200B;](https://developer.android.com/guide/topics/ui/notifiers/notifications#importance)を参照してください |
| **[!UICONTROL 配信の優先順位]** （Androidのみ） | プッシュ通知の優先度を高または通常に設定します。 メッセージの優先度について詳しくは、[Google開発者向けドキュメント &#x200B;](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)を参照してください。 |
| **[!UICONTROL 有効期間]** （Androidのみ） | メッセージの有効期限が切れるまでの秒数を設定します。 Androidでは、有効期限は配信ウィンドウとして扱われます。Firebase Cloud Messaging （FCM）は、有効期限を、メッセージを受信したときに開始されるTime-to-Live （TTL）値に変換します。つまり、未配信のキャンペーンが予想よりも遅く、または望ましい時間枠を超えて送信される可能性があります。 詳しくは、[Android開発者向けドキュメント &#x200B;](https://firebase.google.com/docs/cloud-messaging/concept-options#ttl)を参照してください。 |
