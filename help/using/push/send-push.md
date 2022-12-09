---
solution: Journey Optimizer
product: journey optimizer
title: Push 通知を送信します。
description: このような場合は、旅オプティマイザーの「プッシュ通知」のプレビューとテストを行う方法について学習します。
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Push 通知を送信します。 {#send-push}

## プッシュ通知のプレビュー {#preview-push}

作成したメッセージコンテンツについては、テストプロファイルを使用してプレビューとテストを行うことができます。 パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを確認できます。これによりテストプロファイルデータが活用されます。

1. をクリック **[!UICONTROL Simulate content]** します。

1. テストプロファイルを追加するには、をクリック **[!UICONTROL Manage test profiles]** します。

1. And **[!UICONTROL Identity value]** フィールドを使用 **[!UICONTROL Identity namespace]** してテストプロファイルを検索します。次に、をクリック **[!UICONTROL Add profile]** します。

   ![](assets/push_preview_1.png)

1. 前述の手順を適用してテストプロファイルを選択します。

   ![](assets/push_preview_2.png)

1. プッシュプレビューでは、メッセージコンテンツでテストプロファイルデータが活用されています。

   コンテンツ **[!UICONTROL iOS]** **[!UICONTROL Android]** をプレビューするデバイスのタイプを選択します。

   ![](assets/push_preview_3.png)

## プッシュ通知の検証 {#push-validate}

>[!NOTE]
>
> Deliverability を改善するには、プロバイダーによってサポートされている形式の電話番号を常に使用してください。 例えば、Twilio では、E.i 形式の電話番号のみがサポートされています。

また、エディターの上半分に表示されるアラートも確認する必要があります。  この中には簡単な警告が表示されているものもありますが、メッセージを使用しないようにすることもできます。 アラートは、次の2種類の方法で発生する可能性があります。

* **警告** は「推奨事項」および「ベストプラクティス」を参照してください。

* **エラーがあると、次のようなエラー** が解決されていない限り、それらのテストやアクティブ化は実行できません。

   * **[!UICONTROL The push version of the message is empty]**: push 通知の本文またはタイトルが見つからない場合に、このエラーが表示されます。 この節 ](create-push.md) では、プッシュ通知の [ 内容を定義する方法について説明します。

   * **[!UICONTROL Surface doesn't exist]**: メッセージの作成後に、選択したサーフェスが削除された場合は、メッセージを使用できません。 このエラーが発生した場合は、メッセージ **[!UICONTROL Properties]** 内の別の面を選択します。 この節 ](../configuration/channel-surfaces.md) では、 [ チャネルのサーフェスについて詳しく説明しています。

   * **[!UICONTROL Push iOS/Android payload has exceeded limit of 4KB]**: プッシュ通知のサイズは4KB を超えることはできません。 この制限については、イメージや絵文字の使用量を減らすようにしてください。 この節 ](../push/create-push.md) では [ 、プッシュ通知の内容を管理する方法を説明しています。

![](assets/push_alert.png)

プッシュ通知の準備ができたら、移動または [ キャンペーン ](../campaigns/create-campaign.md) の ](../building-journeys/journey-gs.md) [ 設定を完了して送信します。
