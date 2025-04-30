---
solution: Journey Optimizer
product: journey optimizer
title: テキストメッセージの確認およびテスト
description: Journey Optimizerで LINE メッセージを確認して送信する方法を学ぶ
feature: Line
topic: Content Management
role: User
level: Beginner
source-git-commit: 8714ac6b2fd76ec859c358535fa322f0ac333a82
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 79%

---

# LINE メッセージの確認と送信 {#send-line}

## テキストメッセージのプレビュー {#preview-line}

メッセージコンテンツを定義したら、CSV／JSON ファイルからアップロードした、または手動で追加したテストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューできます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージ内でどのように表示されるかを確認できます。[詳しくは、サンプル入力データを使用してコンテンツをテストする方法を参照してください](../test-approve/simulate-sample-input.md)

これを行うには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルデータを使用してメッセージを確認します。

コンテンツをプレビューおよびテストする方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

## コンテンツの検証 {#line-validate}

エディターの上部セクションでアラートを確認する必要があります。単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。例えば、テキストメッセージが空の場合は警告メッセージが表示されます。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。例えば、件名が見つからない場合に警告するエラーメッセージが表示されます。

## LINE メッセージの送信 {#line-send}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、テキストメッセージを送信できるようにするには、承認をリクエストする必要があります。[詳細情報](../test-approve/gs-approval.md)

LINE メッセージの準備が整ったら、[ ジャーニー ](../building-journeys/journey-gs.md) または [ キャンペーン ](../campaigns/create-campaign.md) の設定を完了して送信します。

