---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp メッセージのチェックとテスト
description: Journey Optimizerで WhatsApp メッセージを確認して送信する方法を学ぶ
feature: WhatsApp
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
badge: label="ベータ版" type="Informative"
source-git-commit: 7ca149d420f802a6230e699cffefddc4117cb85e
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 75%

---

# WhatsApp メッセージをチェックして送信する {#send-whatsapp}

>[!BEGINSHADEBOX]

**目次**

* [WhatsApp メッセージの基本を学ぶ](get-started-whatsapp.md)
* [WhatsApp 設定の基本を学ぶ](whatsapp-configuration.md)
* [WhatsApp メッセージの作成](create-whatsapp.md)
* **[WhatsApp メッセージの確認と送信](send-whatsapp.md)**

>[!ENDSHADEBOX]

## WhatsApp メッセージのプレビュー {#preview-whatsapp}

メッセージコンテンツを定義したら、CSV／JSON ファイルからアップロードした、または手動で追加したテストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューできます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージ内でどのように表示されるかを確認できます。[詳しくは、サンプル入力データを使用してコンテンツをテストする方法を参照してください](../test-approve/simulate-sample-input.md)

これを行うには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルデータを使用してメッセージを確認します。

コンテンツをプレビューおよびテストする方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

## コンテンツの検証 {#whatsapp-validate}

エディターの上部セクションでアラートを確認する必要があります。単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。例えば、テキストメッセージが空の場合は警告メッセージが表示されます。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。例えば、件名がない場合は、それを警告するエラーメッセージが表示されます。

## WhatsApp メッセージの送信 {#whatsapp-send}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、テキストメッセージを送信できるようにするには、承認をリクエストする必要があります。[詳細情報](../test-approve/gs-approval.md)

WhatsApp メッセージの準備が整ったら、[ ジャーニー ](../building-journeys/publishing-the-journey.md) または [ キャンペーン ](../campaigns/review-activate-campaign.md) の設定を完了して送信します。
