---
solution: Journey Optimizer
product: journey optimizer
title: 電子メールの動的サブドメインの設定
description: E メールチャネルのサーフェスレベルで動的サブドメインを設定する方法を説明します
feature: Surface, Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: 設定，電子メール，設定，サブドメイン
hide: true
hidefromtoc: true
source-git-commit: c082d9329949fd8dc68929e3934daf2d9dfdbd46
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 1%

---

# 電子メールの動的サブドメインの設定 {#surface-personalization}

E メールの表面を作成する際の、E メール設定の柔軟性と制御性を高めるため [!DNL Journey Optimizer] では、サブドメイン、ヘッダーおよび URL トラッキングパラメーターのパーソナライズされた値を定義できます。

## 動的サブドメインの追加 {#dynamic-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_surface_perso_not_available"
>title="パーソナライゼーションを利用できません"
>abstract="このサーフェスは、パーソナライゼーション属性を含まないで作成されました。 パーソナライゼーションが必要な場合の解決手順については、ドキュメントを参照してください。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain"
>title="動的サブドメインの有効化"
>abstract="E メールサーフェスを作成する場合、式エディタを使用して定義した条件に基づいて動的サブドメインを設定できます。 最大 50 個の動的サブドメインを追加できます。"

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="一部のサブドメインが使用できない可能性があります"
>abstract="フィードバックループの登録が保留中のため、現在、特定のサブドメインは選択できません。 このプロセスには、最大 10 営業日かかる場合があります。 完了したら、使用可能なすべてのサブドメインから選択できます。"

E メールサーフェスを作成する場合、特定の条件に基づいて動的サブドメインを設定できます。

例えば、国ごとに専用の電子メールアドレスからメッセージを送信する場合の法的制約がある場合、動的サブドメインを使用できます。 これにより、国ごとに複数のサーフェスを作成する代わりに、様々な国に対応する複数の送信サブドメインを持つ単一のサーフェスを作成できます。 その後、1 つのキャンペーンに統合された様々な国を基に顧客のターゲットを設定できます。

動的サブドメインを定義するには、次の手順に従います。

1. チャネルサーフェスを作成します。 [方法についてはこちらを参照](../configuration/channel-surfaces.md)

1. を選択します。 **[!UICONTROL 電子メール]** チャネル。

1. Adobe Analytics の **サブドメイン** セクションで、 **[!UICONTROL 動的サブドメイン]** オプション。

   ![](assets/surface-email-dynamic-subdomain.png)

1. 最初の **[!UICONTROL 条件]** フィールドに入力します。

1. The [式エディター](../personalization/personalization-build-expressions.md) が開きます。 この例では、次のような条件を設定します。 `Country` 次と等しい `US`.

   ![](assets/surface-email-edit-condition.png)

1. この条件に関連付けるサブドメインを選択します。 [サブドメインの詳細を表示](../configuration/about-subdomain-delegation.md)

   >[!NOTE]
   >
   >保留中のため、特定のサブドメインは現在選択できません [フィードバックループ](../reports/deliverability.md#feedback-loops) 登録。 このプロセスには、最大 10 営業日かかる場合があります。 完了したら、使用可能なすべてのサブドメインから選択できます。 <!--where FL registration happens? is it when delegating a subdomain and you're awaiting from subdomain validation? or is it on ISP side only?-->

   ![](assets/surface-email-select-subdomain.png)

   米国に基づくすべての受信者は、その国で選択されたサブドメインを使用してメッセージを受信します。つまり、関係するすべての URL（ミラーページ、トラッキング URL、購読解除リンクなど）が、そのサブドメインに基づいて入力されます。

1. 必要に応じて、他の動的サブドメインを設定します。 追加できる項目は 50 個までです。

   ![](assets/surface-email-add-dynamic-subdomain.png)

1. を選択します。 [IP プール](../configuration/ip-pools.md) サーフェスに関連付けます。 [詳細情報](email-settings.md#subdomains-and-ip-pools)

1 つ以上のダイナミックサブドメインをサーフェスに追加したら、このサーフェスの解決されたダイナミックサブドメインに基づいて、次の項目が設定されます。

* すべての URL（リソース URL、ミラーページ URL およびトラッキング URL）

* The [配信停止 URL](email-settings.md#list-unsubscribe)

* The **送信元メール** および **エラーメール** サフィックス

## ヘッダーをパーソナライズする (#personalize-header)

また、サーフェスで定義されているすべてのヘッダパラメータに対して、パーソナライゼーションを使用することもできます。

例えば、複数のブランドがある場合、1 つのサーフェスを作成し、電子メールヘッダーにパーソナライズされた値を使用できます。 これにより、異なるブランドから送信されるすべての E メールが、適切な **送信者** 名前と e メール。 同様に、受信者が **返信** 電子メールクライアントソフトウェアのボタンを使用して、 **返信先** 名前と e メールは、適切なユーザーの正しいブランドに対応しています。

パーソナライズされた変数をサーフェスヘッダーパラメータに使用するには、次の手順に従います。

1. 通常どおりにヘッダーパラメーターを定義します。 [方法についてはこちらを参照](email-settings.md#email-header)

1. 各フィールドで、「編集」アイコンを選択します。

   ![](assets/surface-email-personalize-header.png)

1. The [式エディター](../personalization/personalization-build-expressions.md) が開きます。 必要に応じて条件を定義し、変更を保存します。<!--In this example, set a condition such as -->

   >[!NOTE]
   >
   >選択できるのは **[!UICONTROL プロファイル属性]** および **[!UICONTROL ヘルパー関数]**.

1. パーソナライゼーションを追加する各パラメーターに対して、上記の手順を繰り返します。

   >[!NOTE]
   >
   >1 つ以上のダイナミックサブドメインをサーフェスに追加した場合、 **送信元メール** および **エラーメール** サフィックスは、解決された [動的サブドメイン](#dynamic-subdomains).

<!--
## Use personalized URL tracking {#personalize-url-tracking}

To use personalized URL tracking prameters, follow the steps below.

select the profile attribute of your choice from the expression editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->
