---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp メッセージの確認およびテスト
description: Journey Optimizer で WhatsApp メッセージを確認および送信する方法について説明します
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
exl-id: 31acb095-de90-495f-8e8c-43a78dedfa06
TQID: https://experienceleague.adobe.com/u2OevVu38fPdytpuTmHeSdEx3Wvpih7ifk-j88rhDFI
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7
  - id: b8df23d2-98a2-4406-86cc-2babe8728d36
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: a4e4f5ca5c3eb9dbfb5691cb5de420009ed7e5a5
workflow-type: tm+mt
source-wordcount: 414
ht-degree: 45%

---

# WhatsApp メッセージの確認および送信 {#send-whatsapp}

## WhatsApp メッセージのプレビュー {#preview-whatsapp}

メッセージコンテンツを定義したら、次のいずれかのシミュレーション方法を使用してコンテンツをプレビューできます。

* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックして、サンプル入力データまたはAI自動生成を使用してコンテンツのバリエーションをテストします。 [コンテンツバリエーションのシミュレート方法を学ぶ](../test-approve/simulate-sample-input.md)
* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択して、テストプロファイルでプレビューします。

コンテンツをプレビューおよびテストする方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

## コンテンツの検証 {#whatsapp-validate}

エディターの上部セクションでアラートを確認する必要があります。 単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。 発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。 例えば、テキストメッセージが空の場合は警告メッセージが表示されます。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。 例えば、件名がない場合は、それを警告するエラーメッセージが表示されます。

## WhatsApp メッセージの送信 {#whatsapp-send}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、テキストメッセージを送信できるようにするには、承認をリクエストする必要があります。 [詳細情報](../test-approve/gs-approval.md)

WhatsApp メッセージの準備が整ったら、[ジャーニー](../building-journeys/publish-journey.md)または[キャンペーン](../campaigns/review-activate-campaign.md)の設定を完了して送信します。

## WhatsApp インタラクションの分析 {#whatsapp-channel-context}

Journey Optimizerは、WhatsApp チャネルから返された追加のインタラクションデータを取得し、`whatsAppChannelContext` フィールドグループの&#x200B;**AJO - メールトラッキングエクスペリエンスイベントデータセット**&#x200B;に保存します。 これらのフィールドを使用して、[&#x200B; オーディエンス &#x200B;](../audience/about-audiences.md)を作成し、[&#x200B; クエリ &#x200B;](../data/get-started-queries.md)を実行し、WhatsApp エンゲージメントを分析します。 [&#x200B; システムデータセットの詳細](../data/get-started-datasets.md#system-datasets)。

次のフィールドがキャプチャされます。

| フィールド | 説明 |
|-|-|
| `messageType` | WhatsApp メッセージの種類（例：`templateBased`、`response`）。 |
| `inboundMessage` | インバウンド返信コンテンツ （例：`stop`、`start`、`subscribe`） |
| `inboundNumber` | インバウンドメッセージを受信した送信者ID。 |
| `channelType` | チャネルカテゴリ （`Utility`、`Marketing`または`Promotional`）。 |
| `profileNumber` | インバウンドメッセージを受信した電話番号。 |
| `origTimestamp` | Meta / WhatsAppの元のタイムスタンプ。 |
| `status` | 標準化されたプロバイダーのフィードバック （`sent`、`delivered`、`bounce`、`error`、`delay`、`duplicate`、`denylist`、`exclude`または`unknown`）と生のプロバイダーのステータスメッセージを含む配信ステータス。 |
| `reactionEvent` | ユーザー応答のコンテンツ：反応の絵文字、または特定のメッセージへの返信のメッセージテキスト。 |
| `reactionMessageID` | 応答する元のメッセージのID。 |
| `reactionActionName` | 応答アクションの種類（`react`、`unreact`または`reply`）。 |
| `interactiveSelectedTitle` | WhatsApp インタラクティブメッセージからユーザーが選択したタイトル。 |
| `interactiveType` | インタラクティブ メッセージの種類（`list reply`、`button reply`または`button`）。 |
| `interactiveSelectedDescription` | 選択したWhatsApp インタラクティブオプションの説明。 |
| `interactiveSelectedID` | WhatsAppから選択したオプションのID。 |

このデータセットをクエリするには、クエリサービスの`ajo_email_tracking_experience_event_dataset` テーブルを使用します。 クエリパターンと関連するユースケースについては、[&#x200B; データセットのクエリ例](../data/datasets-query-examples.md)を参照してください。
