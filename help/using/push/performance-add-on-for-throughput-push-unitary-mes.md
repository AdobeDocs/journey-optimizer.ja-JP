---
solution: Journey Optimizer
product: journey optimizer
title: スループット用パフォーマンスアドオン – （プッシュ）単一 – メッセージ配信
description: Adobe Journey Optimizerでスループット – （プッシュ）単一 – メッセージ配信にPerformance Add-onを設定して使用する方法を説明します。
feature: Push
topic: Content Management
role: User
level: Intermediate
exl-id: 2d0677ad-41c8-4299-a7c8-0e4f8a1716f7
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: c96d2aa5-76a2-443d-8d23-5de95577c909
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b6b77c26-2a48-4a62-9ceb-5ae67f4dfde5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 4aebdb06094628cfe7393c7f7b41e5fe0ee9df13
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---


# スループット用パフォーマンスアドオン – （プッシュ）単一 – メッセージ配信 {#performance-add-on-for-throughput-push-unitary-mes}

>[!AVAILABILITY]
>
>この機能は、**AJO26.7** （2026-07-27）から利用できます。

## 概要 {#overview}

Adobe Journey Optimizerでは、**スループット – （プッシュ）単一 – メッセージ配信**&#x200B;用のPerformance Add-onを導入しました。これにより、組織は、より適切でパーソナライズされた顧客体験をプッシュチャネルをまたいで提供できるようになります。

このページでは、キャンペーンとジャーニーでこの機能を設定して使用する方法について説明します。

## 前提条件 {#prerequisites}

始める前に：

* 必要な&#x200B;**プッシュ**&#x200B;権限を持つAdobe Journey Optimizerにアクセスできます。
* プッシュチャネルサーフェスが設定されます。 [ プッシュチャネルの設定](../configuration/channel-surfaces.md)を参照してください。

## 仕組み {#how-it-works}

Performance Add-on for throughput - （Push） Unitary - Message Deliveryは、AJO実行エンジンと直接統合されます。 プロファイルがジャーニーまたはキャンペーンのプッシュアクションに達すると、送信時に設定されたパラメーターが適用されます。

主な機能：

* **プロファイルレベルのパーソナライゼーション** — プロファイルとコンテキスト属性を使用して、受信者ごとに設定を調整します。
* **ジャーニーとキャンペーンのサポート** – 調整されたジャーニーと1回限りのキャンペーンの両方で機能します。
* **リアルタイム指標** – 結果が[ プッシュレポート ](../reports/push-report.md)に表示されます。

## スループット用のPerformance Add-onの設定 {#configure}

1. AJOの左側のメニューで、**チャネル**/**プッシュ設定**&#x200B;に移動します。
1. チャネル設定を選択または作成します。
1. 「**用** パフォーマンスアドオン」セクションで、この機能を有効にします。
1. 必要なパラメーターを設定します。
1. 「**保存**」をクリックします。

>[!NOTE]
>
>設定の変更は、新しいジャーニーの実行に適用されます。 進行中のジャーニーは影響を受けません。

## 関連トピック {#related-topics}

* [プッシュ通知の基本を学ぶ](get-started-push.md)
* [プッシュ通知の作成](create-push.md)
* [AJO26.7 リリースノート](../rn/release-notes.md)
