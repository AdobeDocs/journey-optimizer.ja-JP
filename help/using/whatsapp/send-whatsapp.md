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
source-git-commit: 623d9b15d1f7f4e7f73f26cf3e19516bed4c0f56
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 100%

---

# WhatsApp メッセージの確認および送信 {#send-whatsapp}

## WhatsApp メッセージのプレビュー {#preview-whatsapp}

メッセージコンテンツを定義したら、CSV／JSON ファイルからアップロードした、または手動で追加したテストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューできます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージ内でどのように表示されるかを確認できます。

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

WhatsApp メッセージの準備が整ったら、[ジャーニー](../building-journeys/publishing-the-journey.md)または[キャンペーン](../campaigns/review-activate-campaign.md)の設定を完了して送信します。
