---
solution: Journey Optimizer
product: journey optimizer
title: 条件の作成
description: 条件の作成方法についてはこちらから
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター, 条件, ルール
exl-id: 246a4a55-059e-462c-ac1e-43b90f4abda4
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 100%

---

# 条件付きルールの操作 {#conditions}

条件付きルールとは、プロファイルの属性、オーディエンスメンバーシップ、コンテキストイベントなどの様々な条件に応じて、メッセージに表示するコンテンツを定義する一連のルールです。

条件付きルールは、式エディターを使用して作成し、コンテンツ間で再利用する場合に保存できます。[ライブラリに条件付きルールを保存する方法を学ぶ](#save)

>[!NOTE]
>
>個人が条件付きルールを保存または削除するには、[ライブラリ項目を管理](../administration/ootb-product-profiles.md)する権限が必要になります。保存した条件は、組織内のすべてのユーザーが使用できます。

## 条件付きルールビルダーへのアクセス {#access}

条件付きルールは、式エディター内の&#x200B;**[!UICONTROL 条件]**&#x200B;メニューで作成されます。このメニューには次のいずれかの方法でアクセスできます。

* メール本文のコンポーネントに対して動的コンテンツを有効にする場合は、メールデザイナーから。[メールに動的コンテンツを追加する方法を学ぶ](dynamic-content.md#emails)

  ![](assets/conditions-access-email.png)

* [式エディター](personalization-build-expressions.md)を使用してパーソナライゼーションを追加できる任意のフィールド。

  ![](assets/conditions-access-editor.png)

## 条件付きルールの作成 {#create-condition}

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions_create"
>title="条件の作成"
>abstract="プロファイル属性、コンテキストイベントまたはオーディエンスを組み合わせて、メッセージに表示するコンテンツを定義するルールを作成します。"

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions"
>title="条件の作成"
>abstract="プロファイル属性、コンテキストイベントまたはオーディエンスを組み合わせて、メッセージに表示するコンテンツを定義するルールを作成します。"

条件付きルールを作成する主な手順は次のとおりです。

1. 式エディターまたはメールデザイナーから&#x200B;**[!UICONTROL 条件]**&#x200B;メニューにアクセスし、「**[!UICONTROL 新規作成]**」をクリックします。

1. 必要に応じて、条件付きルールを作成します。これを行うには、左のメニューから目的の属性をキャンバスにドラッグ&amp;ドロップして配置します。

属性をキャンバスに組み合わせる手順は、セグメント作成のエクスペリエンスと似ています。ルールビルダーキャンバスの操作方法について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja#rule-builder-canvas)を参照してください。

    ![](assets/conditions-create.png)
    
    属性は次の 3 つのタブに整理されます。
    
    * **[!UICONTROL プロファイル]**：
    * **[!UICONTROL オーディエンス]** には、すべてのオーディエンス属性（ステータス、バージョンなど）がリストされます（[Adobe Experience Platform セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)の場合）。
    * **[!UICONTROL XDM 個別プロファイル]** には、Adobe Experience Platform で定義される[エクスペリエンスデータモデル（XDM）スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)に関連するすべてのプロファイル属性がリストされます。
    * **[!UICONTROL コンテキスト]**：ジャーニーでメッセージを使用している場合、コンテキストジャーニーフィールドをこのタブから使用できます。
    * **[!UICONTROL オーディエンス]**：[Adobe Experience Platform セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)で作成されたセグメント定義から生成されたすべてのオーディエンスがリストされます。

1. 条件付きルールの準備が整ったら、メッセージに追加して、動的コンテンツを作成できます。[動的コンテンツの追加方法を学ぶ](dynamic-content.md)

   また、ルールを保存して、後で再利用することもできます。[条件の保存方法を学ぶ](#save)

## 条件付きルールの保存 {#save}

頻繁に再利用する条件付きルールがある場合は、条件ライブラリに保存できます。保存されたルールはすべて共有され、組織内の個人がアクセスして使用できます。

>[!NOTE]
>
>ジャーニーのコンテキスト属性を利用する条件付きルールは、ライブラリに保存できません。

1. 条件編集画面で、「**[!UICONTROL 条件を保存]**」ボタンをクリックします。

1. ルールに名前と説明（オプション）を入力し、「**[!UICONTROL 追加]**」をクリックします。

   ![](assets/conditions-name-description.png)

1. 条件付きルールがライブラリに保存され、メッセージに動的コンテンツを作成するために使用できるようになります。[動的コンテンツの追加方法を学ぶ](dynamic-content.md)

## 保存済み条件付きルールの編集と削除 {#edit-delete}

「...」ボタンを使用すれば、いつでも条件付きルールを削除できます。

![](assets/conditions-open.png)

ライブラリに保存された条件付きルールは変更できません。ただし、これらを使用して新しいルールを作成することはできます。これを行うには、条件付きルールを開き、必要な変更を加えて、ライブラリに保存します。[ライブラリに条件を保存する方法を学ぶ](#save)
