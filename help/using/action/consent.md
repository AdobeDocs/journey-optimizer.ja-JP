---
solution: Journey Optimizer
title: 同意
description: コンテンツ
feature: Actions
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: d826ad21e821235d61db499d25abf1a96ab0bec9
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 2%

---

# 同意管理（ベータ版） {#consent-management}

Adobe Experience Platformでは、顧客の同意設定に従ってマーケティングポリシーを簡単に採用および実施できます。 同意ポリシーは、Adobe Experience Platformで定義されます。 参照： [このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=en#consent-policy).

Journey Optimizerでは、これらの同意ポリシーをカスタムアクションに適用できます。 例えば、E メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外する同意ポリシーを定義できます。

>[!NOTE]
>
>この機能はプライベートベータ版としてリリースされています。 すべてのJourney Optimizerのお客様が利用できるわけではありません。

Journey Optimizerでは、同意は複数のレベルで定義されます。

* when **カスタムアクションの設定**&#x200B;に値を入力する場合、チャネルとマーケティングアクションを定義できます。 この[節](../action/consent.md#consent-custom-action)を参照してください。
* 追加時に **ジャーニーのカスタムアクション**&#x200B;に値を入力する場合、追加のマーケティングアクションを定義できます。 この[節](../action/consent.md#consent-journey)を参照してください。

## 重要な注意事項 {#important-notes}

Journey Optimizerでは、同意をカスタムアクションで利用できます。 組み込みメッセージ機能と共に使用する場合は、条件アクティビティを使用して、ジャーニー内の顧客をフィルタリングする必要があります。

同意管理を使用すると、次の 2 つのジャーニーアクティビティが分析されます。

* セグメントを読み取り：取得したセグメントが考慮されます。
* カスタムアクション：同意管理では、使用される属性 ([アクションパラメーター](../action/about-custom-action-configuration.md#define-the-message-parameters)) と、定義されたマーケティングアクション（必須のマーケティングアクションと追加のマーケティングアクション）が含まれています。

ジャーニーで使用されるその他のアクティビティは、すべて考慮されません。 セグメントの選定でジャーニーを開始した場合、そのセグメントは考慮されません。

ジャーニーで、カスタムアクションで同意ポリシーによってプロファイルが除外された場合、メッセージは送信されませんが、ジャーニーは継続します。 条件を使用する場合、プロファイルはタイムアウトとエラーパスに移動しません。

ジャーニーに配置されたカスタムアクションのポリシーを更新する前に、ジャーニーにエラーがないことを確認してください。

<!--
There are two types of latency regarding the use of consent policies:

* **User latency**: the delay from the time a profile changes a consent settings to the moment it is applied in Experience Platform. This can take up to 48h. 
* **Consent policy latency**: the delay from the time a consent policy is created or updated to the moment it is applied. This can take up to 6 hours
-->

## カスタムアクションの設定 {#consent-custom-action}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action_admin"
>title="必須のマーケティングアクションの定義"
>abstract="必須マーケティングアクションを使用すると、カスタムアクションに関連するマーケティングアクションを定義できます。 例えば、このカスタムアクションを使用して E メールを送信する場合は、「E メールのターゲティング」を選択できます。 ジャーニーで使用すると、そのマーケティングアクションに関連するすべての同意ポリシーが取得され、利用されます。 これはキャンバス上では変更できません。"

カスタムアクションを設定する場合、2 つのフィールドを同意管理に使用できます。

この **チャネル** 「 」フィールドでは、このカスタムアクションに関連するチャネルを選択できます。 **電子メール**, **SMS**&#x200B;または **プッシュ通知**. これは、 **必要なマーケティングアクション** フィールドに、選択したチャネルのデフォルトのマーケティングアクションを入力します。 次を選択した場合、 **その他**&#x200B;に値を指定しない場合、デフォルトでマーケティングアクションは定義されません。

![](assets/consent1.png)

この **必要なマーケティングアクション** では、カスタムアクションに関連するマーケティングアクションを定義できます。 例えば、このカスタムアクションを使用して E メールを送信する場合は、 **E メールのターゲティング**. ジャーニーで使用すると、そのマーケティングアクションに関連するすべての同意ポリシーが取得され、利用されます。 デフォルトのマーケティングアクションが選択されていますが、下向き矢印をクリックして、使用可能なマーケティングアクションをリストから選択できます。

![](assets/consent2.png)

クライアントのパスワードをリセットするために送信されるトランザクションメッセージなど、重要な通信の一部のタイプについては、同意ポリシーを適用しないでください。 次に、 **なし** 内 **必要なマーケティングアクション** フィールドに入力します。

カスタムアクションを設定するその他の手順について詳しくは、 [この節](../action/about-custom-action-configuration.md#consent-management).

### ジャーニーの構築 {#consent-journey}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action_canvas"
>title="必要なマーケティングアクション"
>abstract="必要なマーケティングアクションは、カスタムアクションの作成時に定義されます。 この必須マーケティングアクションは、アクションから削除したり、変更したりすることはできません。"

>[!CONTEXTUALHELP]
>id="ajo_consent_additional_marketing_action_canvas"
>title="その他のマーケティングアクション"
>abstract="必要なマーケティングアクションに加えて、別のマーケティングアクションを追加します。 両方のマーケティングアクションに関連する同意ポリシーが適用されます。"

>[!CONTEXTUALHELP]
>id="ajo_consent_refresh_policies_canvas"
>title="実行時に適用される同意ポリシーを視覚化"
>abstract="マーケティングアクションは、アクションパラメーターと個々のプロファイルの同意値を組み合わせて、ユーザーを除外する同意ポリシーを取り込みます。 更新するボタンをクリックして、これらのポリシーの最新の定義を取得します。"

カスタムアクションをジャーニーに追加する場合、いくつかのオプションで同意を管理できます。 次をクリック： **読み取り専用フィールドを表示** をクリックして、すべてのパラメータを表示します。

この **チャネル** および **必要なマーケティングアクション**&#x200B;は、カスタムアクションを設定する際に定義し、画面の上部に表示されます。 これらのフィールドは変更できません。

![](assets/consent4.png)

次の項目を定義できます。 **その他のマーケティングアクション** ：カスタムアクションのタイプを設定します。 これにより、このジャーニーでのカスタムアクションの目的を定義できます。 必要なマーケティングアクション（通常はチャネルに固有）に加えて、この特定のジャーニーのカスタムアクションに固有の追加のマーケティングアクションを定義できます。 例：ワークアウトコミュニケーション、ニュースレター、フィットネスコミュニケーション等 必要なマーケティングアクションと追加のマーケティングアクションの両方が適用されます。

![](assets/consent3.png)

次をクリック： **ポリシーを更新** ボタン（画面の下部）を使用して、このカスタムアクションで考慮するポリシーのリストを更新および確認します。 これは、ジャーニーを構築する際に、情報を提供する目的でのみ使用します。 ライブジャーニーでは、同意ポリシーは 6 時間ごとに取得され、自動的に更新されます。

![](assets/consent5.png)

<!--
The following data is taken into account for consent:

* marketing actions and additional marketing actions defined in the custom action
* action parameters defined in the custom action, see this [section](../action/about-custom-action-configuration.md#define-the-message-parameters) 
* attributes used as criteria in a segment when the journey starts with a Read segment, see this [section](../building-journeys/read-segment.md) 

>[!NOTE]
>
>Please note that there can be a latency when updating the list of policies applied, refer to this [this section](../action/consent.md#important-notes).
-->

ジャーニーでカスタムアクションを設定するその他の手順について詳しくは、 [この節](../building-journeys/using-custom-actions.md).
