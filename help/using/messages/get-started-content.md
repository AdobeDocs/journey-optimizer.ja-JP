---
title: メッセージを使い始める
description: Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 712dc172-6c0d-4ce8-ba16-de99d65fc641
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 8%

---

# チャネルアクションの概要 {#get-started-messages}

>[!CONTEXTUALHELP]
>id="ajo_journey_message"
>title="チャネルアクション"
>abstract="チャネルアクションを使用して、プッシュ、SMS、または E メールメッセージを送信します。"

用途 [!DNL Journey Optimizer] パーソナライズされたプッシュ通知、SMS および電子メールメッセージを作成して配信します。 すべてのメッセージは、メッセージキャンバス上のアクションの一部としてインラインでジャーニーできます。  「テンプレートとして保存」機能を使用すると、コンテンツを簡単に再利用できます。 次のことができます。

* 用途 [!DNL Journey Optimizer] **メールデザイン機能** レスポンシブ e メールを作成または読み込むには、以下を実行します。

* 活用 **Adobe Experience Manager Assets Essentials** e メールをエンリッチメントするには、独自の assets データベースを作成および管理します。

* 検索 **Adobe Stockの写真** コンテンツを作成し、e メールデザインを改善します。

* パーソナライズされた **プッシュ通知、SMS、E メール** プロファイル属性に基づいて

* **配信の送信** これらのコンテンツに基づいて、顧客行動を追跡します。

>[!NOTE]
>
>ユーザーは、製品プロファイルに応じて、ジャーニーにアクセス、作成、編集、公開できます。 ユーザー権限の詳細については、 [この節](../administration/permissions.md)を参照してください。


## ジャーニーへのメッセージの追加{#messages-in-journeys}

>[!CONTEXTUALHELP]
>id="ajo_message_category"
>title="メッセージカテゴリ"
>abstract="商用メッセージの場合は「マーケティング」を、商用メッセージの場合は「トランザクション」を、注文の確認、パスワードのリセット通知、配信情報など、商用以外のメッセージの場合は「トランザクション」を選択します"

>[!CONTEXTUALHELP]
>id="ajo_message_surface"
>title="チャンネルサーフェス"
>abstract="チャネルサーフェスは、キャンペーンまたはジャーニー経由でアクションを正常に配信するためのすべての設定を持つ、そのチャネルのインスタンスです。 システム管理者が定義します。"

ジャーニーにメッセージを追加するには、ジャーニーキャンペーンにプッシュ、SMS、E メールアクティビティを追加します。

1. ジャーニーを開始するには、 [イベント](../building-journeys/general-events.md) または [セグメントを読み取り](../building-journeys/read-segment.md) アクティビティ。

1. 次の **アクション** パレットのセクションで、 **電子メール**、 **SMS** または **プッシュ** アクティビティをキャンバスに追加します。

   ![](assets/add-a-message.png)

1. ラベルと説明を入力します。

1. メッセージを選択 **[!UICONTROL カテゴリ]**:選択 **マーケティング** 商用メッセージの場合は、 **トランザクション** 商用以外のメッセージ（注文の確認、パスワードのリセット通知、配信情報など）の場合。

   >[!NOTE]
   >
   >定義した場合 [頻度ルール](../configuration/frequency-rules.md) 特定のチャネルとカテゴリの場合、そのチャネルとカテゴリを選択すると、それらがメッセージに自動的に適用されます。 現在、 **[!UICONTROL マーケティング]** カテゴリは頻度ルールで使用できます。

   ![](assets/inline-message-category.png)

   >[!CAUTION]
   >
   >マーケティングタイプのメッセージには、 [オプトアウトリンク](../messages/consent.md#opt-out-management). トランザクションメッセージは、マーケティングコミュニケーションから購読解除されたプロファイルに送信される可能性があるので、トランザクションメッセージではこの設定は必要ありません。

1. チャネルを選択 **[!UICONTROL サーフェス]** （例：メッセージプリセット）を使用してメッセージを送信します。

   サーフェスは、 [システム管理者](../start/path/administrator.md). ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [詳細情報](../configuration/message-presets.md)。

   >[!CAUTION]
   >
   >選択したメッセージカテゴリとチャネルに対して、有効なチャネルサーフェスを選択する必要があります。

   メッセージのラベル、説明、サーフェスは、 **[!UICONTROL プロパティ]** 」ボタンをクリックします。

1. メッセージコンテンツの作成.

   メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

   * [E メールの作成](create-email.md)
   * [プッシュ通知の作成](create-push.md)
   * [SMS メッセージの作成](create-sms.md)

## 送信時間の最適化を有効にする{#sto-in-journeys}

電子メールおよびプッシュ通知の場合、 **[!UICONTROL 送信時間の最適化]**.

用途 **[!UICONTROL 送信時間の最適化]** 各ユーザーがメッセージの開封率とクリック率を上げるために、パーソナライズされた送信時間をスケジュールする場合。 [詳細情報](../messages/send-time-optimization.md)。


## 詳細設定パラメーター{#adv-settings}

詳細設定パラメーターは読み取り専用で、デフォルトでは非表示です。

詳細設定パラメーターにアクセスするには、 **[!UICONTROL 読み取り専用フィールドを表示]** アイコンをクリックします。

![](assets/show-read-only.png)

詳細設定パラメーターがメッセージウィンドウの下部に表示されます。 これらのパラメーターは、 [システム管理者](../start/path/administrator.md) 内 [チャンネル表面](../configuration/message-presets.md) （例：メッセージプリセット）をメッセージに関連付けました。

プッシュ通知の場合、次のパラメーターを表示できます。トークン、AppID、AppPlatform。

![](assets/push-adv-parameters.png)

E メールの場合は、プライマリ E メールアドレスを表示できます。

特定の用途で、特定のコンテキストでこれらの値を上書きできます。 値を強制的に指定するには、 **パラメーターの上書きを有効にする** 「 」アイコンをクリックします。 このオプションは、次の場合に便利です。

* E メールをテストし、E メールアドレスを追加できます。 ジャーニーの公開後にメールが届きます。
* リストの購読者の E メールアドレスを参照します。 詳しくは、 [この使用例](../building-journeys/message-to-subscribers-uc.md).

同じアイコンをクリックして、デフォルトのパラメータにリセットします。


## メッセージの参照{#browse-message}

1 つのジャーニーで複数のメッセージを使用する場合、 **コンテンツを編集** 画面

![](assets/inline-messages-multi-content.png)

その後、 [アラートをチェック](alerts.md) および [シミュレート](../design/preview.md) 単一ビューの各コンテンツ。

## メッセージの複製 {#duplicate-message}

ジャーニーキャンバスから既存のメッセージをコピーできます。

手順は次のとおりです。

1. コピーするメッセージを選択します。

1. 以下を使用： **[!UICONTROL コピー]** ボタン **[!UICONTROL アクション]** ウィンドウ

   ![](assets/message-duplicate.png)

1. 入力 **crtl+V** をクリックして、メッセージを貼り付けます。

   メッセージがジャーニーキャンバスに追加されました。 すべての設定が新しいメッセージにコピーされます。

   ![](assets/message-duplicated.png)

1. メッセージの編集時などに、次のように、最初のメッセージをコピーから区別できるように、メッセージの名前を変更します。

   ![](assets/multi-message.png)


>[!NOTE]
>
>E メールの場合は、既存のメッセージをテンプレートに変換することもできます。 [詳細情報](../design/email-templates.md)。

## メッセージの削除

メッセージを削除するには、チャネルアクションアクティビティウィンドウの上部にあるごみ箱アイコンを使用します。

![](assets/delete-message.png)

以下を使用： **[!UICONTROL 確認]** ボタンをクリックして検証します。
