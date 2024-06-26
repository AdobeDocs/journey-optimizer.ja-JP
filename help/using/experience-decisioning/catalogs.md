---
title: 項目カタログ
description: 項目カタログの使用方法を説明します
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供"
exl-id: 2d118f5a-32ee-407c-9513-fe0ebe3ce8f0
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 100%

---

# 項目カタログ {#catalog}

エクスペリエンス判定では、カタログは、決定項目を整理するための中心的なコンテナとして機能します。各カタログは、決定項目に割り当て可能なすべての属性を含む、Adobe Experience Platform スキーマにリンクされます。

現時点では、作成されたすべての決定項目は、単一の「オファー」カタログ内に統合され、**[!UICONTROL カタログ]**&#x200B;メニューからアクセスできます。

![](assets/catalogs-list.png)

決定項目の属性が保存されるカタログのスキーマにアクセスするには、次の手順に従います。

1. 項目リストで、「**[!UICONTROL 項目を作成]**」ボタンの横にある「**[!UICONTROL スキーマを編集]**」ボタンをクリックします。

1. 以下の構造に従って、新しいタブでカタログのスキーマが開きます。

   * **`_experience`** ノードには、名前、開始日、終了日、説明など、標準の決定項目属性が含まれます。
   * **`_<imsOrg>`** ノードには、カスタムの決定項目属性が格納されています。デフォルトでは、カスタム属性は設定されませんが、必要に応じて必要な数だけ追加できます。完了すると、カスタム属性が標準属性と共に、決定項目作成画面に表示されます。

   ![](assets/catalogs-schema.png)

1. スキーマにカスタム属性を追加するには、**`_<imsOrg>`** ノードに展開し、構造内の目的の場所で「+」ボタンをクリックします。

   ![](assets/catalogs-add.png)

1. 追加した属性に必要なフィールドに入力し、「**[!UICONTROL 適用]**」をクリックします。

   >[!CAUTION]
   >
   >現時点では、Experience Decisioning は、文字列、整数、ブール値、日付、日時、決定アセットの各データタイプのみをサポートしています。これらのデータタイプに該当しないフィールドは、決定項目やカタログの作成時には使用できません。

   決定アセット属性を持つ属性に入力される値はパブリック URL です。ほとんどの場合、これは画像を指します。

   Adobe Experience Platform スキーマの操作方法について詳しくは、[XDM システムドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja)を参照してください。

1. 目的のカスタム属性を追加したら、スキーマを保存します。新しいフィールドは「**[!UICONTROL カスタム属性]** 」セクション内の決定項目作成画面で使用可能になりました。
