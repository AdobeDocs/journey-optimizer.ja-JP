---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツバリアントの自動生成（Beta）
description: AI ベースのシミュレーションを使用して、コンテンツバリアントを自動的に生成する方法について説明します。
feature: Email, Email Rendering, Personalization, Preview, Proofs
topic: Content Management
role: User
level: Intermediate
badge: label="Private Beta" type="Informative"
hide: true
exl-id: 9b7fbd43-3d90-458b-8a2f-0bf0ac5437c3
feature_v2: []
subfeature_v2:
  - id: bf7a266e-e483-42c6-b5bc-09ca6e49900c
source-git-commit: c3c86c6eb2e3717ce348ac562899c4f18dc7007d
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 96%

---

# コンテンツバリアントの自動生成（Beta）{#auto-generate-variants}

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

[!DNL Journey Optimizer] では、コンテンツをテストする複数のバリアントを自動的に生成できる AI ベースのシミュレーションを導入します。 この機能により、手動でバリアントを作成する必要性が軽減され、複雑なテンプレート間でパーソナライゼーションロジックを簡単に検証できます。

シミュレーションやプルーフにコンテンツをレンダリングする際、システムではコンテンツを分析し、すべてのパーソナライゼーショントークンと分岐ルールを特定します。 パーソナライゼーショントークンを、最終的なコンテンツのほとんど現実的なプレビューを提供する意味のある値に置き換えます。

**投資家タイプ**、**年齢グループ**、**婚姻ステータス**、**税 ID の検証**、**場所**&#x200B;に基づいた分岐ロジックを備えた金融サービスメールテンプレートを考慮します。 バリアントを生成しない場合、すべてのパスを検証するには、多数のバリアントを手動で作成する必要があります。 自動生成されたバリアントでは、システムでこれらの条件を自動的に対象とする代表的なバリアントが生成されます。  生成された各バリアントは、プレビューパネルにレンダリングされ、適用されるブロックと条件が正確に表示されます。

## コンテンツバリアントの生成

コンテンツのバリエーションを生成し、プレビューするには、次の手順に従います。

1. コンテンツを開き、**[!UICONTROL コンテンツをシミュレート]**&#x200B;をクリックします。

2. 「**[!UICONTROL 生成]**」ボタンをクリックします。

   ![&#x200B; バリエーションを生成ボタン &#x200B;](assets/simulate-generate-variant.png)

3. [!DNL Journey Optimizer] では、検出された属性に基づいてバリアントを自動的に生成します。

4. 左側のパネルで生成されたバリアントのリストを確認し、バリアントを選択して、プレビューパネルでパーソナライズされたレンダリングを確認します。

>[!NOTE]
>
>この機能は、標準のコンテンツバリエーションをシミュレート機能と同じように動作します。 コンテンツバリエーションのシミュレーションと関連するガードレールおよび制限について詳しくは、[コンテンツバリエーションのシミュレート](../test-approve/simulate-sample-input.md)の節を参照してください。
