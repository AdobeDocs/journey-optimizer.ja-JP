---
solution: Journey Optimizer
product: journey optimizer
title: 条件の作成
description: 条件の作成方法について説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 246a4a55-059e-462c-ac1e-43b90f4abda4
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# 条件付きルールの使用 {#conditions}

条件付きルールとは、プロファイルの属性、セグメントメンバーシップ、状況に応じたイベントなど、様々な条件に基づいて、メッセージにどのコンテンツを表示するかを定義するルールの集合です。

条件付きルールは、式エディターを使用して作成され、コンテンツ間で再利用する場合に格納することができます。 [条件付きルールをライブラリに保存する方法について説明します。](#save)

>[!NOTE]
>
>条件付きルールを保存または削除するには、「ライブラリアイテム ](../administration/ootb-product-profiles.md) の [ 管理」権限が必要です。保存された条件は、組織内のすべてのユーザーが使用できるようになっています。

## 条件付き規則ビルダーにアクセスする {#access}

条件付きルールは、次のいずれかの方法で、式エディター内のメニューから **[!UICONTROL Conditions]** 作成されます。

* 電子メールでは、電子メールの本文に含まれるコンポーネントに動的コンテンツを有効にすることができます。 [電子メールに動的コンテンツを追加する方法について説明しています。](dynamic-content.md#emails)

   ![](assets/conditions-access-email.png)

* 任意のフィールドで、 [ エクスプレッションエディター ](personalization-build-expressions.md) を使用してパーソナル化を追加することができます。

   ![](assets/conditions-access-editor.png)

## 条件付きルールの作成 {#create-condition}

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions_create"
>title="条件の作成"
>abstract="プロファイル属性、状況に応じたイベント、対象ユーザーを作成し、メッセージに表示するコンテンツを定義するための構築ルールを作成します。"

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions"
>title="条件の作成"
>abstract="プロファイル属性、状況に応じたイベント、対象ユーザーを作成し、メッセージに表示するコンテンツを定義するための構築ルールを作成します。"

条件付きルールを作成する手順は、次のとおりです。

1. 式エディターまたは電子メールデザイナーからメニューに **[!UICONTROL Conditions]** アクセスし、をクリック **[!UICONTROL Create new]** します。

1. 必要に応じて条件付きルールを作成します。 そのためには、ドラッグ &amp; ドロップして、左側のメニューで目的の属性をカンバスに配置します。

   属性を canvas に組み合わせる手順は、セグメントの作成操作と似ています。 ルールビルダーの canvas の操作方法について詳しくは、このドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#rule-builder-canvas) を [ 参照してください。

   ![](assets/conditions-create.png)

   属性は、次の3つのタブに分かれています。

   * **[!UICONTROL Profile]**:
      * **[!UICONTROL Segment Membership]** すべてのセグメント属性を一覧表示します (ステータス、バージョンなど)。 Adobe エクスペリエンスプラットフォームセグメンテーションサービス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) について [ は、
      * **[!UICONTROL XDM Individual profiles]** Adobe エクスペリエンスプラットフォームで定義されたエクスペリエンスデータモデル (XDM) スキーマ ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) に関連する [ すべてのプロファイル属性が一覧表示されます。
   * **[!UICONTROL Contextual]**: メッセージが旅に使用されると、状況に応じた「道」フィールドが、このタブで表示されます。
   * **[!UICONTROL Audiences]**: Adobe エクスペリエンスプラットフォームセグメンテーションサービス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) で [ 作成されたセグメントから生成された対象ユーザーすべてが一覧表示されます。

1. 条件付きルールの準備が完了したら、メッセージに追加することで、動的コンテンツを作成することができます。 [動的コンテンツを追加する方法について説明します。](dynamic-content.md)

   ルールを保存して、後で再利用することもできます。 [条件を保存する方法を学習します。](#save)

## 条件付き規則の保存 {#save}

頻繁に再利用する条件ルールがある場合は、条件ライブラリに保存しておくことができます。 保存されているすべてのルールは共有され、組織内のユーザーがアクセスして使用することができます。

>[!NOTE]
>
>Journeys コンテキスト属性を利用する条件付きルールは、ライブラリに保存できません。

1. 「条件版」画面で、ボタンをクリック **[!UICONTROL Save condition]** します。

1. ルールに名前と説明 (オプション) を指定して、をクリック **[!UICONTROL Add]** します。

   ![](assets/conditions-name-description.png)

1. 条件付き規則がライブラリに保存されます。 これを使用してメッセージに動的コンテンツを作成できるようになりました。 [動的コンテンツを追加する方法について説明します。](dynamic-content.md)

## 保存された条件付きルールの編集と削除 {#edit-delete}

「楕円」ボタンを使用して、いつでも条件式を削除することができます。

![](assets/conditions-open.png)

ライブラリに保存された条件付きルールを変更することはできません。 ただし、それらを使用して新しいルールを作成することもできます。 これを行うには、条件付きルールを開き、必要な変更を加えてライブラリに保存します。 [条件をライブラリに保存する方法を学習します。](#save)
