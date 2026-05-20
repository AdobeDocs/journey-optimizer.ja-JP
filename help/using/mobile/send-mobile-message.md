---
solution: Journey Optimizer
product: journey optimizer
title: モバイルメッセージの確認とテスト
description: Journey Optimizerでモバイルメッセージを確認して送信する方法について説明します
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
TQID: https://experienceleague.adobe.com/JPjBxyZzo13tgSLo0dqd5bFOwn9C6MHkA-DjLzlAdEI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: c41e8697-e629-4c38-96b3-564faaa17acfid: f8d2e9f0-69c9-40cd-890f-71336c8dfff7id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 9a68782b0ca1a9a65db621209cf4f39ea5ce911d
workflow-type: tm+mt
source-wordcount: 536
ht-degree: 63%

---

# モバイルメッセージの確認と送信 {#send-sms}

## モバイルメッセージのプレビュー {#preview-sms}

メッセージコンテンツを定義したら、（CSV／JSON ファイルからアップロードした、または手動で追加した）テストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューできます。 パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージ内でどのように表示されるかを確認できます。

これを行うには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルデータを使用してメッセージを確認します。

![](assets/sms_preview_2.png)

コンテンツをプレビューおよびテストする方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

### 文字のエンコーディングと制限 {#sms-character-limits}

モバイルメッセージの計画と管理を支援する「**[!UICONTROL コンテンツをシミュレート]**」メニューにアクセスすると、文字数が表示されます。

![](assets/sms_preview_3.png)

Journey Optimizer は、 SMS エディターで UTF-8 エンコーディングを使用するので、2 バイト文字または Unicode 文字を入力または貼り付けることができます。 これらの文字は、配信のためにサービスプロバイダーに送信されます。 ほとんどの SMS プロバイダーは、160 文字の制限がある標準メッセージには GSM 7 ビットエンコーディングを使用し、70 文字の制限がある GSM 以外の文字が検出されると UTF-16（UCS-2）に切り替えます。

文字カウントには、動的なパーソナライゼーションや GSM 以外の 7 ビット特殊文字により導入されるバリエーションは反映されません。

>[!IMPORTANT]
>
>Journey Optimizer SMS 配信レポートでは、連結メッセージと動的なパーソナライゼーションが考慮されないので、プロバイダーから送信された実際のメッセージ数が反映されない場合があります。 使用状況と課金情報について詳しくは、アドビ担当者にお問い合わせください。
>
>SMS 課金の超過を最小限に抑えるベストプラクティスについて詳しくは、[文字最適化の SMS ベストプラクティス](mobile-cost-optimization.md)を参照してください。

## コンテンツの検証 {#sms-validate}

>[!NOTE]
>
> 配信品質を高めるには、プロバイダーでサポートされている形式の電話番号を使用します。 例えば、Twilio と Sinch では E.164 形式の電話番号のみをサポートしています。

エディターの上部セクションでアラートを確認する必要があります。 単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。 発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

![](assets/sms-alert-button.png)

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。 例えば、モバイルメッセージが空の場合、または動的コンテンツで文字制限を超える可能性がある場合は、警告メッセージが表示されます。

  **文字制限：** セグメントあたり160文字（GSM 7 ビット）、Unicode/絵文字の場合は70文字、合計で最大1500文字。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。 例えば、件名がない場合は、それを警告するエラーメッセージが表示されます。

すべての条件分岐、パーソナライゼーションフィールド、および動的コンテンツを最長で評価することにより、検証によって&#x200B;**可能な最大長**&#x200B;が計算されるため、シミュレートされたメッセージが短い場合でも、「SMS テキスト文字制限を超えました」 **という警告が表示される場合があります。**

検証では、可能なすべてのプロファイルデータの最大長を計算し、シミュレーションでは、1つのテストプロファイルの実際の出力を示します。

## モバイルメッセージを送信する {#sms-send}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となる場合、モバイルメッセージを送信するには、承認をリクエストする必要があります。 [詳細情報](../test-approve/gs-approval.md)

モバイルメッセージの準備ができたら、[ ジャーニー](../building-journeys/journey-gs.md)または[ キャンペーン ](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](mobile-configuration.md)
* [SMS／MMS レポート](../reports/journey-global-report-cja-sms.md)
* [モバイルメッセージの作成](create-mobile-message.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journey-action.md)
