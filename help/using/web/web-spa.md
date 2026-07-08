---
title: シングルページアプリケーションの作成
description: Journey Optimizer で SPA を作成し、様々なビューに変更を適用する方法を学ぶ
feature: Web Channel
topic: Content Management
role: User
level: Intermediate
exl-id: b33e4bca-d2e9-4610-9f04-008d47f686d0
TQID: https://experienceleague.adobe.com/clX0VeCEzwDOgxyFrzVaBIx-eH90KEYaHGTMzf2xvQc
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: c618a0dc-1818-4c6d-9916-0d92e6796f24
  - id: d056adbe-402d-4f42-9746-f3d424e598b1
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
source-git-commit: 6be6438a23ad673d97417c5205ae5985abfc52c2
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 92%

---

# シングルページアプリケーションの作成 {#web-author-spas}

>[!BEGINSHADEBOX]

**このページ：** Web SDKの実装でビューを定義し、参照モードでweb デザイナーで見つけ、選択したビューに変更を適用することで、Adobe Journey Optimizerでシングルページアプリケーションを作成する方法を説明します。

>[!ENDSHADEBOX]

## ビューについて {#about-views}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_modifications_views"
>title="選択したビューに変更を適用"
>abstract="変更は、選択したビューに対してのみ適用されます。 **参照**&#x200B;モードを使用して、ビューに移動します。 お探しのビューが見つからない場合"
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja" text="詳細情報"

**シングルページアプリケーション**（SPA）を web designer のビジュアルエディターで作成できるようになりました。 これにより、web ページの変更を適用する特定の&#x200B;**ビュー**&#x200B;を選択できます。

[このビデオでシングルページアプリケーションの作成方法を学ぶ](#video)

ビューは、サイト全体またはサイト上のビジュアル要素のグループ（ホームページ、製品サイト全体、すべてのチェックアウトページの配信設定フレームなど）として定義できます。

Adobe Experience Platform Web SDK 実装でビューを定義するには、1 回限りの開発者設定が必要です。 これにより、SPA 上で Adobe Journey Optimizer web キャンペーンを作成し、実行できます。

## Web SDK 実装でのビューの定義 {#define-views}

XDM ビューを Adobe [!DNL Journey Optimizer] で活用すると、マーケターは web ビジュアルエディターを使用して、SPA 上で web パーソナライゼーションおよび実験キャンペーンを実行できます。 [詳細情報](web-spa-implementation.md)

[!DNL Journey Optimizer] ユーザーインターフェイスでビューへのアクセスやビューを作成するには、[こちらの節](web-spa-implementation.md#implement-xdm-views)に記載されている手順に従うようにしてください。

## Web designer でビューの確認 {#discover-views}

Adobe Experience Platform Web SDK の実装で SPA の設定が完了したら、変更を適用する web サイトのすべてのビューに移動する必要があります。 次の手順に従います。

1. [Web ジャーニーまたはキャンペーンを作成](create-web.md)して、[web designer](web-visual-editor.md) にアクセスします。

   現在表示中のビューは左上に表示されます。

   ![](assets/web-designer-view-home.png)

1. **[!UICONTROL 参照]**&#x200B;モードにスワップします。 [詳細情報](web-visual-editor.md#browse-mode)

   ![](assets/web-designer-view-browse.png)

1. Web サイトの様々なページ間を移動し、それらすべてを確認します。 上部に表示されるビュー名は、別のページを閲覧する際に変更されます。

   ![](assets/web-designer-other-view.png)

## 他のビューへの変更の適用 {#apply-modifications-views}

特定のビューで変更を追加した後は、選択した他のビューに適用できます。 次の手順に従います。

>[!CAUTION]
>
>**[!UICONTROL 参照]**&#x200B;モードを使用してビューが見つからない場合は、変更を適用するために選択することはできません。 [詳細情報](#discover-views)

1. **[!UICONTROL 変更]**&#x200B;アイコンを選択して、対応するパネルを左側に表示します。

   ![](assets/web-designer-view-modifications-pane.png)

1. 変更を選択し、その横にある「**[!UICONTROL その他のアクション]**」ボタンをクリックします。 「**[!UICONTROL 他のビューに適用]**」を選択します。

   ![](assets/web-designer-modifications-more-actions.png)

1. 変更を適用するビューを選択します。

   ![](assets/web-designer-modifications-apply-to.png)

1. 「**[!UICONTROL 適用]**」をクリックします。

1. **[!UICONTROL 参照]**&#x200B;モードにスワップして、目的のページに変更が適用されていることを確認します。

   ![](assets/web-designer-modifications-applied-view.png)

## チュートリアルビデオ{#video}

このビデオでは、次の方法を説明します。

* **[!UICONTROL 参照]**&#x200B;モードを使用して SPA ビューを見つける
* 現在のビューでオーサリングを実行
* 複数のビューまたは検出されたすべてのビューに web サイトの変更を適用
* 変更に対する一括アクションを実行

>[!VIDEO](https://video.tv.adobe.com/v/3424536/?quality=12&learn=on)
