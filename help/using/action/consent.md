---
solution: Journey Optimizer
product: journey optimizer
title: 同意ポリシーの使用
description: Adobe Experience Platform の同意ポリシーの使用方法を学ぶ
feature: Journeys, Actions, Custom Actions, Privacy, Consent Management
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: ポリシ, ガバナンス, プラットフォーム, Healthcare Shield, 同意
exl-id: 01ca4b3e-3778-4537-81e9-97ef92c9aa9e
source-git-commit: f61bd7d8d03ba2fd4e92c277f0cbfb730b3703c1
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 100%

---

# 同意ポリシーの使用 {#consent-management}

データは、組織または法規制によって定義された使用制限の対象となる場合があります。したがって、Journey Optimizer 内のデータ操作が、[データ使用ポリシー](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ja){target="_blank"}に準拠していることを確認することが重要です。これらのポリシーは、データに対して実行できる[マーケティングアクション](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ja#marketing-actions){target="_blank"}を定義する Adobe Experience Platform ルールです。

使用可能なデータ使用ポリシーの 1 つのタイプは、**同意ポリシー**&#x200B;です。顧客の同意の環境設定に従ってマーケティングポリシーを簡単に採用および実施できます。[詳しくは、ポリシーの適用を参照してください](https://experienceleague.adobe.com/docs/experience-platform/data-governance/enforcement/auto-enforcement.html?lang=ja){target="_blank"}

>[!IMPORTANT]
>
>同意ポリシーは、現在、Adobe **Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

例えば、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外するために、Experience Platform で[同意ポリシーを作成](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#consent-policy){target="_blank"}できます。

* ネイティブのアウトバウンドチャネル（メール、プッシュ、SMS、ダイレクトメール）の場合、ロジックは次のとおりです。

   * デフォルトでは、プロファイルがマーケティング組織からの通信の受信をオプトアウトした場合、対応するプロファイルは以降の配信から除外されます。

   * Adobe **Healthcare Shield** または **Privacy and Security Shield** を使用している場合は、デフォルトのロジックを上書きするカスタム同意ポリシーを作成できます。例えば、オプトインしたすべての個人にのみメールメッセージを送信するポリシーを定義できます。カスタムポリシーがない場合、デフォルトのポリシーが適用されます。

  カスタムポリシーを適用するには、そのポリシーにマーケティングアクションを定義して、チャネル設定に関連付ける必要があります。[詳細情報](#surface-marketing-actions)

ジャーニーレベルでは、同意ポリシーをカスタムアクションに適用できます。

* **カスタムアクションの設定**&#x200B;時、チャネルとマーケティングアクションを定義できます。[詳細情報](#consent-custom-action)
* **ジャーニーのカスタムアクション**&#x200B;の追加時に、追加のマーケティングアクションを定義できます。[詳細情報](#consent-journey)

## チャネル設定を介した同意ポリシーの活用 {#surface-marketing-actions}

[!DNL Journey Optimizer] では、同意は Experience Platform [同意スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja){target="_blank"}で処理されます。デフォルトでは同意フィールドの値は空で、通信内容の受信に同意したものとして扱われます。このデフォルト値はオンボーディングの際に、[こちら](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values){target="_blank"}に一覧表示されている値の 1 つに変更できます。

同意フィールドの値を変更するには、マーケティングアクションとそのアクションの実行条件を定義するカスタム同意ポリシーを作成します。[マーケティングアクションの詳細情報](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ja#marketing-actions){target="_blank"}

例えば、メール通信の受信に同意したプロファイルのみをターゲットにする同意ポリシーを作成する場合は、次の手順に従います。

1. 組織が Adobe **Healthcare Shield** または **Privacy and Security Shield** アドオン製品を購入していることを確認します。[詳細情報](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html?lang=ja){target="_blank"}

1. Adobe Experience Platform で、（**[!UICONTROL プライバシー]**／**[!UICONTROL ポリシー]**&#x200B;メニューから）カスタムポリシーを作成します。[方法についてはこちらを参照](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#create-policy){target="_blank"}

   <!--![](assets/consent-policy-create.png)-->

1. **[!UICONTROL 同意ポリシー]**&#x200B;のタイプを選択し、次のように条件を設定します。[同意ポリシーの設定方法についてはこちらを参照](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#consent-policy){target="_blank"}

   1. 「**[!UICONTROL If]**」セクションで、デフォルトの&#x200B;**[!UICONTROL メールターゲティング]**&#x200B;マーケティングアクションを選択します。

      <!--![](assets/consent-policy-marketing-action.png)-->

      >[!NOTE]
      >
      >アドビが標準で提供するコアマーケティングアクションの一覧については、[この表](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ja#core-actions){target="_blank"}を参照してください。カスタムマーケティングアクションを作成する手順について詳しくは、[この節](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#create-marketing-action){target="_blank"}を参照してください。

   1. マーケティングアクションが適用されたときの動作を選択します。この例では、「**[!UICONTROL メールマーケティングの同意]**」を選択します。

   ![](assets/consent-policy-then.png)

1. このポリシーを保存して[有効](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#enable){target="_blank"}にします。

1. Journey Optimizer で、メールサーフェスを作成します。[方法についてはこちらを参照](../configuration/channel-surfaces.md#create-channel-surface)

1. メール設定の詳細で、「**[!UICONTROL メールターゲティング]**」マーケティングアクションを選択します。

   ![](assets/surface-marketing-action.png)

顧客の環境設定に従うために、そのマーケティングアクションに関連付けられているすべての同意ポリシーが自動的に活用されます。

そのため、この例では、キャンペーンまたはジャーニーでこの設定を使用する[メール](../email/create-email.md)は、マーケティング組織からのメールの受信に同意したプロファイルにのみ送信されます。メール通信の受信に同意しないプロファイルは除外されます。

## カスタムアクションを介した同意ポリシーの活用 {#journey-custom-actions}

### 重要な注意事項 {#important-notes}

Journey Optimizer では、同意をカスタムアクションでも活用できます。組み込みメッセージ機能と共に使用する場合は、条件アクティビティを使用して、ジャーニー内の顧客をフィルタリングする必要があります。

同意管理を使用すると、2 つのジャーニーアクティビティが分析されます。

* オーディエンスを読み取り：取得したオーディエンスが考慮されます。
* カスタムアクション：同意管理では、使用される属性（[アクションパラメーター](../action/about-custom-action-configuration.md#define-the-message-parameters)）と、定義されたマーケティングアクション（必須のマーケティングアクションと追加のマーケティングアクション）が考慮されます。
* 標準の結合スキーマを使用するフィールドグループに属する属性はサポートされていません。 これらの属性は、インターフェイスで非表示になります。 別のスキーマを使用して別のフィールドグループを作成する必要があります。
* 同意ポリシーは、マーケティングアクション（必須または追加）がカスタムアクションレベルで設定されている場合にのみ適用されます。

ジャーニーで使用されるその他のアクティビティは、すべて考慮されません。オーディエンスの選定でジャーニーを開始した場合、そのオーディエンスは考慮されません。

ジャーニー中に、カスタムアクションの同意ポリシーによってプロファイルが除外された場合、メッセージは送信されませんが、ジャーニーは継続します。条件を使用する場合、プロファイルはタイムアウトとエラーパスに移動しません。

ジャーニーに配置されたカスタムアクションのポリシーを更新する前に、ジャーニーにエラーがないことを確認してください。

<!--
There are two types of latency regarding the use of consent policies:

* **User latency**: the delay from the time a profile changes a consent settings to the moment it is applied in Experience Platform. This can take up to 48h. 
* **Consent policy latency**: the delay from the time a consent policy is created or updated to the moment it is applied. This can take up to 6 hours
-->

### カスタムアクションの設定 {#consent-custom-action}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action"
>title="必須のマーケティングアクションの定義"
>abstract="必須のマーケティングアクションを使用すると、カスタムアクションに関連するマーケティングアクションを定義できます。例えば、このカスタムアクションを使用してメールを送信する場合は、メールのターゲティングを選択できます。ジャーニーで使用すると、そのマーケティングアクションに関連するすべての同意ポリシーが取得され、活用されます。これはキャンバス上では変更できません。"

カスタムアクションを設定する場合、2 つのフィールドを同意管理に使用できます。

「**チャネル**」フィールドでは、**メール**、**SMS** または&#x200B;**プッシュ通知**&#x200B;などの、このカスタムアクションに関連するチャネルを選択できます。これにより、「**必須のマーケティングアクション**」フィールドに、選択したチャネルのデフォルトのマーケティングアクションが事前に入力されます。**その他**&#x200B;を選択した場合、デフォルトでマーケティングアクションは定義されません。

![](assets/consent1.png)

**必須のマーケティングアクション**&#x200B;を使用すると、カスタムアクションに関連するマーケティングアクションを定義できます。例えば、このカスタムアクションを使用してメールを送信する場合は、**メールのターゲティング**&#x200B;を選択できます。ジャーニーで使用すると、そのマーケティングアクションに関連するすべての同意ポリシーが取得され、活用されます。デフォルトのマーケティングアクションが選択されていますが、下向き矢印をクリックして、使用可能なマーケティングアクションをリストから選択できます。

![](assets/consent2.png)

クライアントのパスワードをリセットするために送信されるトランザクションメッセージなど、重要な通信の一部の種類については、同意ポリシーを適用しないでください。次に、「**必須のマーケティングアクション**」フィールドで「**なし**」を選択します。

カスタムアクションを設定するその他の手順について詳しくは、[この節](../action/about-custom-action-configuration.md#consent-management)を参照してください。

### ジャーニーの構築 {#consent-journey}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action_canvas"
>title="必須のマーケティングアクション"
>abstract="必須のマーケティングアクションは、カスタムアクションの作成時に定義されます。この必須マーケティングアクションは、アクションから削除したり、変更したりすることはできません。"

>[!CONTEXTUALHELP]
>id="ajo_consent_additional_marketing_action_canvas"
>title="追加のマーケティングアクション"
>abstract="必須のマーケティングアクションに加えて、別のマーケティングアクションを追加します。両方のマーケティングアクションに関連する同意ポリシーが適用されます。"

>[!CONTEXTUALHELP]
>id="ajo_consent_refresh_policies_canvas"
>title="実行時に適用される同意ポリシーの視覚化"
>abstract="マーケティングアクションは、アクションパラメーターと個々のプロファイルの同意値を組み合わせて、ユーザーを除外する同意ポリシーを取り込みます。更新するボタンをクリックして、これらのポリシーの最新の定義を取得します。"

カスタムアクションをジャーニーに追加する場合、いくつかのオプションで同意を管理できます。「**読み取り専用フィールドを表示**」をクリックして、すべてのパラメーターを表示します。

カスタムアクションを設定する際に定義した&#x200B;**チャネル**&#x200B;および&#x200B;**必須のマーケティングアクション**&#x200B;は、画面の上部に表示されます。これらのフィールドは変更できません。

![](assets/consent4.png)

**追加のマーケティングアクション**&#x200B;を定義して、カスタムアクションのタイプを設定できます。これにより、このジャーニーでのカスタムアクションの目的を定義できます。必須のマーケティングアクション（通常はチャネルに固有）に加えて、この特定のジャーニーのカスタムアクションに固有の追加のマーケティングアクションを定義できます。例：ワークアウトコミュニケーション、ニュースレター、フィットネスコミュニケーション等必須のマーケティングアクションと追加のマーケティングアクションの両方が適用されます。

![](assets/consent3.png)

画面下部の「**ポリシーの更新**」ボタンをクリックして、このカスタムアクションで考慮するポリシーのリストを更新および確認します。これは、ジャーニーを構築する際に、情報を提供する目的でのみ使用します。ライブジャーニーでは、同意ポリシーは 6 時間ごとに取得され、自動的に更新されます。

![](assets/consent5.png)

<!--
The following data is taken into account for consent:

* marketing actions and additional marketing actions defined in the custom action
* action parameters defined in the custom action, see this [section](../action/about-custom-action-configuration.md#define-the-message-parameters) 
* attributes used as criteria in a segment when the journey starts with a Read segment, see this [section](../building-journeys/read-audience.md) 

>[!NOTE]
>
>Please note that there can be a latency when updating the list of policies applied, refer to this [this section](../action/consent.md#important-notes).
-->

ジャーニーでカスタムアクションを設定するその他の手順について詳しくは、[この節](../building-journeys/using-custom-actions.md)を参照してください。