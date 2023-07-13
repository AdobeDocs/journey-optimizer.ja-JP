---
solution: Journey Optimizer
product: journey optimizer
title: オプトアウトの管理
description: オプトアウトとプライバシーを管理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 43%

---

# オプトアウトの管理 {#consent}

ブランドからの連絡を登録解除する機能を受信者に提供することは、法的要件であり、この選択を確実に行うためにも必要です。適用される法律について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target="_blank"}を参照してください。

**なぜそれが重要なのでしょうか？**

* これらの規制に準拠できないと、ブランドに法規制上のリスクが生じます。
* この機能を使用すると、未承諾の通信を受信者に送信して、メッセージがスパムと見なされたり、ブランドの評判が損なわれたりする危険性を避けることができます。

## ジャーニーとキャンペーンでの購読解除の管理 {#opt-out-ajo}

ジャーニーやキャンペーンからメッセージを送信する場合は、顧客が今後の通信を登録解除できるようにする必要があります。登録解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。

**[!DNL Journey Optimizer]** には、メールと SMS メッセージでオプトアウトを管理する方法が用意されていますが、プッシュ通知では、受信者が自分のデバイスを介して登録解除できるので、顧客側でのアクションは不要です。例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。同様に、モバイルオペレーティングシステムから通知設定を変更することもできます。

Journey Optimizer のメールと SMS メッセージでオプトアウトを管理する方法について、以下の節で説明します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../email/email-opt-out.md">
<img alt="リード" src="../assets/do-not-localize/privacy-email-optout.jpeg" width="50%">
</a>
<div><a href="../email/email-opt-out.md"><strong>メールオプトアウトの管理</strong>
</div>
<p>
</td>
<td>
<a href="../sms/sms-opt-out.md">
<img alt="低頻度" src="../assets/do-not-localize/privacy-sms-opt-out.jpeg" width="50%">
</a>
<div>
<a href="../sms/sms-opt-out.md"><strong>SMS オプトアウトの管理</strong></a>
</div>
<p></td>
</tr></table>

>[!NOTE]
>
>[!DNL Journey Optimizer] では、同意は Experience Platform [同意スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja){target="_blank"}. By default, the value for the consent field is empty and treated as consent to receive your communications. You can modify this default value while onboarding to one of the possible values listed [here](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values){target="_blank"}で処理されます。

## パーソナライゼーションの同意の実装 {#opt-out-personalization}

顧客は、パーソナライズされたコンテンツの表示をオプトアウトすることもできます。あるプロファイルがパーソナライゼーションからオプトアウトされたら、そのデータがパーソナライゼーションに使用されていないことを確認し、パーソナライズされたコンテンツをフォールバックバリアントに置き換える必要があります。

### 意思決定管理の場合

オファーを活用する場合、パーソナライゼーション環境設定は、[Decisioning](../offers/api-reference/offer-delivery-api/decisioning-api.md) API リクエストまたは [Edge Decisioning](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md) API リクエストから使用される[決定範囲](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)に自動的に実装されません。この場合、パーソナライゼーションの同意を手動で実施する必要があります。これを行うには、以下の手順に従います。

>[!NOTE]
>
>[!DNL Journey Optimizer] で作成したチャネルで使用される決定範囲は、属するジャーニーまたはキャンペーンからのこの要件を満たします。

1. の作成 [Adobe Experience Platformオーディエンス](../audience/access-audiences.md) の使用 [セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja){target="_blank"} また、 **[!UICONTROL コンテンツをパーソナライズ=はい（オプトイン）]** パーソナライゼーションに同意したユーザーをターゲットにする

   ![](assets/perso-consent-od-audience.png)

1. を作成する際に [決定](../offers/offer-activities/create-offer-activities.md)、決定範囲を追加し、パーソナライズされたオファーを含む各評価条件コレクションに対して、このオーディエンスに基づいて実施要件の制約を定義します。

   ![](assets/perso-consent-od-audience-decision.png)

1. パーソナライズされたコンテンツを含まない[フォールバックオファー](../offers/offer-library/creating-fallback-offers.md)を作成します。

1. パーソナライズされていないフォールバックオファーを決定に[割り当てます](../offers/offer-activities/create-offer-activities.md#add-fallback)。

   ![](assets/perso-consent-od-audience-fallback.png)

1. [決定のレビューと保存](../offers/offer-activities/create-offer-activities.md#review)を行います。

ユーザーが以下の条件を満たしている場合：

* パーソナライゼーションに同意した場合、決定範囲によってそのプロファイルに最適なオファーが決定されます。

* パーソナライゼーションに同意していない場合、対応するプロファイルは評価条件に含まれるオファーの対象外となるので、パーソナライズされていないフォールバックオファーを受信します。

>[!NOTE]
>
>[データモデリング](../offers/ranking/ai-models.md)でプロファイルデータを使用するための同意は、[!DNL Journey Optimizer] ではまだサポートされていません。

## 式エディター内

<!--Expressions Editor while personalizing images, text, subject line  ( Segment in Campaigns) - UI and Headless -->

この [式エディター](../personalization/personalization-build-expressions.md) メッセージの配信には関係ないので、自身は同意の確認や実施を実行しません。

ただし、右ベースのアクセス制御ラベルを使用すると、パーソナライゼーションに使用できるフィールドを制限できます。 この [メッセージプレビュー](../email/preview.md#preview-email) および [e メールレンダリングサービス](../email/preview.md#email-rendering) は、機密情報で識別されるフィールドをマスクします。

>[!NOTE]
>
>詳しくは、 [この節](../administration/object-based-access.md).


In [!DNL Journey Optimizer] キャンペーンの場合、同意ポリシーは次のように適用されます。

* オーディエンスの作成の一環として同意ポリシーの定義を含めると、キャンペーン用に選択されたオーディエンスが既に存在していることを確認できます **同意条件に一致しないプロファイルを除外**.

* [!DNL Journey Optimizer] がチャネルレベルでに対して一般的な同意チェックを実行します。 **プロファイルがオプトインしたことを確認する** 対応するチャネルでマーケティングコミュニケーションを受け取る。

  >[!NOTE]
  >
  >この [!DNL Journey Optimizer] 現時点では、campaign オブジェクト自体は追加の同意ポリシー実施チェックを実行しません。

キャンペーンでパーソナライゼーションの同意を手動で実施するには、次のいずれかのオプションに従います。

### セグメントルールビルダーの使用

セグメントルールビルダーを使用して、オプトアウトプロファイルを含むオーディエンスを作成できます。

1. の作成 [Adobe Experience Platformオーディエンス](../audience/access-audiences.md) の使用 [セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja){target="_blank"}.

   ![](assets/perso-consent-audience-build-rule.png)

1. 次のようなプロファイル属性を選択します。 **[!UICONTROL コンテンツをパーソナライズ=いいえ（オプトアウト）]** パーソナライゼーションに同意しなかったユーザーを除外する

   ![](assets/perso-consent-audience-no.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

これで、このオーディエンスを使用して、パーソナライゼーションに同意していないプロファイルをキャンペーンから除外できます。

### 構成ワークフローでの分割アクティビティの使用

また、構成ワークフローに分割アクティビティを追加することで、パーソナライゼーションの同意チェックをオーディエンスに追加できます。

1. オーディエンスを作成するには、 **[!UICONTROL オーディエンスを作成]** オプション。 [構成ワークフローの作成に関する詳細](../audience/create-compositions.md)

   ![](assets/perso-consent-audience-compose.png)

1. 右側の専用ボタンを使用して、開始オーディエンスを追加します。

1. 「+」アイコンをクリックし、「 **[!UICONTROL 分割]** をクリックして、分割オーディエンスを作成します。 [分割アクティビティの詳細を説明します](../audience/composition-canvas.md#split)

   ![](assets/perso-consent-audience-split.png)

1. 選択 **[!UICONTROL 属性の分割]** を右側のウィンドウの分割タイプとして使用します。

   ![](assets/perso-consent-audience-attribute-split.png)

1. 横の鉛筆アイコンをクリックします。 **[!UICONTROL 属性]** 持ち出すフィールド **[!UICONTROL プロファイル属性を選択]** ウィンドウ

1. パーソナライゼーションの同意属性 (`profile.consents.personalize.content.val`) をクリックし、選択します。

   ![](assets/perso-consent-audience-consent-attribute.png)

1. **[!UICONTROL パス 1]** は、パーソナライズされていないオーディエンスになります。 関連するラベルを選択します。

1. この中から適切な値を選択します。 [リスト](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values){target="_blank"}.

   この場合、 `n` を使用することで、ユーザーはパーソナライゼーションに対するデータの使用に同意しないことを示します。

   ![](assets/perso-consent-audience-path-1-n.png)

1. 他の選択値に対しては、別のパスを作成できます。 残りのパスを削除してオンにすることもできます **[!UICONTROL その他のプロファイル]** 選択値を持たない他のすべてのプロファイルを含めるには `n`.

1. 終了したら、「 **[!UICONTROL オーディエンスを保存]** を設定します。 パスごとに 1 つのオーディエンスがAdobe Experience Platformに保存されます。

1. 完了したら、構成ワークフローを公開します。

これで、このオーディエンスを使用して、パーソナライゼーションに同意していないプロファイルをキャンペーンから除外できます。

>[!NOTE]
>
>パーソナライゼーションに対する同意を得ていないオーディエンスを作成し、キャンペーンでこのオーディエンスを選択した場合、パーソナライゼーションツールは引き続き使用できます。 パーソナライゼーションを受け取るべきでないオーディエンスを扱う場合、パーソナライゼーションツールを使用すべきでないことを理解するのは、マーケティングユーザー次第です。
