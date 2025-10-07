---
title: 決定ポリシーの基本を学ぶ
description: 決定ポリシーを操作してオファーを配信する方法を説明します。
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
source-git-commit: 7896dc3450f499e0889f6e32df5958ae9868d9e6
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 79%

---

# 決定ポリシーの基本を学ぶ {#create-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_decision"
>title="決定とは"
>abstract="決定ポリシーには、決定エンジンが最適なコンテンツを選択するためのすべての選択ロジックが含まれています。決定ポリシーはキャンペーンに固有です。目標は、各プロファイルに最適なオファーを選択することです。一方、キャンペーンのオーサリングでは、メッセージに含める項目属性など、選択した決定項目の表示方法を指定できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="決定について"

>[!CONTEXTUALHELP]
>id="ajo_journey_decision_policy"
>title="決定ポリシーの定義"
>abstract="決定ポリシーを使用すると、決定エンジンから最適な項目を選択し、正しいオーディエンスに配信できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="決定について"

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_policy"
>title="決定ポリシー"
>abstract="決定ポリシーを使用すると、決定エンジンから最適な項目を選択し、各オーディエンスに配信できます。"

>[!CONTEXTUALHELP]
>id="ajo_exd_placements"
>title="プレースメント"
>abstract="プレースメントにより、決定エンジンから返された項目がメッセージ内に表示される場所が決まります。レポートでは、様々なプレースメントにわたるパフォーマンスを追跡できます。"

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_attribute"
>title="カタログから決定属性を選択する"
>abstract="決定属性はカタログのスキーマに保存されます。選択したカタログから、ここで使用する属性を選択します。"

決定ポリシーは、各オーディエンスメンバーに配信する最適なコンテンツを動的に返すことを目的に、決定エンジンを活用するオファーのコンテナです。目標は、各プロファイルに最適なオファーを選択することです。一方、キャンペーン／ジャーニーのオーサリングでは、メッセージに含める項目属性など、選択した決定項目の表示方法を指定できます。

>[!AVAILABILITY]
>
>現時点では、すべての顧客がコードベースのエクスペリエンスチャネルで決定ポリシーを使用できます。 これらのオファーは、使用制限があるメールチャネルでのみ使用できます。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

## 主な手順 {#key}

メッセージで決定ポリシーを活用する主な手順は次のとおりです。

1. [決定ポリシーの作成](../experience-decisioning/create-decision-policy.md)

   返す項目数の選択、選択戦略、フォールバックオプションおよび評価順序の設定により、メッセージに決定ポリシーを設定します。

1. [コンテンツで決定ポリシーを使用](../experience-decisioning/use-decision-policy.md)

   メッセージに表示する決定ポリシーの出力と決定項目の属性を使用してコンテンツをパーソナライズします。

1. [レポートダッシュボードを作成](cja-reporting.md)

   カスタムの Customer Journey Analytics ダッシュボードを作成してパフォーマンスを測定し、決定ポリシーとオファーがどのように配信および関与されているかに関するインサイトを得ます。

## ガードレールと制限

* **メールのミラーページ** – 現時点では、決定項目は、メールのミラーページではレンダリングされません。
* **トラッキングとリンクのタイプ** - 決定によって生成されたリンクを追跡するには、「決定アセット」としてスキーマで定義します。属性ベースのリンクは追跡できません。
* **メールでの決定ポリシーのネスト** - 既に決定ポリシーが関連付けられている親メールコンポーネント内に複数の決定ポリシーをネストすることはできません。
* **決定ポリシーを含む複製されたジャーニー／キャンペーン** - 決定ポリシーを含むジャーニーまたはキャンペーンを複製すると、複製されたバージョンは元のメールまたはコードベースのエクスペリエンスを参照するので、エラーが発生します。複製後は、常に決定ポリシーを再設定します。
* **同意ポリシー** - 同意ポリシーの更新が有効になるまで最大 48 時間かかります。決定ポリシーが、最近更新された同意ポリシーに関連付けられた属性を参照している場合、変更は直ちに適用されません。

  同様に、同意ポリシーの対象となる新しいプロファイル属性が決定ポリシーに追加された場合、その属性は使用可能になりますが、関連付けられた同意ポリシーは、遅延が経過するまで適用されません。

  同意ポリシーは、Adobe Healthcare Shield または Privacy and Security Shield アドオンを導入している組織でのみ使用できます。

* **AI ランキング** - 現時点では、決定を含むジャーニーのメールチャネルでは、AI ランキングはサポートされていません。

## 次の手順 {#next-steps}

これで、決定ポリシーの仕組みと、パーソナライズされたオファーの配信に決定ポリシーがどのように役立つかを理解できたので、最初の決定ポリシーを作成する準備が整いました。

➡️[&#x200B; 決定ポリシーの作成方法を説明します &#x200B;](../experience-decisioning/create-decision-policy.md)
