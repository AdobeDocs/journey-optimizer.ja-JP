---
solution: Journey Optimizer
product: journey optimizer
title: ターゲティングディメンションの作成
description: リレーショナルスキーマを顧客プロファイルにマッピングする方法を説明します
exl-id: 2479c109-cd6f-407e-8a53-77e4477dc36f
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 0%

---


# ターゲティングディメンションの設定 {#configuration}

**[!UICONTROL オーケストレートキャンペーン]** を使用すると、Adobe Experience Platformのリレーショナルスキーマ機能を活用して、ターゲットコミュニケーションを設計し、エンティティレベルで配信できます。

**[!UICONTROL オーケストレートキャンペーン]** のセグメント化は主にリレーショナルスキーマに基づいて動作しますが、実際のメッセージ配信は常に **プロファイル** レベルで行われます。

ターゲティングを設定する際には、次の 2 つの重要な側面を定義します。

* **ターゲット可能スキーマ**

  ターゲット設定の対象となるリレーショナルスキーマを指定します。 デフォルトでは、`Recipient` という名前のスキーマが使用されますが、`Visitors`、`Customers` などの代替値を設定できます。

  >[!IMPORTANT]
  >
  > ターゲットスキーマは、:1 スキーマと 1`Profile` の関係がある必要があります。 例えば、通常は 1 対多の関係を表すので、`Purchases` をターゲットスキーマとして使用することはできません。

* **プロファイルのリンケージ**

  システムは、ターゲットスキーマが `Profile` にどのようにマッピングされるかを理解する必要があります。 これは、共有 ID フィールドを通じて実現されます。共有 ID フィールドは、ターゲットスキーマと `Profile` スキーマの両方に存在し、ID 名前空間として設定されています。

## ターゲティングディメンションの作成 {#targeting-dimension}

まず、リレーショナルスキーマを顧客プロファイルにマッピングして、キャンペーンオーケストレーションを設定します。

1. **[!UICONTROL 管理]** から **[!UICONTROL 設定]** メニューにアクセスし、**[!UICONTROL Campaign Target Dimension]** を選択します。

   ![](assets/target-dimension-1.png)

1. **[!UICONTROL 作成]** をクリックして、**[!UICONTROL ターゲティングディメンション]** の作成を開始します。

1. ドロップダウンから [ 以前に設定したスキーマ ](gs-schemas.md)&#x200B;を選択します。

   すべてのリレーショナルスキーマが表示されますが、選択できるのは **プロファイル** への直接 ID 関係を持つスキーマのみです。

1. ターゲットにするエンティティを表す **[!UICONTROL ID 値]** を選択します。

   この例では、顧客プロファイルは複数のサブスクリプションにリンクされ、それぞれが `crmID` スキーマ内の一意の `Recipient` で表されます。 **[!UICONTROL スキーマとその]** ID を使用するように `Recipient`Target Dimension`crmID` を設定することで、メイン顧客プロファイルではなく購読レベルでメッセージを送信でき、各契約または明細が独自にパーソナライズされたメッセージを受信するようになります。

   [詳しくは、Adobe Experience Platform ドキュメントを参照してください。](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)

   ![](assets/target-dimension-2.png)

1. **[!UICONTROL 保存]** をクリックして、設定を完了します。 一度作成した **[!UICONTROL ターゲットディメンション]** は、削除または編集できません。

**[!UICONTROL Target Dimension]** を設定したら、**[!UICONTROL チャネル設定]** の作成とセットアップに進み、対応する **[!UICONTROL 実行の詳細]** を定義します。

## チャネル設定の指定 {#channel-configuration}

**[!UICONTROL Target Dimension]** を設定した後、メールまたは SMS **[!UICONTROL チャネルを設定し]** 適切な **[!UICONTROL 実行の詳細]** を定義する必要があります。 次の項目を定義できます。

* **メッセージ配信のレベル**：例えば、個々の受信者に 1 件のメールを送信するなど、受信者ごとに 1 件のメッセージを送信します。

* **実行アドレス**：メールアドレスや電話番号など、送信に使用される特定の連絡先フィールド。

チャネル設定を指定するには：

1. まず、**[!UICONTROL チャネル設定]** を作成および設定します。

   また、既存の **[!UICONTROL チャネル設定]** を更新することもできます。

   ➡️ [ このページで説明されている手順に従ってください ](../email/surface-personalization.md)

1. **[!UICONTROL チャネル設定]** の **[!UICONTROL 実行の詳細]** セクションから、**[!UICONTROL オーケストレーションされたキャンペーン]** タブにアクセスします。

   ![](assets/target-dimension-3.png)

1. **[!UICONTROL 有効]** をクリックして、オーケストレートキャンペーンと互換性を持たせます。

1. 配信方法を選択します。

   * **[!UICONTROL Target Dimension]**：プライマリエンティティ（受信者など）に送信します。

   * **[!UICONTROL Target +セカンダリDimension]**：プライマリエンティティとセカンダリエンティティの両方を使用して送信します（例：受信者+ コントラクト）。

1. ドロップダウンから [ 以前に作成した Target Dimension](#targeting-dimension) を選択します。

   ![](assets/target-dimension-4.png)

1. 配信方法として **[!UICONTROL ターゲット +セカンダリDimension]** を選択した場合は、**[!UICONTROL セカンダリDimension]** を選択して、メッセージ配信のコンテキストを定義します。

1. 「**[!UICONTROL 実行アドレス]**」セクションで、配信アドレスの取得に使用する **[!UICONTROL 2&rbrace;Source&rbrace; を選択します（メールアドレスや電話番号など）。]**

   * **[!UICONTROL プロファイル]**：配信アドレス（メールなど）がメイン顧客プロファイルに直接保存されている場合は、このオプションを選択します。

     特定の関連エンティティではなく、メイン顧客にメッセージを送信する場合に役立ちます。

   * **[!UICONTROL Target Dimension]**：配信アドレスがプライマリエンティティ（受信者など）に保存されている場合に選択します。

     各受信者が独自の配信アドレス（別のメールや電話番号など）を持っている場合に役立ちます。

   * **[!UICONTROL セカンダリDimension]**: **[!UICONTROL Target +セカンダリDimension]** を配信方法として使用する場合は、以前に設定した関連する **[!UICONTROL セカンダリDimension]** を選択します。

     例えば、セカンダリディメンションが予約または購読を表す場合、実行アドレス（メールなど）をそのレベルから取得できます。 これは、プロファイルがサービスの予約や購読時に異なる連絡先の詳細を使用する場合に便利です。

1. 「**[!UICONTROL 配信アドレス]**」フィールドで ![ 編集アイコン ](assets/do-not-localize/edit.svg) をクリックして、メッセージ配信に使用する特定のフィールドを選択します。

   ![](assets/target-dimension-4.png)

1. 設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

これで、チャネルを **オーケストレーションされたキャンペーン** で使用する準備が整い、選択したターゲットディメンションに従ってメッセージが配信されます。
