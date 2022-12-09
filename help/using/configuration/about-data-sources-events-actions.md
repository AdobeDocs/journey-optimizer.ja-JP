---
solution: Journey Optimizer
product: journey optimizer
title: Journeys の構成
description: データソース、イベント、アクションの設定方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: c144d44f-031f-4ca2-800e-d3878af400a5
source-git-commit: f04454860ebe597d3306e62b58de5f32e08342ee
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Journeys の構成 {#configure-journeys}

>[!CONTEXTUALHELP]
>id="ajo_journey_configuration_dashboard"
>title="旅の設定について"
>abstract="Journeys を使用してメッセージを送信するには、データソース、イベント、アクションを設定する必要があります。 データソースを使用すると、例えば、journeys で使用される追加情報を取得するための、システムへの接続を定義することができます。 イベントを使用すると、イベントを受け取ったときに journeys をトリガーできます。 カスタムアクションを使用すると、サードパーティシステムに接続してメッセージを送信できます。 旅オプティマイザーに組み込まれたメッセージ機能を使用している場合は、アクションを設定する必要はありません。"

Journeys を使用してメッセージを送信するには、と **[!UICONTROL Actions]** を **[!UICONTROL Events]** 設定 **[!UICONTROL Data Sources]** する必要があります。

![](assets/admin-menu.png)

## データソース {#data-sources}

データソース設定を使用すると、journeys で使用される追加情報を取得するための、システムへの接続を定義することができます。 [詳細情報](../../using/datasource/about-data-sources.md)

## 発生 {#events}

イベントを使用すると、journeys unitarily を利用して、その過程に流れている個々のメッセージをリアルタイムに送信することができます。

イベントの設定では、journeys に必要なイベントを設定します。 受信イベントデータは、Adobe エクスペリエンスデータモデル (XDM) に従って標準化されています。 イベントは、認証および認証されていないイベント (Adobe Mobile SDK イベントなど) 用のストリーミング取り込み Api によって発生します。 [詳細情報](../../using/event/about-events.md)

## 活動 {#actions}

旅のオプティマイザーメッセージは、次のような機能を備えています。 &quot;チャンネルアクション&quot; アクティビティを追加するだけです。 サードパーティのシステムを使用してメッセージを送信している場合は、カスタムアクションを作成することができます。 [詳細情報](../../using/action/action.md)

## Adobe エクスペリエンスプラットフォームフィールドを参照します。 {#friendly-names-display}

イベントのペイロード ](../event/about-creating.md#define-the-payload-fields) 、フィールドグループのペイロード ](../datasource/configure-data-sources.md#define-field-groups) 、 [ および式エディター ](../building-journeys/expression/expressionadvanced.md) で [ のフィールドの選択を定義 [ すると、フィールド名に加えて表示名が表示されます。この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。

スキーマの設定時に「xdm: alternateDisplayInfo」などのディスクリプターが提供されている場合は、表示名がユーザーにとってわかりやすい名前に置き換えられます。 これは、Evevand generic fields を操作する場合に特に便利です。 API 呼び出しを使用して、フレンドリーな名前記述子を設定することができます。 詳しくは、『スキーマレジストリ開発ガイド』 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) の [ 「target = &quot;_blank&quot;}」を参照してください。

![](assets/xdm-from-descriptors.png)

使用可能な名前が表示されて `<friendly-name>(<name>)` いる場合は、そのフィールドがに表示されます。 表示名が指定されていない場合は、表示名が表示 `<display-name>(<name>)` されます。 定義されていない場合は、フィールドの技術的な名前のみが表示 `<name>` されます。

>[!NOTE]
>
>ユニオンスキーマからフィールドを選択した場合は、表示名は取得されません。
