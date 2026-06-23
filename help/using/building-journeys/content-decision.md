---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツ決定アクティビティ
description: コンテンツ決定アクティビティについて説明します
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: アクティビティ, 決定, コンテンツ決定, 決定ポリシー, キャンバス, ジャーニー
exl-id: 6188644a-6a3b-4926-9ae9-0c6b42c96bae
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/1tZd4-NYBxu1iuUZGMKQ6DIXFxRpX0FARTEPpWqxzjY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
  - id: cfba2953-2ce9-4b00-a00c-71cd338ae63f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: b5d14f7b40933f110ff666db858e976e5de711db
workflow-type: tm+mt
source-wordcount: 1913
ht-degree: 49%

---

# コンテンツ決定アクティビティ {#content-decision}

>[!BEGINSHADEBOX]

**このページ：** コンテンツ決定アクティビティを使用して、ジャーニーにパーソナライズされたオファーを含め、対象プロファイルに配信する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Journey Optimizer]を使用すると、ジャーニーキャンバスの専用の&#x200B;**コンテンツ決定** アクティビティを通じて、ジャーニーにオファーを含めることができます。 次に、他のアクティビティ（[カスタムアクション](../action/about-custom-action-configuration.md)など）をジャーニーに追加して、パーソナライズされたオファーでオーディエンスをターゲットにすることができます。

>[!NOTE]
>
>コンテンツ決定アクティビティの出力は、ネイティブチャネルアクティビティでは使用できません。

この機能を活用するには、[コンテンツ決定アクティビティ](#add-content-decision-activity)を追加して、実施要件を満たすプロファイルに提示するオファーを定義するジャーニーを作成します。

次に、コンテンツ決定アクティビティの出力は、以下の用途で使用できます。

* 取得したオファーに基づいてプロファイルを特定のパスに移動する条件[&#128279;](#add-condition-activity)を持つOptimize アクティビティ。

* [カスタムアクション](#add-custom-action)：これらのオファーを外部システムに送信できます。

## コンテンツ決定アクティビティの設定 {#add-content-decision-activity}

コンテンツ決定アクティビティを使用すると、[!DNL Journey Optimizer] 決定から最適な項目を選択し、適切なオーディエンスに配信できるようにする決定ポリシーを定義できます。

<!--Their goal is to select the best offers for each profile, while the campaign/journey authoring allows you to indicate how the selected decision items should be presented, including which item attributes to be included in the message.-->

**[!UICONTROL コンテンツ決定]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーケストレーション]**&#x200B;カテゴリを展開し、**[!UICONTROL コンテンツ決定]**&#x200B;アクティビティをキャンバスにドロップします。

   ![ジャーニーにコンテンツ決定を追加](assets/journey-content-decision.png){width=100%}

1. オプションで、アクティビティにラベルと説明を追加します。

1. 「**[!UICONTROL 決定ポリシーを追加]**」をクリックします。 [決定ルールの詳細情報](../experience-decisioning/create-decision.md)

   >[!NOTE]
   >
   >決定ポリシーを作成するには、決定権限が必要です。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md#steps)

1. 返される項目の数を選択します。 例えば、「2」を選択した場合、最適な 2 つの実施要件を満たすオファーが表示されます。 「**[!UICONTROL 次へ]**」をクリックします。

1. 「**[!UICONTROL 戦略シーケンス]**」セクションでは、決定ポリシーと共に提示する決定項目や選択戦略を選択します。 [詳細情報](../experience-decisioning/create-decision.md#create-decision)

1. 必要に応じて、評価順序を並べ替えます。

   複数の決定項目や戦略を追加すると、順番に評価され、各オブジェクトまたはオブジェクトのグループの左側に数字で示されます。 デフォルトのシーケンスを変更するには、オブジェクトやグループをドラッグ＆ドロップして、任意の順序に並べ替えることができます。 [詳細情報](../experience-decisioning/create-decision.md#create-decision)

1. （オプション）フォールバックオファーを追加します。 [詳細情報](../experience-decisioning/create-decision.md#create-decision)

1. 決定ポリシーをレビューして保存します。

   ![決定ポリシーの概要](assets/journey-content-decision-policy.png){width=70%}<!--reshoot or change screen-->

これで、このコンテンツ決定アクティビティの出力をジャーニーで活用する準備が整いました。

## ガードレールと制限 {#guardrails}

**同意ポリシー**

* 同意ポリシーの更新が有効になるまで最大 48 時間かかります。 決定ポリシーが、最近更新された同意ポリシーに関連付けられた属性を参照している場合、変更は直ちに適用されません。

* 同様に、同意ポリシーの対象となる新しいプロファイル属性が決定ポリシーに追加された場合、その属性は使用可能になりますが、関連付けられた同意ポリシーは、遅延が経過するまで適用されません。

* 同意ポリシーは、Adobe Healthcare Shield または Privacy and Security Shield アドオンを導入している組織でのみ使用できます。

## コンテンツ決定アクティビティの出力の使用 {#use-content-decision-output}

コンテンツ決定の出力は、複数のジャーニーアクティビティで使用できます。 例えば、条件[&#128279;](#add-condition-activity)を含む最適化アクティビティを使用して、取得されたオファー数に基づいて、プロファイルをジャーニーの特定の分岐に移動できます。

また、コンテンツ決定アクティビティからのオファーを外部システムと共有することを目的に、[カスタムアクション](#add-custom-action)をジャーニーに追加することもできます。

### 最適化アクティビティで（条件付きメソッド） {#add-condition-activity}

コンテンツ決定アクティビティの出力を活用するには、**[!UICONTROL 最適化]** アクティビティを追加し、**[!UICONTROL 条件]** メソッドを選択し、それらのオファーのデータを使用してプロファイルを特定のパスに移動する式を定義します。 次の手順に従います。 その他の条件タイプとオプションについては、[条件](conditions.md)を参照してください。

1. **[!UICONTROL オーケストレーション]** カテゴリから、**[!UICONTROL 最適化]** アクティビティをキャンバスにドロップします。 [詳細情報](optimize.md)

1. （オプション）定義する最初の式に対応する **[!UICONTROL Path1]** の名前を、より関連性の高いラベルに変更します。

1. この最初のパスでは、「**[!UICONTROL 式]**」フィールド内をクリックするか、編集アイコンを使用して式を追加します。

   ![条件を追加し、式を編集](assets/journey-content-decision-condition.png){width=80%}

1. 開いたポップアップウィンドウで、**[!UICONTROL 詳細設定モード]**&#x200B;に切り替えて、[高度な式エディター](expression/expressionadvanced.md)を使用します。

   >[!CAUTION]
   >
   >コンテンツ決定ノードの出力は、**[!UICONTROL 詳細設定モード]**&#x200B;でのみ使用できます。

1. **[!UICONTROL コンテキスト]**&#x200B;ノードを展開し、決定ポリシーに移動して、[オファーカタログスキーマ](../experience-decisioning/catalogs.md#access-catalog-schema)で使用可能なすべての属性を表示します。

   ![条件を追加し、式を編集](assets/journey-content-decision-context.png)

   >[!NOTE]
   >
   >属性に定義された制限されたラベルは、DULEまたは同意のポリシー違反につながる可能性があります。 これは、決定ルールで使用されるジャーニーエクスペリエンスイベントおよび[&#x200B; オファースキーマ &#x200B;](../experience-decisioning/catalogs.md#access-catalog-schema)に適用されます。 データガバナンスポリシーについて詳しくは、[この節](../action/action-privacy.md)を参照してください。

1. ジャーニーにエントリするプロファイルに対してオファーが返されたかどうかを確認するには、構文 `listSize(@decision{ContentdecisionName.items})>0` で [listSize](functions/list-functions.md#listSize) 関数を使用します

   >[!NOTE]
   >
   >この例では、`Name` はジャーニーに追加したコンテンツ決定のラベルです。

   ![リストを使用して条件を追加](assets/journey-content-decision-condition-list.png)

1. 「**[!UICONTROL OK]**」をクリックします。

1. 必要に応じて、他の条件を定義するパスを追加します。

   また、「**[!UICONTROL 上記以外の事例のパスを表示]**」をオンにして、最初の条件を満たさないプロファイルの別のパスを作成することもできます。<!--These profiles will then exit the journey if no other activity is added in that path.-->

1. 条件アクティビティを保存します。

### カスタムアクションの場合 {#add-custom-action}

コンテンツ決定アクティビティの出力を活用するには、定義したオファーを外部システムと共有するカスタムアクションをジャーニーに追加します。 次の手順に従います。

1. カスタムアクションをジャーニーに追加します。 [詳細情報](../action/about-custom-action-configuration.md)

1. アクションのラベルを入力します。

1. 「**[!UICONTROL リクエストパラメーター]**」セクションで、取得したオファーの属性にマッピングするパラメーターを選択します。

   編集可能なテキストフィールド内をクリックし、取得したオファーの属性にマッピングするパラメーターを選択します。

   ![カスタムアクションのリクエストパラメーターを編集](assets/journey-content-decision-custom-action-param.png)

1. 開いたポップアップウィンドウで、**[!UICONTROL 詳細設定モード]**&#x200B;に切り替えます。 [高度な式エディター](expression/expressionadvanced.md)で、**[!UICONTROL コンテキスト]**&#x200B;ノードを展開して、すべての決定ポリシー項目を表示します。

   >[!CAUTION]
   >
   >コンテンツ決定ノードの出力は、**[!UICONTROL 詳細設定モード]**&#x200B;でのみ使用できます。

1. `items`配列を使用して、[&#x200B; オファーカタログスキーマ &#x200B;](../experience-decisioning/catalogs.md#access-catalog-schema)を参照します。 例えば、最初に取得したオファーの `itemName` と、2 番目に取得したオファーの `itemName` を使用します。

   ![決定ポリシーを含むカスタムアクションのリクエストパラメーター](assets/journey-content-decision-custom-action-param-ex.png)

1. 「**[!UICONTROL OK]**」をクリックして式を保存します。

1. カスタムアクション設定を&#x200B;**[!UICONTROL 保存]**&#x200B;します。

### エンドツーエンドの例 {#use-case}

上記で説明したように、条件アクティビティとカスタムアクションを組み合わせたコンテンツ決定アクティビティを使用するジャーニーの完全な例を以下に示します。

![ジャーニーを完了](assets/journey-content-decision-full-journey.png)

<!--When all activities are properly configured and saved, [publish](publish-journey.md) your journey.-->

ジャーニーを[アクティブ化](publish-journey.md)すると、次の操作が行われます。

<!--
* Profiles who enter the journey and are eligible for at least one offer are targeted by the custom action.

* If no offer is returned for a profile, they are excluded from the custom action.
-->

1. プロファイルがそのオーディエンスを選定するたびに、そのプロファイルはジャーニーにエントリします。

1. コンテンツ決定アクティビティを通じて、[!DNL Journey Optimizer] は各プロファイルに関連するオファーを取得します。

1. 1 つ以上のオファーを取得したプロファイルのみが、ジャーニーを続行します（「実施要件を満たすプロファイル」パス経由）。

1. 条件が満たされると、対応するオファーがカスタムアクションを通じて外部システムに送信されます。

## ステップイベントでのデータ決定 {#decisioning-step-events}

ジャーニーでコンテンツ決定アクティビティが実行されると、ジャーニーステップイベントで決定データが使用可能になります。 このデータには、取得された項目と決定方法に関する詳細な情報が記載されています。

コンテンツ決定アクティビティごとに、ステップイベントには、最上位レベルの決定データ（**exdRequestID**&#x200B;および&#x200B;**propositionEventType**&#x200B;など）と&#x200B;**提案**&#x200B;の配列が含まれます。 各提案には、**id**、**scopeDetails** （決定プロバイダー、相関ID、決定ポリシーを含む）および&#x200B;**items**&#x200B;配列が含まれます。 各項目には次のものが含まれます。

* **id**：項目の一意のID
* **name**：項目の名前
* **スコア**：項目に割り当てられたスコア
* **itemSelection**：決定が行われた方法と項目の取得方法に関するデータ。次のデータを含みます。
   * **selectionDetail**：使用される選択戦略に関する情報
   * **rankingDetail**: ランキングプロセスに関する情報（戦略、アルゴリズム、ステップ、トラフィックタイプ）

**ステップイベントでのデータ決定の例：**

```json
"decisioning": {
  "exdRequestID": "8079d2bb-a8b2-4ecf-b9e7-32923dd6ad4e",
  "propositions": [
    {
      "id": "f475cb21-0842-44da-b0eb-70766ba53464",
      "scopeDetails": {
        "decisionProvider": "EXD",
        "correlationID": "6940d1c46208f3c00dae2ab94f3cd31c601461b47bf6d29ff8af0d0806a9c204",
        "decisionPolicy": {
          "id": "b913f724-3747-447b-a51e-8a2f9178f0db"
        }
      },
      "items": [
        {
          "id": "dps:14c7468e7f6271ff8023748a1146d11f05f77b7fc1368081:1bebbf0b7e0f1374",
          "name": "My item name",
          "score": 0.93,
          "itemSelection": {
            "selectionDetail": {
              "strategyID": "dps:selection-strategy:1bebbfc9245cb35e",
              "strategyName": "My selection strategy",
              "selectionType": "selectionStrategy",
              "version": "latest"
            },
            "rankingDetail": {
              "strategyID": "4FyRZTmpjrbzuL7rX7gvmu",
              "algorithmID": "RANDOM",
              "step": "aiModel",
              "trafficType": "random"
            }
          }
        }
      ]
    }
  ],
  "propositionEventType": {
    "decision": 1
  }
}
```

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、Journey Optimizer ジャーニーでContent Decision アクティビティを設定および使用して、決定ポリシーを介してパーソナライズされたオファーを取得し、条件とカスタムアクションを使用してルーティングまたは転送する方法について説明します。

**インテント：**
* コンテンツ決定アクティビティをジャーニーに追加し、決定ポリシーを設定する
* 決定ポリシー内の決定項目と選択戦略を選択して順序付け
* 取得したオファーに基づいてプロファイルを分岐するには、アクティビティの最適化条件でコンテンツ決定出力を使用します
* 取得したオファーをカスタムアクションを使用して外部システムに転送する
* 監査およびトラブルシューティングのために、ジャーニーステップイベントで意思決定データを検査します

**用語集：**
* **コンテンツ決定アクティビティ**：決定ポリシーを評価し、各プロファイル *（製品固有）*&#x200B;に対して最適な適格オファーを取得するジャーニーオーケストレーションアクティビティ
* **決定ポリシー**：評価する決定項目と選択戦略、および返す項目の数を指定する構成&#x200B;*（製品固有）*
* **選択戦略**：決定ポリシー内で使用されるランク付け評価方法で、どのオファーが実施要件を満たしているか、またどのようにスコアが付けられるかを判断します&#x200B;*（製品固有）*
* **提案**：選択した項目と関連するスコープおよびランキングメタデータ *（製品固有）*&#x200B;を含む、決定ポリシー実行の出力単位
* **listSize関数**: コンテンツ決定によって返されるアイテム数をカウントするために使用される式エディター関数（例：`listSize(@decision{Name.items})>0`） *（製品固有）*
* **カタログスキーマを提供**：決定項目で使用可能な属性を定義するスキーマ。高度な式エディターモード *（製品固有）*&#x200B;のコンテキストノードからアクセスできます

**ガードレール：**
* コンテンツ決定アクティビティの出力は、ネイティブチャネルアクティビティ（電子メール、プッシュ、SMSなど）では使用できません。
* コンテンツ決定出力は、式エディターの詳細モードでのみアクセスできます。単純モードでは使用できません
* 決定ポリシーを作成するには、決定権限が必要です
* 同意ポリシーの更新は、決定ポリシーで参照される属性に対して有効になるまでに最大48時間かかります
* 同意ポリシーは、Adobe Healthcare ShieldまたはPrivacy and Security Shield アドオンを使用している組織のみが使用できます
* オファースキーマ属性のデータ使用ラベル（DULE）が制限されていると、ガバナンスポリシー違反が発生する可能性があります

**用語：**
* 正規の名前：Content decision activity — Acronym: none — バリアント：content decision node, decisioning activity
* 同義語：「決定ポリシー」 = 「オファー選択ポリシー」、「提案」 = 「決定出力」
* 「コンテンツ決定アクティビティ」≠「ネイティブチャネルアクション」を混同しないでください（コンテンツ決定はオファーを取得しますが、直接配信しません。出力に対してアクションを実行するには、カスタムアクションまたは条件が必要です）

**FAQ:**
* **Q: コンテンツ決定アクティビティから返されたオファーを電子メールで直接使用できますか？**  – いいえ、コンテンツ決定アクティビティの出力は、ネイティブチャネルアクティビティでは使用できません。外部システムに送信するには、オファーをカスタムアクションに渡す必要があります。
* **Q: プロファイルに対してオファーが返されたかどうかを確認するにはどうすればよいですか？**  – 高度な式エディターでlistSize関数を使用します：`listSize(@decision{ContentdecisionName.items})>0`。
* **Q：式エディターのコンテンツ決定出力はどこでアクセスできますか？**  – 詳細モードに切り替え、コンテキストノードを展開し、決定ポリシーに移動して、使用可能なすべてのオファーカタログスキーマ属性を表示します。
* **Q：同意ポリシーの更新が決定ポリシーに適用されるまでにどのくらいの時間がかかりますか？**  – 同意ポリシーが更新されてから最大48時間後。
* **Q: ジャーニーステップイベントで使用できる決定データは何ですか？**  – 各ステップイベントには、exdRequestID、propositionEventType、提案の配列が含まれます。それぞれ、ID、scopeDetails （decision provider、correlationID、decision policy）、およびid、name、score、itemSelectionの詳細を含むitems配列が含まれます。

+++
