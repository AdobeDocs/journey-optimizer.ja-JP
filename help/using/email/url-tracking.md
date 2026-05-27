---
solution: Journey Optimizer
product: journey optimizer
title: URL トラッキングの設定
description: メールのチャネル設定レベルで URL トラッキングを設定する方法について説明します。
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: 設定, メール, 設定
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
ht-degree: 85%

---

# URL トラッキング {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="URL トラッキングパラメーターの定義"
>abstract="このセクションを使用すると、メールコンテンツに存在する URL にトラッキングパラメーターを自動的に追加できます。 この機能はオプションです。"

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_url_preview"
>title="URL トラッキングパラメーターのプレビュー"
>abstract="メールコンテンツに存在する URL にトラッキングパラメーターを追加する方法を確認します。"

新しい[メールチャネル設定](email-settings.md)を指定する際に、**[!UICONTROL URL トラッキングパラメーター]**&#x200B;を定義し、チャネルをまたいでマーケティング活動の有効性を測定できます。 この機能のアクティブ化はオプションです。

対応する節で定義したパラメーターは、メールメッセージコンテンツに含まれる URL の末尾に追加されます。 その後、これらのパラメーターを Adobe Analytics や Google Analytics などの web 分析ツールで取得し、様々なパフォーマンスレポートを作成できます。

>[!NOTE]
>
>URLに追加されたURL トラッキングパラメーターの順序はランダムで、制御できません。 システムに特定の順序でパラメーターが必要な場合は、解析して並べ替える必要があります。

「**[!UICONTROL 新しいパラメーターを追加]**」ボタンを使用して最大 10 個のトラッキングパラメーターを追加できます。

![](assets/preset-url-tracking.png){width="80%"}

URL トラッキングパラメーターを設定するには、目的の値を&#x200B;**[!UICONTROL 名前]**&#x200B;および&#x200B;**[!UICONTROL 値]**&#x200B;フィールドに直接入力することができます。

また、[パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)を使用して各&#x200B;**[!UICONTROL 値]**&#x200B;フィールドを編集することもできます。 「編集」アイコンをクリックして、エディターを開きます。 ここから、利用可能なコンテキスト属性を選択したり、テキストを直接編集したりできます。

![](assets/preset-url-tracking-editor.png)

パーソナライゼーションエディターでは、次の事前定義済みの値を使用できます。

* **メッセージプロファイル ID**：配信内の各ターゲットプロファイルに送信された各メッセージを一意に識別するメッセージ指向の属性。

* **オファー ID**：メールで使用されるオファーの ID。

* **ソースアクション ID**：ジャーニーまたはキャンペーンに追加されたメールアクションの ID。

  >[!NOTE]
  >
  >製品の変更後に閉じられたか再公開されなかったジャーニーは、トラッキング URLに`context.system.source.actionId`が入力されず、空のプレースホルダー（例：`cid=em-acou-adob{}`）になる可能性があります。 トラッキングパラメーターが正しく入力されるようにするには、[影響を受けるジャーニーを再公開するか、クローズしたジャーニーに対してこのコンテキストフィールドへの参照を削除します](../building-journeys/publish-journey.md#journey-create-new-version)。 詳しくは、[ ライブジャーニー実行のトラブルシューティング ](../building-journeys/troubleshooting-execution.md#tracking-parameters-closed-journeys)を参照してください。

* **ソースアクション名**：ジャーニーまたはキャンペーンに追加されたメールアクションの名前。

* **ソース ID**：メールの送信に使用されたジャーニーまたはキャンペーンの ID。

* **ソース名**：メールの送信に使用されたジャーニーまたはキャンペーンの名前。

* **ソースバージョン ID**：メールの送信に使用されたジャーニーまたはキャンペーンのバージョンの ID。

>[!NOTE]
>
>テキスト値の入力と、パーソナライゼーションエディターからのコンテキスト属性の使用を組み合わせることができます。 各「**[!UICONTROL 値]**」フィールドには、5 KB の制限までの文字数を含めることができます。

<!--You can drag and drop the parameters to reorder them.-->

以下に、Adobe Analytics および Google Analytics 互換 URL の例を示します。

* Adobe Analytics 互換 URL：`www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics 互換 URL：`www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

結果のトラッキング URL を動的にプレビューできます。 パラメーターを追加、編集、または削除するたびに、プレビューが自動的に更新されます。

![](assets/preset-url-tracking-preview.png)

>[!NOTE]
>
>また、メールコンテンツ内のリンクに動的にパーソナライズされたトラッキングパラメーターを追加することもできます。 [詳細情報](surface-personalization.md#personalize-url-tracking)
