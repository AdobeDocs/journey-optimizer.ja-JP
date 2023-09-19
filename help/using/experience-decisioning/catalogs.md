---
title: 品目カタログ
description: 項目カタログの操作方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---


# 品目カタログ {#catalog}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [Experience Decisioning の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目を管理
   * **[項目カタログを設定](catalogs.md)**
   * [決定項目の作成](items.md)
   * [項目コレクションを管理](collections.md)
* 項目の選択を設定
   * [決定ルールの作成](rules.md)
   * [ランキングメソッドの作成](ranking.md)
* [選択戦略を作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

エクスペリエンス判定では、カタログは、判定項目を整理するための中央コンテナとして機能します。 各カタログは、決定項目に割り当て可能なすべての属性を含む、Adobe Experience Platformスキーマにリンクされます。

現時点では、作成されたすべての決定項目は、単一の「オファー」カタログ内に統合され、 **[!UICONTROL 項目]** メニュー。

![](assets/catalogs-list.png)

決定項目の属性が保存されるカタログのスキーマにアクセスするには、次の手順に従います。

1. 項目リストで、 **[!UICONTROL スキーマを編集]** の横にあるボタン **[!UICONTROL 項目を作成]** 」ボタンをクリックします。

1. 以下の構造に従って、新しいタブでカタログのスキーマが開きます。

   * The **`_experience`** ノードには、名前、開始日、終了日、説明など、標準の決定項目属性が含まれます。
   * The **`_<imsOrg>`** ノードは、カスタムの決定項目属性を格納します。 デフォルトでは、カスタム属性は設定されませんが、必要に応じて必要な数だけ追加できます。 完了すると、カスタム属性が標準属性と共に、判定項目作成画面に表示されます。

   ![](assets/catalogs-schema.png)

1. スキーマにカスタム属性を追加するには、 **`_<imsOrg>`** ノードに移動し、構造内の目的の場所で「+」ボタンをクリックします。

   ![](assets/catalogs-add.png)

1. 追加した属性に必要なフィールドに入力し、 **[!UICONTROL 適用]**.

   >[!CAUTION]
   >
   >現時点では、Experience Decisioning は、以下に示すデータタイプのみをサポートしています。 これらのデータタイプに該当しないフィールドは、決定項目の作成時には使用できません。
   >* 文字列
   >* ブール値
   >* 数値

   Adobe Experience Platformスキーマの操作方法に関する詳細については、 [XDM システムドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.htm?lang=ja).

1. 目的のカスタム属性を追加したら、スキーマを保存します。 新しいフィールドが、 **[!UICONTROL カスタム属性]** 」セクションに入力します。
