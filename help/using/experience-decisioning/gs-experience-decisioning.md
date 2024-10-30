---
title: 意思決定の概要
description: 決定の詳細情報
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供"
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 75%

---

# 意思決定の概要 {#get-started-experience-decisioning}

>[!AVAILABILITY]
>
>決定は現在、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。
>
>現時点では、Adobe **Healthcare Shield** および **Privacy and Security Shield** アドオン製品を購入したお客様は、この機能を使用できません。

## 決定とは {#about}

意思決定は、「決定項目」と呼ばれるマーケティングオファーの一元化されたカタログと高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。 このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。

これらの決定項目は、Journey Optimizer キャンペーン内でアクセス可能になった[新しいコードベースのエクスペリエンスチャネル](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/code-based-experience/get-started-code-based)を通じて、幅広いインバウンドサーフェスにシームレスに統合されます。意思決定決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。


## 決定の主な手順 {#steps}

Decisioning を使用する主な手順は次のとおりです。

1. **適切な権限を割り当て**&#x200B;ます。決定は、決定マネージャーなど、決定に関連する **[!UICONTROL 役割]** へのアクセス権を持つユーザーのみが使用できます。 Decisioning にアクセスできない場合は、権限を拡張する必要があります。

   +++決定マネージャーの役割の割り当て方法

   1. [!DNL Permissions] 製品でユーザーに役割を割り当てるには、「**[!UICONTROL 役割]**」タブに移動し、決定マネージャーを選択します。

      ![](assets/decision_permission_1.png)

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

      ![](assets/decision_permission_2.png)

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users)を参照してください。

      ![](assets/decision_permission_3.png)

   これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

+++

1. **カスタム属性の設定**：カスタム属性をカタログのスキーマに設定して、項目カタログを特定の要件に合わせます。

1. ターゲットオーディエンスに表示する&#x200B;**決定項目を作成**&#x200B;します。

1. **コレクションで整理**：コレクションを使用し、属性ベースのルールに基づいて決定項目を分類します。コレクションを選択戦略に組み込んで、考慮する必要がある決定項目のコレクションを特定します。

1. **決定ルールの作成**：決定ルールは、どのユーザーに決定項目を表示できるかを決定するために、決定項目や選択戦略で使用されます。

1. **ランキングメソッドの実装**：ランキングメソッドを作成し、決定戦略内で適用して、決定項目を選択する際の優先順位を決定します。

1. **選択戦略の作成**：コレクション、決定ルール、ランキングメソッドを活用して、プロファイルに表示するのに適した決定項目を特定する選択戦略を作成します。

1. **コードベースのキャンペーンに決定ポリシーを埋め込む**：決定ポリシーは、複数の選択戦略を組み合わせて、対象のオーディエンスに表示する適格な決定項目を決定します。
