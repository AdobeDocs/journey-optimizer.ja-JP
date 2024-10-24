---
solution: Journey Optimizer
product: journey optimizer
title: SMS チャネルの設定
description: Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を学ぶ
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: f715fb9135c446d569a4384ce73e9e92c72cb9ff
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 99%

---

# SMS 設定の基本を学ぶ {#sms-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Journey Optimizer での SMS プロバイダーの設定"
>abstract="Adobe Journey Optimizer では、SMS サービスプロバイダーを通じてテキストメッセージを送信します。プロバイダーを選択し、API 資格情報を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_mms_api_header"
>title="Journey Optimizer での MMS プロバイダーの設定"
>abstract="Adobe Journey Optimizer では、MMS サービスプロバイダーを通じてメディアコンテンツを送信します。プロバイダーを選択し、API 資格情報を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Journey Optimizer での SMS／MMS プロバイダーの設定"
>abstract="テキストメッセージ（SMS／MMS）を送信する前に、プロバイダー設定を Journey Optimizer と統合する必要があります。完了したら、SMS／MMS 設定を作成する必要があります。これらの手順は、Adobe Journey Optimizer システム管理者が実行する必要があります。"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/communication-channels/sms/configure-sms/sms-configuration-surface" text="SMS チャネル設定の作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="SMS ベンダー設定の選択"
>abstract="SMS ベンダーに設定する API 資格情報を選択します。"

SMS または MMS を送信する前に、Adobe Journey Optimizer 環境を設定する必要があります。次の手順を実行します。

1. Journey Optimizer とプロバイダー設定を統合する
   * [Sinch を使用](sms-configuration-sinch.md)
   * [Infobip を使用](sms-configuration-infobip.md)
   * [カスタムプロバイダーを使用](sms-configuration-custom.md)
1. [SMS サーフェスの作成](sms-configuration-surface.md)

これらの手順は、Adobe Journey Optimizer [システム管理者](../start/path/administrator.md)が実行する必要があります。

## 前提条件{#sms-prerequisites}

Adobe Journey Optimizer は現在、Adobe Journey Optimizer とは独立してテキストメッセージングサービスを提供する、サードパーティプロバイダーと統合されています。テキストメッセージと MMS でサポートされているプロバイダーは、**Sinch**、**Twilio** および **Infobip** です。

SMS チャネルを設定する前に、こうしたいずれかのプロバイダーのアカウントを作成して、Adobe Journey Optimizer と該当するプロバイダー間の接続を設定するために必要な **API トークン**&#x200B;と&#x200B;**サービス ID** を取得する必要があります。

テキストメッセージサービスと MMS サービスを使用した場合、該当するプロバイダーが定める追加の利用条件に同意したと見なされます。Adobe Journey Optimizer ユーザーは、サードパーティソリューションとして、統合を通じて Sinch、Twilio、Infobip を利用できます。サードパーティ製品について、アドビは一切関係せず、責任も負いません。テキストメッセージサービス（SMS／MMS）に関する問題やサポートのリクエストについては、プロバイダーにお問い合わせください。

>[!CAUTION]
>
>SMS サブドメインにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL SMS サブドメインの管理]**&#x200B;権限が必要です。権限について詳しくは、[このページ](../administration/high-low-permissions.md#administration-permissions)を参照してください。
>

