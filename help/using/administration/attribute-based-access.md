---
title: 属性ベースのアクセス制御
description: 属性ベースのアクセス制御を学ぶ
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 162b0848-313a-447e-9237-5a6dbc8102c6
source-git-commit: 630b8ef5a140709161b24256083b2104be5b6121
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 98%

---

# 属性ベースのアクセス制御 {#attribute-based-access}

>[!IMPORTANT]
>
>属性ベースのアクセス制御の使用は、現在、一連の組織でのみ使用できます（使用制限）。 この機能を利用する場合は、アドビアカウント担当者にお問い合わせください。

属性ベースのアクセス制御（ABAC）を使用すると、特定のユーザーチームまたはユーザーグループのデータアクセスを管理する権限を定義できます。その目的は、機密性の高いデジタルアセットを権限のないユーザーから保護し、個人データの保護を向上させることです。

Adobe Journey Optimizer では、ABAC を使用することで、データを保護し、Experience Data Model（XDM）スキーマ、プロファイル属性、セグメントなどの特定のフィールド要素に対する特定のアクセス権を付与できます。

<!--For a more detailed list of the terminology used with ABAC, refer to Adobe Experience Platform documentation.-->

この例では、**国籍**&#x200B;スキーマフィールドにラベルを追加して、権限のないユーザーによる使用を制限します。 これを実現するには、次の手順を実行する必要があります。

1. Adobe Experience Platform で&#x200B;**[!UICONTROL ラベル]**&#x200B;を&#x200B;**国籍**&#x200B;スキーマフィールドに割り当てます。

2. 新しい&#x200B;**[!UICONTROL 役割]**&#x200B;を作成し、スキーマフィールドにアクセスして使用できるようにさせたいユーザーに対応する&#x200B;**[!UICONTROL ラベル]**&#x200B;を割り当てます。

3. Adobe Journey Optimizer で&#x200B;**[!UICONTROL スキーマフィールド]**&#x200B;を使用します。

## Adobe Experience Platform でオブジェクトにラベルを割り当てます。 {#assign-label}

>[!WARNING]
>
>ラベルの使用が正しくないと、ユーザーへのアクセスが中断され、ポリシー違反が発生する可能性があります。

**[!UICONTROL ラベル]**は、属性ベースのアクセス制御を使用して特定の特徴領域を割り当てるために使用できます。
この例では、**国籍**&#x200B;フィールドへのアクセスを制限します。このフィールドには、**[!UICONTROL 役割]**&#x200B;に対応する&#x200B;**[!UICONTROL ラベル]**&#x200B;を持つユーザーのみがアクセスできます。

**[!UICONTROL ラベル]**&#x200B;は&#x200B;**[!UICONTROL スキーマ]**&#x200B;や、**[!UICONTROL データセット]**、**[!UICONTROL セグメント]**&#x200B;に追加することもできます。

1. **[!UICONTROL スキーマ]**&#x200B;を作成します。詳しくは、[こちらのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja)を参照してください。

   ![](assets/label_1.png)

1. 新しく作成された&#x200B;**[!UICONTROL スキーマ]**&#x200B;で、まずは&#x200B;**国籍**&#x200B;フィールドを含む&#x200B;**[!UICONTROL デモグラフィックの詳細]**&#x200B;フィールドグループを追加します。

   ![](assets/label_2.png)

1. 「**[!UICONTROL ラベル]**」タブで、制限されたフィールド名、この例では&#x200B;**国籍**&#x200B;を確認します。次に、右側のパネルのメニューから、「**[!UICONTROL ガバナンスラベルを編集]**」を選択します。

   ![](assets/label_3.png)

1. 対応する&#x200B;**[!UICONTROL ラベル]**（このケースでは C2）を選択します。データをサードパーティにエクスポートすることはできません。使用可能なラベルの詳細なリストについては、[こちらのページ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=ja#contract-labels)を参照してください。

   ![](assets/label_4.png)

1. 必要に応じてスキーマをさらにパーソナライズし、有効にします。スキーマを有効にする方法に関する詳細な手順については、こちらの[ページ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=jal#profile)を参照してください。

これで、スキーマのフィールドが表示され、使用できるのは、C2 ラベルで設定されたロールの一部であるユーザーのみになります。
**[!UICONTROL ラベル]**&#x200B;を&#x200B;**[!UICONTROL フィールド名]**&#x200B;に適用することで、作成されるすべてのスキーマで&#x200B;**[!UICONTROL ラベル]**&#x200B;が自動的に&#x200B;**国籍**&#x200B;フィールドに適用されることに注意してください。

![](assets/label_5.png)

## ロールの作成とラベルの割り当て {#assign-role}

**[!UICONTROL 役割]**&#x200B;は、組織内で同じ権限、ラベル、サンドボックスを共有するユーザーの集まりです。 ある&#x200B;**[!UICONTROL 役割]**に属する各ユーザーには、製品に含まれる Adobe のアプリとサービスに対する権限が付与されます。
独自の**[!UICONTROL 役割]**&#x200B;を作成して、インターフェイス内の特定の機能やオブジェクトに対するユーザーのアクセスを微調整することもできます。

ここでは、特定のユーザーに、「C2」というラベルの付いた&#x200B;**国籍**&#x200B;フィールドへのアクセス権を付与します。これをおこなうには、特定のユーザーの集まりで新しい&#x200B;**[!UICONTROL 役割]**&#x200B;を作成し、C2 ラベルを付与して、**[!UICONTROL メッセージ]**&#x200B;または&#x200B;**[!UICONTROL ジャーニー]**&#x200B;の&#x200B;**国籍**&#x200B;詳細を使用できるようにする必要があります。

1. [!DNL Permissions] 製品で、左側のパネルのメニューから「**[!UICONTROL 役割]**」を選択し、「**[!UICONTROL 役割を作成]**」をクリックします。**[!UICONTROL ラベル]**&#x200B;は、組み込みの役割に追加することもできます。

   ![](assets/role_1.png)

1. 新しい&#x200B;**[!UICONTROL 役割]**&#x200B;に、**[!UICONTROL 名前]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を追加します。ここでは「Restricted role demographic」とします。

1. ドロップダウンで&#x200B;**[!UICONTROL サンドボックス]**&#x200B;を選択します。

   ![](assets/role_2.png)

1. **[!UICONTROL リソース]**&#x200B;メニューで「**[!UICONTROL Adobe Experience Platform]**」をクリックし、様々な機能を開きます。 ここでは、「**[!UICONTROL メッセージ]**」を選択します。

   ![](assets/role_3.png)

1. ドロップダウンで、「**[!UICONTROL メッセージの表示]**」や「**[!UICONTROL ジャーニーの公開]**」など、選択した機能にリンクされている&#x200B;**[!UICONTROL 権限]**&#x200B;を選択します。

   ![](assets/role_6.png)

1. 新しく作成した&#x200B;**[!UICONTROL 役割]**&#x200B;を保存したら、「**[!UICONTROL プロパティ]**」をクリックして、役割へのアクセスをさらに設定します。

   ![](assets/role_7.png)

1. 「**[!UICONTROL ユーザー]**」タブで、「**[!UICONTROL ユーザーを追加]**」をクリックします。

   ![](assets/role_8.png)

1. 「**[!UICONTROL ラベル]**」タブで、「**[!UICONTROL ラベルを追加]**」を選択します。

   ![](assets/role_9.png)

1. 役割に追加したい&#x200B;**[!UICONTROL ラベル]**&#x200B;を選択して、「**[!UICONTROL 保存]**」をクリックします。この例では、先ほど制限したスキーマのフィールドにアクセスできるようにしたいユーザーに、ラベル「C2」を付与します。

   ![](assets/role_4.png)

これで「**Restricted role demographic**」の役割のユーザーが、C2 のラベルが付いたオブジェクトにアクセスできるようになりました。

## Adobe Journey Optimizer のラベル付きオブジェクトへのアクセス {#attribute-access-ajo}

新しいスキーマの「**国籍**」フィールド名と新しい役割にラベルを付けたら、この制限の影響を Adobe Journey Optimizer で確認できます。
この例では、C2 というラベルの付いたオブジェクトにアクセスできる最初のユーザー X は、制限された**[!UICONTROL フィールド名]**&#x200B;をターゲットにする条件を備えるジャーニーを作成します。次に、C2 というラベルの付いたオブジェクトにアクセスできない 2 人目のユーザー Y は、ジャーニーを公開する必要があります。

1. Adobe Journey Optimizer から、最初に「**[!UICONTROL データソース]**」を新しいスキーマに設定する必要があります。

   ![](assets/journey_1.png)

1. 新しく作成した&#x200B;**[!UICONTROL スキーマ]**&#x200B;の新しい&#x200B;**[!UICONTROL フィールドグループ]**&#x200B;を組み込みの&#x200B;**[!UICONTROL データソース]**&#x200B;に追加します。また、新しい外部&#x200B;**[!UICONTROLDデータソース]**&#x200B;および関連する&#x200B;**[!UICONTROL フィールドグループ]**&#x200B;を作成することもできます。

   ![](assets/journey_2.png)

1. 以前に作成した&#x200B;**[!UICONTROL スキーマ]**&#x200B;を選択した後、**[!UICONTROL フィールド]**&#x200B;カテゴリから「**[!UICONTROL 編集]**」をクリックします。

   ![](assets/journey_3.png)

1. ターゲット設定する&#x200B;**[!UICONTROL フィールド名]**&#x200B;を選択します。ここでは、制限付きの「**国籍**」フィールドを選択します。

   ![](assets/journey_4.png)

1. 次に、特定の国籍を持つユーザーにメッセージを送信するジャーニーを作成します。「**[!UICONTROL イベント]**」、「**[!UICONTROL 条件]**」の順に追加します。

   ![](assets/journey_5.png)

1. 制限付きの「**国籍**」フィールドを選択して、式の作成を開始します。

   ![](assets/journey_6.png)

1. 「**[!UICONTROL 条件]**」を編集し、制限付きの「**国籍**」フィールドを持つ特定の母集団をターゲットにします。

   ![](assets/journey_7.png)

1. 必要に応じてジャーニーをパーソナライズします。ここでは、「**[!UICONTROL メッセージ]**」アクションを追加します。

   ![](assets/journey_8.png)

ラベル C2 オブジェクトへのアクセス権を持たないユーザー Y が、このジャーニー、またはこの制限付きフィールドを使用するメッセージにアクセスする必要がある場合：

* ユーザー Y にはこのフィールドは表示されないので、制限付きのフィールド名を使用できません。

* ユーザー Y は、フィールド名が制限された式を詳細設定モードで編集できません。「`The expression is invalid. Field is no longer available or you don't have enough permission to see it`」のエラーが表示されます。

* ユーザー Y は式を削除できます。

* ユーザー Y はジャーニーやメッセージをテストできません。

* ユーザー Y は、ジャーニーまたはメッセージを公開できません。
