---
solution: Journey Optimizer
product: journey optimizer
title: SMS チャネルの設定
description: Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を学ぶ
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
TQID: https://experienceleague.adobe.com/dO8HoRdGLuYVFN2YVjRCiFJQHmWHApROU8qz2-hKmTs
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d556b755-390a-43f0-be32-a08cf6236126
subfeature_v2:
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
  - id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a4c92daab69394e6a736517f2e23a941135f7eb4
workflow-type: tm+mt
source-wordcount: 429
ht-degree: 85%

---

# モバイル設定の基本を学ぶ {#sms-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Journey Optimizer での SMS プロバイダーの設定"
>abstract="Adobe Journey Optimizer では、SMS サービスプロバイダーを通じてテキストメッセージを送信します。 プロバイダーを選択し、API 資格情報を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_mms_api_header"
>title="Journey Optimizer での MMS プロバイダーの設定"
>abstract="Adobe Journey Optimizer では、MMS サービスプロバイダーを通じてメディアコンテンツを送信します。 プロバイダーを選択し、API 資格情報を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Journey Optimizer での SMS／MMS プロバイダーの設定"
>abstract="テキストメッセージ（SMS／MMS）を送信する前に、プロバイダー設定を Journey Optimizer と統合する必要があります。 完了したら、SMS／MMS 設定を作成する必要があります。 これらの手順は、Adobe Journey Optimizer システム管理者が実行する必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="SMS チャネル設定の作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="SMS ベンダー設定の選択"
>abstract="SMS ベンダーに設定する API 資格情報を選択します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_fuzzy_opt_out"
>title="ファジーオプトアウト"
>abstract="有効にすると、ファジーオプトアウトは、定義済みのオプトアウトキーワード（CANCIL など）に非常に類似したインバウンドメッセージを検出し、ユーザーの登録解除の意図を検証する確認返信を自動的に送信します。 定義済みのプロンプトを通じてユーザーが確認すると、登録解除されます。"

SMS、MMS または RCS を送信する前に、Adobe Journey Optimizer 環境を設定する必要があります。 これを実行するには、次の手順を実行します。

1. Journey Optimizer とプロバイダー設定を統合します。
手順は、SMS プロバイダーによって異なります。 詳細なドキュメントにアクセスするには、以下のリンクを参照してください。
   * [Infobip](mobile-configuration-infobip.md)
   * [Sinch](mobile-configuration-sinch.md)
   * [Twilio](mobile-configuration-twilio.md)
   * [カスタムプロバイダー](mobile-configuration-custom.md)
1. [Webhook の作成](mobile-webhook.md)
1. [モバイル設定の作成](mobile-configuration-surface.md)

これらの手順は、Adobe Journey Optimizer [システム管理者](../start/path/administrator.md)が実行する必要があります。

## 前提条件{#sms-prerequisites}

Adobe Journey Optimizer は現在、Adobe Journey Optimizer とは独立してテキストメッセージングサービスを提供する、サードパーティプロバイダーと統合されています。 テキストメッセージと MMS でサポートされているプロバイダーは、**Sinch**、**Twilio** および **Infobip** です。 [カスタムプロバイダー設定](mobile-configuration-custom.md)を使用して、追加のメッセージプロバイダーを設定できます。

モバイルチャネルの設定を行う前に、これらのプロバイダーのいずれかを使用してアカウントを作成し、**API トークン**&#x200B;および&#x200B;**サービス ID**&#x200B;を取得する必要があります。これには、Adobe Journey Optimizerと該当するプロバイダーとの間の接続を設定する必要があります。

テキストメッセージサービスと MMS サービスを使用した場合、該当するプロバイダーが定める追加の利用条件に同意したと見なされます。 Adobe Journey Optimizer ユーザーは、サードパーティソリューションとして、統合を通じて Sinch、Twilio、Infobip を利用できます。 サードパーティ製品について、アドビは一切関係せず、責任も負いません。 モバイルメッセージングサービスに関連する問題やサポートのリクエストについては、プロバイダーにお問い合わせください。

>[!CAUTION]
>
>SMS サブドメインにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL SMS サブドメインの管理]**&#x200B;権限が必要です。 権限について詳しくは、[このページ](../administration/high-low-permissions.md#administration-permissions)を参照してください。
>

