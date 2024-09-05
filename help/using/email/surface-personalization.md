---
solution: Journey Optimizer
product: journey optimizer
title: メール設定のパーソナライズ
description: メールのチャネル設定レベルで設定のパーソナライズされた値を定義する方法について説明します。
feature: Surface, Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: 設定, メール, 設定, サブドメイン
badge: label="限定提供"
exl-id: 1e004a76-5d6d-43a1-b198-5c9b41f5332c
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 100%

---

# メール設定のパーソナライズ {#surface-personalization}

メール設定の柔軟性と制御を高めるために、[!DNL Journey Optimizer] では、メール設定の作成時にサブドメインおよびヘッダー <!--and URL tracking parameters--> に、パーソナライズされた値を定義できます。

>[!AVAILABILITY]
>
>メール設定のパーソナライゼーションは、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。

## 動的サブドメインを追加 {#dynamic-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_surface_perso_not_available"
>title="パーソナライゼーションを利用できません"
>abstract="この設定は、パーソナライゼーション属性なしで作成されました。パーソナライゼーションが必要な場合に解決する手順については、ドキュメントを参照してください。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain"
>title="動的サブドメインを有効にする"
>abstract="メール設定を作成する際に、パーソナライゼーションエディターを使用して定義した条件に基づいて、動的サブドメインを設定できます。最大 50 個の動的サブドメインを追加できます。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="一部のサブドメインは使用できない場合があります"
>abstract="フィードバックループ登録が保留になっているので、特定のサブドメインは現在選択できません。この処理には、最大 10 営業日かかる場合があります。完了したら、使用可能なすべてのサブドメインから選択できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/configuration/delegate-subdomains/about-subdomain-delegation" text="サブドメインデリゲーションの基本を学ぶ"

メール設定を作成する際に、特定の条件に基づいて動的サブドメインを設定できます。

例えば、国別に専用のメールアドレスからメッセージを送信するという法的制約がある場合は、動的サブドメインを使用できます。これにより、国ごとに複数の設定を作成する代わりに、異なる国に対応する複数の送信サブドメインを含む単一の設定を作成できます。次に、様々な国に拠点を持つ顧客を 1 つのキャンペーンに統合してターゲットにすることができます。

メールチャネル設定で動的サブドメインを定義するには、以下の手順に従います。

1. 設定を作成する前に、ユースケースに応じて、メールの送信に使用するサブドメインを設定します。[方法についてはこちらを参照](../configuration/about-subdomain-delegation.md)

   例えば、国ごとに異なるサブドメインを使用する場合、米国に固有のサブドメインと、英国に固有のサブドメインをそれぞれ 1 つ設定します。

1. チャネル設定を作成します。[方法についてはこちらを参照](../configuration/channel-surfaces.md)

1. **[!UICONTROL メール]**&#x200B;チャネルの選択

1. **サブドメイン**&#x200B;セクションで、**[!UICONTROL 動的サブドメイン]**&#x200B;オプションを有効にします。

   ![](assets/surface-email-dynamic-subdomain.png)

1. 最初の&#x200B;**[!UICONTROL 条件]**&#x200B;フィールドの横にある「編集」アイコンを選択します。

1. [パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)が開きます。この例では、`Country`等しい`US`のような条件を設定します。

   ![](assets/surface-email-edit-condition.png)

1. この条件に関連付けるサブドメインを選択します。[サブドメインについて詳細はこちらを参照](../configuration/about-subdomain-delegation.md)

   >[!NOTE]
   >
   >[フィードバックループ](../reports/deliverability.md#feedback-loops)登録が保留中のため、特定のサブドメインは現在選択できません。この処理には、最大 10 営業日かかる場合があります。完了したら、使用可能なすべてのサブドメインから選択できます。<!--where FL registration happens? is it when delegating a subdomain and you're awaiting from subdomain validation? or is it on ISP side only?-->

   ![](assets/surface-email-select-subdomain.png)

   米国在住のすべての受信者は、その国で選択されたサブドメインを使用してメッセージを受信します。つまり、関連するすべての URL（ミラーページ、トラッキング URL、登録解除リンクなど）は、そのサブドメインに基づいて設定されます。

1. 必要に応じて他の動的サブドメインを設定します。最大 50 の項目を追加できます。

   ![](assets/surface-email-add-dynamic-subdomain.png)

   <!--Select the [IP pool](../configuration/ip-pools.md) to associate with the configuration. [Learn more](email-settings.md#subdomains-and-ip-pools)-->

1. その他すべての[メール設定](email-settings.md)を定義して、設定を[送信](../configuration/channel-surfaces.md#create-channel-surface)します。

1 つ以上の動的サブドメインを設定に追加すると、この設定で解決された動的サブドメインに基づいて、次の項目が入力されます。

* すべての URL（リソース URL、ミラーページ URL およびトラッキング URL）

* [URL の登録解除](email-settings.md#list-unsubscribe)

* **送信元メール**&#x200B;および&#x200B;**エラーメール**&#x200B;サフィックス

>[!NOTE]
>
>動的サブドメインを設定してから&#x200B;**[!UICONTROL 動的サブドメイン]**&#x200B;オプションを無効にすると、すべての動的な値が削除されます。サブドメインを選択し、設定を送信して変更を有効にします。

## ヘッダーのパーソナライズ {#personalize-header}

また、設定で定義されているすべてのヘッダーパラメーターに対してパーソナライゼーションを使用することもできます。

例えば、ブランドが複数ある場合は、単一の設定を作成し、メールヘッダーにパーソナライズされた値を使用できます。これにより、様々なブランドから送信されるすべてのメールが、正しい&#x200B;**送信元**&#x200B;の名前とメールアドレスを使用して、各顧客に送信されるようになります。同様に、受信者がメールクライアントソフトウェアの「**返信**」ボタンを押した際、**返信先**&#x200B;の名前とメールアドレスが、適切なユーザーの正しいブランドに対応するようにする必要があります。

設定ヘッダーパラメーターにパーソナライズされた変数を使用するには、次の手順に従います。

>[!NOTE]
>
>「**[!UICONTROL エラーメールのプレフィックス]**」フィールドを除く、すべての「**[!UICONTROL ヘッダーパラメーター]**」フィールドをパーソナライズできます。


1. 通常どおりにヘッダーパラメーターを定義します。[方法についてはこちらを参照](email-settings.md#email-header)

1. 各フィールドに対して、編集アイコンを選択します。

   ![](assets/surface-email-personalize-header.png)

1. [パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)が開きます。必要に応じて条件を定義し、変更を保存します。

   例えば、各受信者が自分のブランド担当者からメールを受信するなどの条件を設定します。

   >[!NOTE]
   >
   >選択できるのは、**[!UICONTROL プロファイル属性]**&#x200B;と&#x200B;**[!UICONTROL ヘルパー関数]**&#x200B;のみです。

1. パーソナライゼーションを追加する各パラメーターに対して、上記の手順を繰り返します。

>[!NOTE]
>
>1 つ以上の動的サブドメインを設定に追加した場合、**送信元メール**&#x200B;と&#x200B;**エラーメール**&#x200B;のサフィックスは、解決された[動的サブドメイン](#dynamic-subdomains)に基づいて入力されます。

<!--
## Use personalized URL tracking {#personalize-url-tracking}

To use personalized URL tracking prameters, follow the steps below.

1. Select the profile attribute of your choice from the personalization editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->

## 設定の詳細の表示 {#view-surface-details}

キャンペーンまたは設定でパーソナライズされた設定を持つ設定を使用する際、キャンペーンまたは設定内で設定の詳細を直接表示できます。次の手順に従います。

1. メールの[キャンペーン](../campaigns/create-campaign.md)または[ジャーニー](../building-journeys/journey-gs.md)を作成します。

1. 「**[!UICONTROL コンテンツを編集]**」ボタンを選択します。

1. 「**[!UICONTROL 設定の詳細を表示]**」ボタンをクリックします。

   ![](assets/campaign-view-surface-details.png)

1. **[!UICONTROL 配信設定]**&#x200B;ウィンドウが表示されます。動的サブドメインやパーソナライズされたヘッダーパラメーターを含む、すべての設定を表示できます。

   >[!NOTE]
   >
   >この画面上のすべての情報は、読み取り専用です。

1. 「**[!UICONTROL 展開]**」を選択して、動的サブドメインの詳細を表示します。

   ![](assets/campaign-delivery-settings-subdomain-expand.png)
