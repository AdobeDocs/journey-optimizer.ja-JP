---
solution: Journey Optimizer
product: journey optimizer
title: URL トラッキングを設定
description: メールチャネル設定レベルでURL トラッキングを設定する方法について説明します
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: 設定、電子メール、設定
exl-id: 5a12280c-b937-4cd9-a1ef-563bab48e42e
TQID: https://experienceleague.adobe.com/q1T-efX3vK77d1PfKA8mWU73w6Cj4-H95RynkHHg16U
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: fae48155-b23f-40d2-a252-a25bce350b4d
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 489
ht-degree: 0%

---

# URL トラッキング {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="URL トラッキングパラメーターの定義"
>abstract="このセクションを使用すると、メールコンテンツに存在するURLにトラッキングパラメーターを自動的に追加できます。 この機能はオプションです。"

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_url_preview"
>title="URL トラッキングパラメーターのプレビュー"
>abstract="メールコンテンツに存在するURLにトラッキングパラメーターを追加する方法を確認します。"

新しい[ メールチャネル設定](email-settings.md)を設定する際に、**[!UICONTROL URL トラッキングパラメーター]**&#x200B;を定義して、チャネル全体のマーケティング活動の効果を測定できます。 この機能の有効化はオプションです。

対応するセクションで定義されたパラメーターは、メールメッセージのコンテンツに含まれるURLの末尾に追加されます。 その後、Adobe AnalyticsやGoogle Analyticsなどのweb分析ツールでこれらのパラメーターを取得し、様々なパフォーマンスレポートを作成できます。

>[!NOTE]
>
>URLに追加されたURL トラッキングパラメーターの順序はランダムで、制御できません。 システムで特定の順序でパラメーターが必要な場合は、それを解析して並べ替える必要があります。

「**[!UICONTROL 新しいパラメーターを追加]**」ボタンを使用して、最大10個のトラッキングパラメーターを追加できます。

![](assets/preset-url-tracking.png){width="80%"}

URL トラッキングパラメーターを設定するには、**[!UICONTROL 名前]**&#x200B;および&#x200B;**[!UICONTROL 値]** フィールドに目的の値を直接入力できます。

[ パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)を使用して、各&#x200B;**[!UICONTROL 値]** フィールドを編集することもできます。 編集アイコンをクリックしてエディターを開きます。 そこから、使用可能なコンテキスト属性を選択したり、テキストを直接編集したりできます。

![](assets/preset-url-tracking-editor.png)

パーソナライゼーションエディターでは、次の定義済み値を使用できます。

* **メッセージ プロファイル ID**：配信内の各対象プロファイルに送信された各メッセージを一意に識別するメッセージ指向の属性。

* **オファーID**：電子メールで使用されるオファーのID。

* **Source アクション ID**: ジャーニーまたはキャンペーンに追加されたメールアクションのID。

  >[!NOTE]
  >
  >製品の変更後に閉じられたか再公開されなかったジャーニーは、トラッキング URLに`context.system.source.actionId`が入力されず、空のプレースホルダー（例：`cid=em-acou-adob{}`）になる可能性があります。 トラッキングパラメーターが正しく入力されるようにするには、[影響を受けるジャーニーを再公開するか、クローズしたジャーニーに対してこのコンテキストフィールドへの参照を削除します](../building-journeys/publish-journey.md#journey-create-new-version)。 詳しくは、[ ライブジャーニー実行のトラブルシューティング ](../building-journeys/troubleshooting-execution.md#tracking-parameters-closed-journeys)を参照してください。

* **Source アクション名**: ジャーニーまたはキャンペーンに追加された電子メールアクションの名前。

* **Source id**：電子メールが送信されたジャーニーまたはキャンペーンのID。

* **Source名**：電子メールが送信されたジャーニーまたはキャンペーンの名前。

* **Source バージョン ID**：電子メールが送信されたジャーニーまたはキャンペーンバージョンのID。

>[!NOTE]
>
>パーソナライゼーションエディターで、テキスト値を入力したり、コンテキスト属性を使用したりすることができます。 各&#x200B;**[!UICONTROL 値]** フィールドには、最大5 KBまでの文字数を入力できます。

<!--You can drag and drop the parameters to reorder them.-->

以下に、Adobe AnalyticsとGoogle Analyticsの互換性のあるURLの例を示します。

* Adobe Analyticsと互換性のあるURL: `www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analyticsと互換性のあるURL: `www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

結果のトラッキング URLを動的にプレビューできます。 パラメーターを追加、編集または削除するたびに、プレビューは自動的に更新されます。

![](assets/preset-url-tracking-preview.png)

>[!NOTE]
>
>また、メールコンテンツに含まれるリンクに、動的にパーソナライズされたトラッキングパラメーターを追加することもできます。 [詳細情報](surface-personalization.md#personalize-url-tracking)
