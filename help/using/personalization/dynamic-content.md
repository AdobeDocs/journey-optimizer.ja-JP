---
solution: Journey Optimizer
product: journey optimizer
title: 動的コンテンツの作成
description: メッセージに動的を追加する方法について説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 639ad7df-0d0f-4c9b-95d1-f3101267aae2
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# 動的コンテンツの作成 {#dynamic-content}

Adobe 旅のオプティマイザーにより、ライブラリ内に作成された条件付きルールを活用して、メッセージに動的コンテンツを追加できます。

動的コンテンツは任意のフィールドに作成できます。これを使用すると、式エディターを使用してパーソナル化を追加することができます。 これには、題名行、リンク、プッシュ通知コンテンツ、またはテキストタイプの表示が含まれます。 [パーソナル化コンテキストについて詳しく説明します。](personalization-contexts.md)

さらに、条件付きルールを電子メールデザイナーに使用して、複数のバリエーションのコンテンツコンポーネントを作成することもできます。

## エクスプレッションへの動的コンテンツの追加 {#perso-expressions}

式に動的コンテンツを追加するには、次の手順に従います。

1. 動的コンテンツを追加するフィールドに移動して、式エディターを開きます。

1. **[!UICONTROL Conditions]**&#x200B;メニューを選択して、使用可能な条件付きルールのリストを表示します。ルールの横にある「+」ボタンをクリックして、現在のエクスプレッションに追加します。

   また、を選択 **[!UICONTROL Create new]** して新しいルールを作成することもできます。 [条件の作成方法について説明します。](create-conditions.md)

   ![](assets/conditions-expression.png)

1. および `{%/if}` タグ間 `{%if}` に追加し、条件付き規則が満たされている場合に表示するコンテンツを指定します。必要に応じて、複数のルールを追加することができます。

   次の例では、受信者が使用している言語に応じて、2つのバリエーションが SMS コンテンツとして作成されています。

   ![](assets/conditions-language-sample.png)

1. コンテンツの準備が完了したら、ボタンを使用して **[!UICONTROL Simulate content]** 様々なバリエーションをプレビューできます。 [メッセージをテストおよびプレビューする方法について説明します。](../email/preview.md)

   ![](assets/conditions-preview.png)

## 電子メールへの動的コンテンツの追加 {#emails}

>[!CONTEXTUALHELP]
>id="ac_conditional_content"
>title="条件付きコンテンツ"
>abstract="条件付き規則を使用して、複数のバリエーションのコンテンツコンポーネントを作成します。 メッセージの送信時にどのような条件も満たさない場合は、デフォルトのバリエーションのコンテンツが表示されます。"

>[!CONTEXTUALHELP]
>id="ac_conditional_content_select"
>title="条件付きコンテンツ"
>abstract="ライブラリに保存された条件付きルールを使用するか、または新規作成します。"

電子メールデザイナーでコンテンツコンポーネントのバリエーションを作成する手順を次に示します。

1. 電子メールデザイナーで、コンテンツのコンポーネントを選択し、をクリック **[!UICONTROL Enable conditional content]** します。

   ![](assets/conditions-enable-conditional.png)

1. **[!UICONTROL Conditional Content]**&#x200B;ペインが左側に表示されます。このウィンドウでは、条件を使用して、選択したコンテンツコンポーネントの複数のバリエーションを作成できます。

   ボタンを選択 **[!UICONTROL Apply condition]** して、最初のバリエーションを設定します。

   ![](assets/conditions-apply.png)

1. 条件ライブラリが表示されます。 バリエーションに関連付ける条件ルールを選択してから、をクリック **[!UICONTROL Select]** します。 この例では、選択した言語に応じてコンポーネントのテキストを調整します。

   ![](assets/conditions-select.png)

   「」をクリック **[!UICONTROL Create new]** して、新しいルールを作成することもできます。 [条件の作成方法について説明します。](create-conditions.md)

1. 条件付き規則はバリアントに関連付けられます。 読みやすさを向上させるためには、楕円メニューをクリックして、バリエーションの名前を変更することをお勧めします。

   ここでは、メッセージを送信する際にルールが満たされている場合に、コンポーネントの表示方法を設定します。 次の例では、受取人の選択された言語である場合は、フランス語のテキストを表示します。

   ![](assets/conditions-design.png)

1. コンテンツコンポーネントには、必要な数のバリエーションを追加します。 異なるバリエーション間ではいつでも変更できます。この場合は、条件ルールに応じてコンテンツコンポーネントがどのように表示されるかを確認することができます。

   >[!NOTE]
   >バリエーションで定義されているルールの中で、メッセージを送信する際に適合しないものがある場合、に **[!UICONTROL Default variant]** よって定義されているコンテンツがコンテンツコンポーネントに表示されます。
   >
   >条件付きコンテンツは、そのバリアントが表示されている順序に基づいて、関連付けられたルールに対して評価されます。 他の条件が満たされていない場合は、常にデフォルトのバリアントが表示されます。
