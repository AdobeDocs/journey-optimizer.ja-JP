---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツ決定アクティビティ
description: コンテンツ決定アクティビティについて学ぶ
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
badge: label="限定提供" type="Informative"
keywords: アクティビティ，決定，コンテンツの決定，決定ポリシー，キャンバス，ジャーニー
exl-id: 6188644a-6a3b-4926-9ae9-0c6b42c96bae
source-git-commit: 701b2caeac704149c820ce3bf6338107ab4bc9f8
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 7%

---

# コンテンツ決定アクティビティ {#content-decision}

>[!AVAILABILITY]
>
>この機能は、一連の組織でのみ使用でき（限定提供）、今後のリリースでグローバルにロールアウトされる予定です。

[!DNL Journey Optimizer] を使用すると、ジャーニーキャンバスの専用の **コンテンツ決定** アクティビティを通じて、ジャーニーにオファーを含めることができます。 その後、ジャーニーに他のアクティビティ（[ カスタムアクション ](../action/about-custom-action-configuration.md) など）を追加し、パーソナライズされたオファーでオーディエンスをターゲットに設定できます。

>[!NOTE]
>
>コンテンツ決定アクティビティの出力は、ネイティブチャネルアクティビティでは使用できません。

この機能を活用するには、[ コンテンツ決定アクティビティ ](#add-content-decision-activity) を追加して、実施要件を満たすプロファイルに提示するオファーを定義するジャーニーを作成します。

その後、次の場所でコンテンツ決定アクティビティの出力を使用できます。

* [ 条件アクティビティ ](#add-condition-activity)：取得したオファーに基づいてプロファイルを特定のパスに移動します。

* [ カスタムアクション ](#add-custom-action)：オファーを外部システムに送信できます。

## コンテンツ決定アクティビティの設定 {#add-content-decision-activity}

コンテンツ決定アクティビティを使用すると、[!DNL Journey Optimizer] Decisioning から最適な項目を選択し、適切なオーディエンスに配信できる決定ポリシーを定義できます。

<!--Their goal is to select the best offers for each profile, while the campaign/journey authoring allows you to indicate how the selected decision items should be presented, including which item attributes to be included in the message.-->

**[!UICONTROL コンテンツの決定]** アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーケストレーション]** カテゴリを展開し、**[!UICONTROL コンテンツ決定]** アクティビティをキャンバスにドロップします。

   ![ ジャーニーへのコンテンツ決定の追加 ](assets/journey-content-decision.png){width=100%}

1. オプションで、アクティビティにラベルと説明を追加します。

1. 「**[!UICONTROL 決定ポリシーを追加]**」をクリックします。 [ 決定ポリシーの詳細情報 ](../experience-decisioning/create-decision.md)

   >[!NOTE]
   >
   >決定ポリシーを作成するには、決定権限が必要です。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md#steps)

1. 返される項目の数を選択します。例えば、2 を選択した場合、最適な 2 つの実施要件を満たすオファーが提示されます。 「**[!UICONTROL 次へ]**」をクリックします。

1. 「**[!UICONTROL 戦略シーケンス]**」セクションで、決定ポリシーで提示する決定項目や選択戦略を選択します。 [詳細情報](../experience-decisioning/create-decision.md#select)

1. 必要に応じて、評価順序を並べ替えます。

   複数の決定項目や戦略を追加する場合は、順番に評価され、各オブジェクトまたはオブジェクトのグループの左側に数字が表示されます。 デフォルトのシーケンスを変更するには、オブジェクトやグループをドラッグ＆ドロップして、任意の順序に並べ替えることができます。[詳細情報](../experience-decisioning/create-decision.md#evaluation-order)

1. オプションで、フォールバックオファーを追加します。 [詳細情報](../experience-decisioning/create-decision.md#fallback)

1. 決定ポリシーをレビューして保存します。

   ![ 決定ポリシーの概要 ](assets/journey-content-decision-policy.png){width=70%}<!--reshoot or change screen-->

これで、このコンテンツ決定アクティビティの出力をジャーニーで活用する準備が整いました。

## コンテンツ決定アクティビティの出力を使用 {#use-content-decision-output}

コンテンツの決定の出力は、複数のジャーニーアクティビティで使用できます。 例えば、[ 条件アクティビティ ](#add-condition-activity) を使用して、取得したオファーの数に基づいて、ジャーニーの特定の分岐にプロファイルを移動できます。

また、オファーをコンテンツ決定アクティビティから外部システムと共有するために、ジャーニーに [ カスタムアクション ](#add-custom-action) を追加することもできます。

### 条件アクティビティ内 {#add-condition-activity}

コンテンツ決定アクティビティの出力を活用するには、ジャーニーに条件を追加します。この条件では、オファーのデータを使用して、プロファイルを特定のパスに移動する式を定義できます。 次の手順に従います。

1. **[!UICONTROL オーケストレーション]** カテゴリから、**[!UICONTROL 条件]** アクティビティをキャンバスにドロップします。 [詳細情報](condition-activity.md#add-condition-activity)

1. 必要に応じて、定義する最初の式に対応する **[!UICONTROL Path1]** の名前を、より関連性の高いラベルに変更します。

1. この最初のパスでは、「**[!UICONTROL 式]** フィールド内をクリックするか、編集アイコンを使用して式を追加します。

   ![ 条件を追加し、式を編集 ](assets/journey-content-decision-condition.png){width=80%}

1. 開いたポップアップウィンドウで、**[!UICONTROL 詳細設定モード]** に切り替えて [ 高度な式エディター ](expression/expressionadvanced.md) を使用します。

   >[!CAUTION]
   >
   >コンテンツ決定ノードの出力は、**[!UICONTROL 詳細設定モード]** でのみ使用できます。

1. **[!UICONTROL コンテキスト]** ノードを展開し、決定ポリシーに移動して、[ オファーカタログスキーマ ](../experience-decisioning/catalogs.md#access-catalog-schema) で使用可能なすべての属性を表示します。

   ![ 条件を追加し、式を編集 ](assets/journey-content-decision-context.png)

   >[!NOTE]
   >
   >決定ルールで使用されるジャーニーエクスペリエンスイベント（コンテキストデータとして）または [ オファースキーマ ](../experience-decisioning/catalogs.md#access-catalog-schema) のいずれかで属性に定義された制限ラベルは、DULE または同意のポリシー違反には至りません。 データガバナンスポリシーの詳細については、[ この節 ](../action/action-privacy.md) を参照してください

1. ジャーニーにエントリするプロファイルにオファーが返されたかどうかを確認するには、[listSize](functions/functionlistsize.md) 関数を次の構文で使用します。`listSize(@decision{ContentdecisionName.items})>0`

   >[!NOTE]
   >
   >この例では、ジャーニーに追加したコンテンツ決定のラベルは `Name` です。

   ![ リストを使用した条件の追加 ](assets/journey-content-decision-condition-list.png)

1. 「**[!UICONTROL OK]**」をクリックします。

1. 必要に応じて、他の条件を定義するパスを追加します。

   最初の条件を満たさないプロファイルに対して、別のパスを作成することもできます。その場合は、「**[!UICONTROL 上記以外の事例のパスを表示]**」をオンにします。<!--These profiles will then exit the journey if no other activity is added in that path.-->

1. 条件アクティビティを保存します。

### カスタムアクション内 {#add-custom-action}

コンテンツ決定アクティビティの出力を活用するには、ジャーニーにカスタムアクションを追加し、定義したオファーを外部システムと共有します。 次の手順に従います。

1. カスタムアクションをジャーニーに追加します。 [詳細情報](../action/about-custom-action-configuration.md)

1. アクションのラベルを入力します。

1. 「**[!UICONTROL リクエストパラメーター]**」セクションで、取得されたオファーから属性にマッピングするパラメーターを選択します。

   編集可能なテキストフィールド内をクリックし、取得されたオファーから属性にマッピングしたいパラメーターを選択します。

   ![ カスタムアクションのリクエストパラメーターの編集 ](assets/journey-content-decision-custom-action-param.png)

1. 開いたポップアップウィンドウで **[!UICONTROL 詳細設定モード]** に切り替えます。 [ 高度な式エディター ](expression/expressionadvanced.md) で、**[!UICONTROL コンテキスト]** ノードを展開して、すべての決定ポリシー項目を表示します。

   >[!CAUTION]
   >
   >コンテンツ決定ノードの出力は、**[!UICONTROL 詳細設定モード]** でのみ使用できます。

1. [ 配列を使用して ](../experience-decisioning/catalogs.md#access-catalog-schema) オファーカタログスキーマ `items` を参照します。 例えば、取得した最初のオファーの `itemName` と取得した 2 番目のオファーの `itemName` を使用します。

   ![ 決定ポリシーを含むカスタムアクションのリクエストパラメーター ](assets/journey-content-decision-custom-action-param-ex.png)

1. **[!UICONTROL OK]** をクリックして式を保存します。

1. カスタムアクション設定を **[!UICONTROL 保存]** します。

### エンドツーエンドの例 {#use-case}

以下は、上記のように、コンテンツ決定アクティビティを条件アクティビティとカスタムアクションに組み合わせて使用したジャーニーの完全な例です。

![ ジャーニーの完了 ](assets/journey-content-decision-full-journey.png)

<!--When all activities are properly configured and saved, [publish](publishing-the-journey.md) your journey.-->

ジャーニーが [ アクティブ化 ](publishing-the-journey.md) されると、次の操作が行われます。

<!--* Profiles who enter the journey and are eligible for at least one offer are targeted by the custom action.

* If no offer is returned for a profile, they are excluded from the custom action.-->

1. プロファイルがそのオーディエンスの対象となるたびにジャーニーにエントリします。

1. コンテンツ決定アクティビティを通じ [!DNL Journey Optimizer]、各プロファイルに関連するオファーを取得します。

1. 1 つ以上のオファーが取得されたプロファイルのみが（「適格なプロファイル」パスを介して）ジャーニーを継続します。

1. 条件が満たされると、対応するオファーがカスタムアクションを通じて外部システムに送信されます。
