---
title: Web コンテンツの編集
description: Journey Optimizer で web ページを作成し、そのコンテンツを編集する方法を学ぶ
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: 3847ac1d-2c0a-4f80-8df9-e8e304faf261
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 97%

---

# Web コンテンツの編集 {#edit-web-content}

ジャーニーまたはキャンペーンに [web エクスペリエンスを追加](create-web.md#create-web-experience)すると、web デザイナーでサイトのコンテンツを編集できるようになります。

[このビデオで web キャンペーンの作成方法について学ぶ](#video)

[!DNL Journey Optimizer] の web オーサリングには、**Adobe Experience Cloud Visual Helper** の Chrome ブラウザー拡張機能が利用されています。[詳細情報](web-prerequisites.md#visual-authoring-prerequisites)

>[!CAUTION]
>
>[!DNL Journey Optimizer] ユーザーインターフェイスで web ページへのアクセスや web ページを作成するには、[こちらのセクション](web-prerequisites.md)に記載されている前提条件を必ず満たすようにしてください。

各トピックについて詳しくは、次の節にアクセスしてください。

* [変更の管理](manage-web-modifications.md)

* [Web キャンペーンの監視](monitor-web-experiences.md)

## Web デザイナーの操作 {#work-with-web-designer}

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_surface"
>title="編集する URL の確認"
>abstract="上記で定義した web 設定に適用されるコンテンツの編集に使用する特定の web ページの URL を確認します。Web ページは、Adobe Experience Platform Web SDK を使用して実装する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja" text="詳細情報"

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_rule"
>title="編集する URL の入力"
>abstract="ルールに一致するすべてのページに適用されるコンテンツの編集に使用する特定の web ページの URL を入力します。 Web ページは、Adobe Experience Platform Web SDK を使用して実装する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja" text="詳細情報"

Web エクスペリエンスのオーサリングを開始するには、次の手順に従います。

1. キャンペーンの「**[!UICONTROL アクション]**」タブまたはジャーニーの web エクスペリエンスアクティビティで「**[!UICONTROL コンテンツを編集]**」を選択します。<!--change screen with rule-->

   ![](assets/web-campaign-edit-content.png)

1. ルールに一致するページを作成した場合は、このルールに一致する URL を入力する必要があります。変更は、ルールに一致するすべてのページに適用されます。ページのコンテンツが表示されます。

   >[!NOTE]
   >
   >Web 設定に 1 つの URL を入力した場合、パーソナライズする URL は既に入力されています。

   ![](assets/web-edit-enter-url.png)

   >[!CAUTION]
   >
   >Web ページには、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} を含める必要があります。[詳細情報](web-prerequisites.md#implementation-prerequisites)

1. 「**[!UICONTROL Web ページを編集]**」をクリックしてオーサリングを開始します。Web デザイナーが表示されます。

   ![](assets/web-designer.png)

   >[!NOTE]
   >
   >読み込みに失敗した web サイトを読み込もうとすると、[Visual Editing Helper のブラウザー拡張機能](#install-visual-editing-helper)のインストールを勧めるメッセージが表示されます。トラブルシューティングのヒントについては、[こちらのセクション](web-prerequisites.md#troubleshooting)をご覧ください。

1. キャンバスから要素（画像、ボタン、段落、テキスト、コンテナ、見出し、リンクなど）を選択します。[詳細情報](#content-components)

1. 用途：

   * コンテンツ、レイアウト、リンクの挿入、パーソナライゼーションなどを編集するためのコンテキストメニュー。

     ![](assets/web-designer-contextual-bar.png)

   * 各要素を編集、複製、削除または非表示にするための、右側パネルの上部にあるアイコン。

     ![](assets/web-designer-right-panel-icons.png)

   * 選択した要素に応じて動的に変化する右側のパネル。 例えば、要素の背景、テキスト編集、境界線、サイズ、位置、間隔、エフェクトまたはインラインスタイルを編集できます。

     ![](assets/web-designer-right-panel.png)

>[!NOTE]
>
>Web のコンテンツデザイナーは、E メールデザイナーと非常に似ています。詳しくは、[ [!DNL Journey Optimizer]](../email/get-started-email-design.md) でのコンテンツのデザインを参照してください。

## コンポーネントの使用 {#content-components}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_components"
>title="Web ページへのコンポーネントの追加"
>abstract="Web ページに多数のコンポーネントを追加し、必要に応じて編集できます。"

1. 左側の&#x200B;**[!UICONTROL コンポーネント]**&#x200B;パネルで、項目を選択します。Web ページに以下のコンポーネントを追加し、必要に応じて編集できます。

   * [ディバイダー](../email/content-components.md#divider)
   * [HTML](../email/content-components.md#HTML)
   * [画像](../email/content-components.md#image)
   * 見出し - このコンポーネントを使用することは、E メールデザイナーで&#x200B;**[!UICONTROL テキスト]**&#x200B;コンポーネントを使用することに似ています。[詳細情報](../email/content-components.md#text)
   * 段落 - このコンポーネントを使用することは、E メールデザイナーで&#x200B;**[!UICONTROL テキスト]**&#x200B;コンポーネントを使用することに似ています。[詳細情報](../email/content-components.md#text)
   * リンク

   ![](assets/web-designer-components.png)

1. ページにポインタを置いて、「**[!UICONTROL 前に挿入]**」または「**[!UICONTROL 後ろに挿入]**」ボタンをクリックして、コンポーネントをページ上の既存の要素に追加します。

   ![](assets/web-designer-insert-components.png)

   >[!NOTE]
   >
   >コンポーネントの選択を解除するには、キャンバス上部の青いコンテキストバナーにある **[!UICONTROL ESC]** ボタンをクリックします。

1. 必要に応じて、ページのコンテンツでコンポーネントを直接編集できます。

   ![](assets/web-designer-edit-header.png)

1. 右側のコンテキストパネルに表示されるスタイル（背景、テキストカラー、境界線、サイズ、位置など）を調整します。- 選択したコンポーネントによって異なります。

   ![](assets/web-designer-header-style.png)

## パーソナライゼーションの追加

パーソナライゼーションを追加するには、コンテナを選択し、表示されるコンテキストメニューバーからパーソナライゼーションアイコンを選択します。 パーソナライゼーションエディターを使用して、変更を追加します。[詳細情報](../personalization/personalization-build-expressions.md)

![](assets/web-designer-personalization.png)

## Web デザイナー内での移動 {#navigate-web-designer}

この節では、web デザイナーでの様々なナビゲーション方法について説明します。Web エクスペリエンスに追加された変更の表示および管理について詳しくは、[こちらの節](manage-web-modifications.md)を参照してください。

### パンくずリストの使用 {#breadcrumbs}

1. キャンバスから任意の要素を選択します。

1. 画面の左下に表示される「**[!UICONTROL パンくずリストを展開／折りたたむ]**」ボタンをクリックすると、選択した要素に関する情報をすばやく表示します。

   ![](assets/web-designer-breadcrumbs.png)

1. パンくずリストにポインタを合わせると、エディターで対応する要素がハイライト表示されます。

1. これを使用すると、ビジュアルエディター内で任意の親要素、兄弟要素または子要素に簡単に移動できます。

### 参照モードにスワップ {#browse-mode}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_browse"
>title="参照モードの使用"
>abstract="このモードでは、パーソナライズする選択した設定から該当するページに移動できます。"

専用ボタンを使用して、デフォルトの&#x200B;**[!UICONTROL デザイン]**&#x200B;モードから&#x200B;**[!UICONTROL 参照]**&#x200B;モードにスワップします。

![](assets/web-designer-browse-mode.png)

**[!UICONTROL 参照]**&#x200B;モードでは、パーソナライズする選択した設定から該当するページに移動できます。

これは、認証の後のページや、特定の URL で最初から使用できないページを処理する場合に特に便利です。例えば、認証を行い、アカウントページや買い物かごページに移動して、**[!UICONTROL デザイン]**&#x200B;モードに戻り、目的のページで変更を実行できます。

**[!UICONTROL 参照]**&#x200B;モードを使用すると、単一ページアプリケーションを作成する際に、web サイトのすべてのビューをナビゲートできます。[詳細情報](web-spa.md)

### デバイスサイズの変更 {#change-device-size}

Web デザイナーのディスプレイのデバイスサイズは、**[!UICONTROL タブレット]**&#x200B;または&#x200B;**[!UICONTROL モバイル横置き]**&#x200B;などの事前定義済みのサイズに変更したり、必要なピクセル数を入力してカスタムのサイズを定義したりできます。

また、ズームフォーカスを 25％から 400％に変更することもできます。

![](assets/web-designer-device.png)

デバイスサイズを変更する機能は、様々なデバイス、ウィンドウ、画面のサイズに適切にレンダリングされるレスポンシブサイト用に設計されています。レスポンシブサイトは、デスクトップ、ノートパソコン、タブレット、携帯電話を含む、あらゆる画面サイズに自動的に調整および適応します。

>[!CAUTION]
>
>特定のデバイスサイズで web エクスペリエンスを編集できます。ただし、セレクターが同じである限り、これらの変更は作業中のデバイスサイズだけでなく、すべてのサイズとデバイスに適用されます。 同様に、通常のデスクトップビューでのエクスペリエンスの編集は、そのデスクトップビューだけでなく、すべての画面サイズに適用されます。
>
>現在、[!DNL Journey Optimizer] は、デバイスサイズに固有のページの変更をサポートしていません。例えば、個別のサイト構造を持つ別のモバイル web サイトがある場合は、別のキャンペーンでそのモバイルサイトに固有の変更を行う必要があります。

## チュートリアルビデオ{#video}

次のビデオでは、[!DNL Journey Optimizer] キャンペーンで Web デザイナーを使用して web エクスペリエンスを作成する方法を確認できます。

>[!VIDEO](https://video.tv.adobe.com/v/3452636/?quality=12&learn=on&captions=jpn)