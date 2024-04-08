---
solution: Journey Optimizer
product: journey optimizer
title: メールの動的サブドメインの設定
description: メールチャネルサーフェスレベルで動的サブドメインを設定する方法を学ぶ
feature: Surface, Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: 設定，メール，設定，サブドメイン
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 1e004a76-5d6d-43a1-b198-5c9b41f5332c
source-git-commit: 94d39089d94b4fe42eb3fb95603426012b104517
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 1%

---

# メールサーフェスの設定をパーソナライズ {#surface-personalization}

メール設定の柔軟性と制御を高めるには、 [!DNL Journey Optimizer] では、サブドメインおよびヘッダーのパーソナライズされた値を定義できます<!--and URL tracking parameters--> メールサーフェスの作成時に使用します。

>[!AVAILABILITY]
>
>この機能は、現在、一部のユーザーのみがベータ版として利用できます。 <!--To join the beta program, contact Adobe Customer Care.-->

## 動的サブドメインを追加 {#dynamic-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_surface_perso_not_available"
>title="パーソナライゼーションを使用できません"
>abstract="このサーフェスは、パーソナライゼーション属性なしで作成されました。 パーソナライゼーションが必要な場合に解決する手順については、ドキュメントを参照してください。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain"
>title="動的サブドメインを有効にする"
>abstract="メールサーフェスを作成する際に、式エディターを使用して定義する条件に基づいて、動的なサブドメインを設定できます。 最大 50 個の動的サブドメインを追加できます。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="一部のサブドメインは使用できない場合があります"
>abstract="フィードバックループ登録が保留になっているので、特定のサブドメインは現在選択できません。 この処理には、最大 10 営業日かかる場合があります。 完了したら、使用可能なすべてのサブドメインから選択できます。"

メールサーフェスを作成する際に、特定の条件に基づいて動的サブドメインを設定できます。

例えば、国別に専用のメールアドレスからメッセージを送信するという法的制約がある場合は、動的サブドメインを使用できます。 これにより、国ごとに複数のサーフェスを作成する代わりに、異なる国に対応する複数の送信サブドメインを含む単一のサーフェスを作成できます。 次に、様々な国に拠点を持つ顧客を 1 つのキャンペーンに統合してターゲットにすることができます。

メールチャネルサーフェスで動的サブドメインを定義するには、次の手順に従います。

1. サーフェスを作成する前に、使用例に応じて、メールの送信に使用するサブドメインを設定します。 [方法についてはこちらを参照](../configuration/about-subdomain-delegation.md)

   例えば、国ごとに異なるサブドメインを使用する場合、米国に固有のサブドメインと、英国に固有のサブドメインをそれぞれ 1 つ設定します。

1. チャネルサーフェスを作成します。 [方法についてはこちらを参照](../configuration/channel-surfaces.md)

1. 「」を選択します **[!UICONTROL 電子メール]** チャネル。

1. が含まれる **Subdomain** セクションで、 **[!UICONTROL 動的サブドメイン]** オプション。

   ![](assets/surface-email-dynamic-subdomain.png)

1. 最初のの横にある「編集」アイコンを選択します **[!UICONTROL 条件]** フィールド。

1. この [式エディター](../personalization/personalization-build-expressions.md) が開きます。 この例では、次のような条件を設定します `Country` 等しい `US`.

   ![](assets/surface-email-edit-condition.png)

1. この条件に関連付けるサブドメインを選択します。 [サブドメインの詳細情報](../configuration/about-subdomain-delegation.md)

   >[!NOTE]
   >
   >保留中のため、特定のサブドメインは現在選択できません [フィードバックループ](../reports/deliverability.md#feedback-loops) 登録。 この処理には、最大 10 営業日かかる場合があります。 完了したら、使用可能なすべてのサブドメインから選択できます。 <!--where FL registration happens? is it when delegating a subdomain and you're awaiting from subdomain validation? or is it on ISP side only?-->

   ![](assets/surface-email-select-subdomain.png)

   米国に基づくすべての受信者は、その国で選択されたサブドメインを使用してメッセージを受信します。つまり、関連するすべての URL （ミラーページ、トラッキング URL、登録解除リンクなど）は、そのサブドメインに基づいて入力されます。

1. 必要に応じて他の動的サブドメインを設定します。 最大 50 個の項目を追加できます。

   ![](assets/surface-email-add-dynamic-subdomain.png)

   <!--Select the [IP pool](../configuration/ip-pools.md) to associate with the surface. [Learn more](email-settings.md#subdomains-and-ip-pools)-->

1. その他すべてを定義 [メールの設定](email-settings.md) および [submit](../configuration/channel-surfaces.md#create-channel-surface) サーフェス。

1 つ以上の動的サブドメインをサーフェスに追加すると、このサーフェスで解決された動的サブドメインに基づいて、次の項目が入力されます。

* すべての URL （リソース URL、ミラーページ URL およびトラッキング URL）

* この [url の登録解除](email-settings.md#list-unsubscribe)

* この **送信元メール** および **エラーメール** サフィックス

>[!NOTE]
>
>動的サブドメインを設定してから無効にした場合、 **[!UICONTROL 動的サブドメイン]** オプションを選択すると、すべての動的な値が削除されます。 サブドメインを選択し、サーフェスを送信して変更を有効にします。

## ヘッダーのパーソナライズ {#personalize-header}

また、サーフェスで定義されているすべてのヘッダーパラメーターに対してパーソナライゼーションを使用することもできます。

例えば、複数のブランドがある場合、1 つのサーフェスを作成し、メールヘッダーにパーソナライズされた値を使用できます。 これにより、様々なブランドから送信されるすべてのメールが、各顧客に正しくアドレス指定されるようになります **送信元** 名前とメール。 同様に、受信者がヒットした場合 **返信** メールクライアントソフトウェアのボタンで、 **返信先** 名前とメールは、適切なユーザーの正しいブランドに対応します。

サーフェスのヘッダーパラメーターにパーソナライズされた変数を使用するには、次の手順に従います。

>[!NOTE]
>
>すべてをパーソナライズできます **[!UICONTROL ヘッダーパラメーター]** フィールド（を除く） **[!UICONTROL エラーの E メール プレフィックス]** フィールド。


1. 通常どおりにヘッダーパラメーターを定義します。 [方法についてはこちらを参照](email-settings.md#email-header)

1. 各フィールドに対して、編集アイコンを選択します。

   ![](assets/surface-email-personalize-header.png)

1. この [式エディター](../personalization/personalization-build-expressions.md) が開きます。 必要な条件を定義して、変更を保存します。

   例えば、各受信者がブランドの代表者からメールを受信するなどの条件を設定します。

   >[!NOTE]
   >
   >選択できるのは **[!UICONTROL プロファイル属性]** および **[!UICONTROL ヘルパー関数]**.

1. パーソナライゼーションを追加する各パラメーターに対して、上記の手順を繰り返します。

>[!NOTE]
>
>1 つ以上の動的サブドメインをサーフェスに追加した場合、 **送信元メール** および **エラーメール** サフィックスは、解決されたに基づいて設定されます [動的サブドメイン](#dynamic-subdomains).

<!--
## Use personalized URL tracking {#personalize-url-tracking}

To use personalized URL tracking prameters, follow the steps below.

1. Select the profile attribute of your choice from the expression editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->

## サーフェスの詳細を表示 {#view-surface-details}

キャンペーンやサーフェスでパーソナライズされた設定でサーフェスを使用する場合は、キャンペーンやサーフェス内にサーフェスの詳細を直接表示できます。 次の手順に従います。

1. メールの作成 [campaign](../campaigns/create-campaign.md) または [ジャーニー](../building-journeys/journey-gs.md).

1. 「」を選択します **[!UICONTROL コンテンツを編集]** ボタン。

1. 「」をクリックします **[!UICONTROL サーフェスの詳細を表示]** ボタン。

   ![](assets/campaign-view-surface-details.png)

1. この **[!UICONTROL 配信設定]** ウィンドウが表示されます。 動的サブドメインやパーソナライズされたヘッダーパラメーターなど、すべてのサーフェス設定が表示されます。

   >[!NOTE]
   >
   >この画面に表示される情報はすべて読み取り専用です。

1. を選択 **[!UICONTROL を展開]** 動的サブドメインの詳細を表示します。

   ![](assets/campaign-delivery-settings-subdomain-expand.png)
