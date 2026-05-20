---
solution: Journey Optimizer
product: journey optimizer
title: モバイルメッセージのサブドメインの設定
description: Journey Optimizer で SMS サブドメインを設定する方法を学ぶ
role: Admin
feature: SMS, Channel Configuration
level: Intermediate
keywords: SMS, サブドメイン, 設定
exl-id: 08a546d1-060c-43e8-9eac-4c38945cc3e1
TQID: https://experienceleague.adobe.com/8-zVIM8jOX2aNPSs2OWcjtG40u4aKfCHc6aroaaBFyQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: cf64c7f6-7428-4ae5-b158-8df9771f38f4id: d2e8a157-b3b0-4143-9ff3-809bf400be56id: e30b0a1a-b594-47b8-af94-1e3a2be6df11id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a4c92daab69394e6a736517f2e23a941135f7eb4
workflow-type: tm+mt
source-wordcount: 1035
ht-degree: 93%

---

# SMS サブドメインの設定 {#sms-mms-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms_header"
>title="モバイルメッセージサブドメインのデリゲート"
>abstract="モバイルメッセージ用のサブドメインを設定します。 既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms"
>title="モバイルメッセージサブドメインのデリゲート"
>abstract="SMS設定を作成するには、このサブドメインが必要なので、モバイルメッセージに使用するサブドメインを設定する必要があります。 既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="SMS 設定の作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_config_sms_subdomain"
>title="モバイルメッセージサブドメインの選択"
>abstract="SMS 設定を作成できるようにするには、少なくとも 1 つの SMS サブドメインを、サブドメイン名リストから選択するように事前に設定しておく必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="SMS 設定の作成"

## SMS サブドメインの基本を学ぶ {#gs-sms-mms-subdomains}

SMS／MMS メッセージに追加された URL を短縮できるようにするには、[SMS 設定を作成](mobile-configuration.md#sms-prerequisites)する際に選択するサブドメインを設定する必要があります。

既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。 サブドメインのアドビへのデリゲートについて詳しくは、[この節](../configuration/delegate-subdomain.md)を参照してください。

SMS サブドメインの設定は、**すべての環境間で共有**&#x200B;されます。 したがって、SMS サブドメインを変更すると、他の本番稼働用サンドボックスにも影響します。

>[!NOTE]
>
>SMS サブドメインにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL SMS サブドメインの管理]**&#x200B;権限が必要です。 権限について詳しくは、[この節](../administration/high-low-permissions.md)を参照してください。

## 既存のサブドメインの使用 {#sms-use-existing-subdomain}

既にアドビにデリゲートされているサブドメインを使用するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューを参照して、**[!UICONTROL SMS 設定]**／**[!UICONTROL SMS サブドメイン]**&#x200B;を選択します。

1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。

   ![](assets/sms_set-up-subdomain.png)

1. 「**[!UICONTROL 設定タイプ]**」セクションから「**[!UICONTROL デリゲートサブドメインを使用]**」を選択します。

   ![](assets/sms_use-delegated-subdomain.png)

1. SMS の URL に表示する接頭辞を入力します。

   英数字とハイフンのみが使用できます。

   >[!CAUTION]
   >
   >`cdn` または `data` プレフィックスは内部使用のために予約されているので、使用しないでください。 `dmarc` や `spf` など、他の制限または予約済みのプレフィックスも使用を避ける必要があります。

1. リストからデリゲートされたサブドメインを選択します。

   既に SMS サブドメインとして使用されているサブドメインは選択できません。

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

   ![](assets/sms_prefix-and-subdomain.png)

   <!--Note that you cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your SMS messages, you will not be able to use 'marketing2.yourcompany.com'. However, multi-level subdomains being supported for SMS, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.-->

   >[!CAUTION]
   >
   >[CNAME メソッド](../configuration/delegate-subdomain.md#cname-subdomain-setup)を使用してアドビにデリゲートされたドメインを選択する場合、ホスティングプラットフォーム上に DNS レコードを作成する必要があります。 DNS レコードを生成する手順は、新しい SMS サブドメインを設定する際の手順と同じです。 [この節](#sms-configure-new-subdomain)の手順を参照してください。

1. 「**[!UICONTROL 送信]**」をクリックします。

1. 送信されると、サブドメインは&#x200B;**[!UICONTROL 処理中]**&#x200B;ステータスでリストに表示されます。 サブドメインのステータスについて詳しくは、[この節](../configuration/delegate-subdomain.md#access-delegated-subdomains)を参照してください。<!--Same statuses?-->

   そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（**最大で 4 時間**&#x200B;かかることがあります）。<!--Learn more in [this section](../configuration/delegate-subdomain.md#subdomain-validation).-->

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。 SMS チャネル設定を作成する準備が整いました。

## 新しいサブドメインを設定 {#sms-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_subdomain_dns"
>title="一致する DNS レコードを生成"
>abstract="新しい SMS サブドメインを設定するには、Journey Optimizer インターフェイスに表示されるアドビのネームサーバー情報をコピーし、ドメインホストソリューションに貼り付けて、一致する DNS レコードを生成する必要があります。 チェックが正常に完了すると、SMS 設定の作成にサブドメインを使用する準備が整います。"

新しいサブドメインを設定するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューを参照して、**[!UICONTROL SMS 設定]**／**[!UICONTROL SMS サブドメイン]**&#x200B;を選択します。

1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。

   ![](assets/sms_set-up-subdomain.png)

1. 「 **[!UICONTROL 設定タイプ]** 」セクションから「**[!UICONTROL 独自のドメインを追加]**」を選択します。

   ![](assets/sms_add-your-own-subdomain.png)

1. デリゲートするサブドメインを指定します。

   >[!CAUTION]
   >
   >* 既存の SMS サブドメインは使用できません。
   >
   >* サブドメインでは大文字は使用できません。

   無効なサブドメインをアドビにデリゲートすることはできません。 組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。

   （同じ親ドメインの）複数レベルのサブドメインがサポートされます。 例えば、「sms.marketing.yourcompany.com」を使用できます。

1. DNS サーバーに配置するレコードが表示されます。 このレコードをコピーするか、CSV ファイルをダウンロードしてから、ドメインをホストするソリューションに移動し、一致する DNS レコードを生成します。

1. DNS レコードがドメインホスティングソリューションに生成されていることを確認します。 すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](assets/sms_add-your-own-subdomain-confirm.png)

   新しい SMS サブドメインを設定すると、常に CNAME レコードを指すようになります。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。 サブドメインのステータスについて詳しくは、[この節](../configuration/delegate-subdomain.md#access-delegated-subdomains)を参照してください。<!--Same statuses?-->

サブドメインを使用してSMS メッセージを送信する前に、Adobeが必要なチェックを実行するまで待つ必要があります。これには最大4時間かかる場合があります。<!--Learn more in [this section](#subdomain-validation).--> チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。 SMS チャネル設定を作成する準備が整いました。

ホスティングソリューションで検証レコードを作成できなかった場合、サブドメインは「**[!UICONTROL 失敗]**」とマークされます。

## ガードレール {#guardrails}

現在、[!DNL Journey Optimizer] ユーザーインターフェイスでは、SMS サブドメインが設定された後にそれらを削除またはデリゲーション解除することはできません。

ただし、[!DNL Journey Optimizer] 内で機能をテストする場合は、SMS サブドメインを作成する必要がある場合があります。 テストが完了すると、UI で SMS サブドメインの削除やデリゲート解除ができないので、散乱した環境に不要な設定が生じる可能性があります。

推奨手順と考慮事項を次に示します。

<!--As an alternative action, create a new SMS subdomain for future use cases and avoid using the existing one if it is no longer needed.-->

* ベストプラクティスとして、必要なコンポーネントと設定のみを作成して、適切な環境を維持します。
* ビジネスに影響が及ぶ状況では、SMS サブドメインの削除またはデリゲーション解除を支援できる可能性のあるアドビ担当者にお問い合わせください。 [詳細情報](#undelegate-subdomain)
* さらにサポートが必要な場合は、アドビに問い合わせて、インスタンスを効果的に管理する方法を確認してください。

## サブドメインのデリゲート解除 {#undelegate-subdomain}

SMS サブドメインをデリゲートを解除する場合、デリゲート解除するサブドメインについて詳しくは、アドビ担当者にお問い合わせください。

SMS サブドメインが CNAME レコードを指している場合は、SMS サブドメイン用に作成した CNAME DNS レコードをホスティングソリューションから削除できます（ただし、元のメールサブドメインがある場合は削除しないでください）。

>[!NOTE]
>
>SMS サブドメインは、[CNAME メソッド](../configuration/delegate-subdomain.md#cname-subdomain-setup)を使用してアドビにデリゲートされた[既存のサブドメイン](#sms-use-existing-subdomain)であるか、ユーザーが設定した[新しい SMS サブドメイン](#sms-configure-new-subdomain)のいずれかであるので、CNAME レコードを指すことができます。

アドビがリクエストを処理すると、デリゲート解除したドメインはサブドメイン在庫ページに表示されなくなります。
