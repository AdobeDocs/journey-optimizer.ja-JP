---
title: Experience Decisioning の基本を学ぶ
description: 詳しくは、Experience Decisioningを参照してください
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供（LA）"
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 63%

---

# エクスペリエンス決定の基本を学ぶ {#get-started-experience-decisioning}

>[!AVAILABILITY]
>
>エクスペリエンス決定は、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。
>
>現時点では、Adobeを購入したお客様は機能を利用できません **ヘルスケアシールド** および **プライバシーとセキュリティシールド** アドオン製品

## Experience Decisioning とは {#about}

Experience Decisioning は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。

これらの決定項目は、新しいコードベースのエクスペリエンスチャネルを通じて様々なインバウンドサーフェスにシームレスに統合され、Journey Optimizer キャンペーン内でアクセスできるようになりました。 エクスペリエンス決定決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。

## Experience Decisioning の主な手順 {#steps}

Experience Decisioning を操作する主な手順は次のとおりです。

1. **適切な権限の割り当て**. Experience Decisioning は、Experience Decisioning 関連のアクセス権を持つユーザーのみが使用できます **[!UICONTROL 役割]** 意思決定管理者など。 Experience Decisioning にアクセスできない場合は、権限を拡張する必要があります。

   +++決定マネージャーの役割の割り当て方法を学ぶ

   1. でユーザーに役割を割り当てるには [!DNL Permissions] 製品、に移動します **[!UICONTROL 役割]** タブをクリックして、「決定マネージャー」を選択します。

      ![](assets/decision_permission_1.png)

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

      ![](assets/decision_permission_2.png)

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      ユーザーがまだ作成されていない場合は、を参照してください。 [ユーザー追加ドキュメント](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

      ![](assets/decision_permission_3.png)

   これにより、ユーザーをインスタンスへリダイレクトするメールが、ユーザーに送られます。

+++

1. **カスタム属性の設定**：カタログのスキーマにカスタム属性を設定することで、特定の要件に合わせて品目カタログをカスタマイズします。

1. ターゲットオーディエンスに表示する&#x200B;**決定項目を作成**&#x200B;します。

1. **コレクションで整理**：コレクションを使用し、属性ベースのルールに基づいて決定項目を分類します。コレクションを選択戦略に組み込んで、考慮する必要がある決定項目のコレクションを特定します。

1. **決定ルールの作成**：決定ルールは、どのユーザーに決定項目を表示できるかを決定するために、決定項目や選択戦略で使用されます。

1. **ランキングメソッドの実装**：ランキングメソッドを作成し、決定戦略内で適用して、決定項目を選択する際の優先順位を決定します。

1. **選択戦略の作成**：コレクション、決定ルール、ランキングメソッドを活用して、プロファイルに表示するのに適した決定項目を特定する選択戦略を作成します。

1. **コードベースのキャンペーンに決定ポリシーを埋め込む**：決定ポリシーは、複数の選択戦略を組み合わせて、対象のオーディエンスに表示する適格な決定項目を決定します。
