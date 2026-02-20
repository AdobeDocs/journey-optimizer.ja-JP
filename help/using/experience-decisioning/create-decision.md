---
title: 決定ポリシーの基本を学ぶ
description: 決定ポリシーを操作して、オファーを配信する方法について説明します。
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
version: Journey Orchestration
source-git-commit: be4c0453630388d898d53feeb5f9dcfe57ad5934
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 70%

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

➡️ [この機能について詳しくは、ビデオを参照してください](#video)。

## ガードレールと制限

* **サポートされているチャネル** – 決定ポリシーは、すべてのお客様がコードベースのエクスペリエンス、SMS およびプッシュ通知に使用できます。 メールチャネルの決定は、限定提供（LA）でのみ使用できます。
* **プッシュ通知のSDK要件** - プッシュ通知を使用した Experience Decisioning では、特定のバージョンの Mobile SDKが必要です。 この機能を実装する前に、[ リリースノート ](https://developer.adobe.com/client-sdks/home/release-notes/){target="_blank"} を確認して、必要なバージョンを特定し、それに応じてアップグレードしていることを確認します。 また、お使いのプラットフォームで利用可能なすべてのSDK バージョンを確認することもできます [ この節 ](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}。
* **メールのミラーページ** - 現時点では、決定項目はメールのミラーページではレンダリングされません。
* **トラッキングとリンクのタイプ** - 決定によって生成されたリンクを追跡するには、「決定アセット」としてスキーマで定義します。属性ベースのリンクは追跡できません。
* **メールでの決定ポリシーのネスト** - 既に決定ポリシーが関連付けられている親メールコンポーネント内に複数の決定ポリシーをネストすることはできません。
* **決定ポリシーを含む複製されたジャーニー／キャンペーン** - 決定ポリシーを含むジャーニーまたはキャンペーンを複製すると、複製されたバージョンは元のメールまたはコードベースのエクスペリエンスを参照するので、エラーが発生します。複製後は、常に決定ポリシーを再設定します。
* **同意ポリシー** - 同意ポリシーの更新が有効になるまで最大 48 時間かかります。決定ポリシーが、最近更新された同意ポリシーに関連付けられた属性を参照している場合、変更は直ちに適用されません。

  同様に、同意ポリシーの対象となる新しいプロファイル属性が決定ポリシーに追加された場合、その属性は使用可能になりますが、関連付けられた同意ポリシーは、遅延が経過するまで適用されません。

  同意ポリシーは、Adobe Healthcare Shield または Privacy and Security Shield アドオンを導入している組織でのみ使用できます。

* **AI ランキング** - 現時点では、決定を含むジャーニーのメールチャネルでは、AI ランキングはサポートされていません。

* **コンテンツテンプレート** - コンテンツ内で設定された決定ポリシーは、テンプレートには保存されません。 テンプレートを別のアクションに適用する場合は、ポリシーを再設定する必要があります。

## 主な手順 {#key}

メッセージに決定ポリシーを活用する主な手順を次に示します。

1. **決定ポリシーの作成**

   メッセージに決定ポリシーを追加し、返す項目数、選択戦略、フォールバックオプションを設定します。

   ➡️ [決定ポリシーの作成方法を学ぶ](../experience-decisioning/create-decision-policy.md)

1. **コンテンツでの決定ポリシーの使用**

   メッセージに表示する決定項目から属性を挿入して、決定ポリシーの出力を使用してコンテンツをパーソナライズします

   ➡️[メッセージで決定ポリシーを使用する方法を学ぶ](../experience-decisioning/create-decision-policy.md)

## チュートリアルビデオ {#video}

Decisioning を使用して、オーディエンス向けにメールをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3476158?quality=12)

Decisioning を使用して、オーディエンス向けにプッシュ通知をパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479199?quality=12)

Decisioning を使用して、オーディエンス向けに SMS メッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479529?quality=12)
