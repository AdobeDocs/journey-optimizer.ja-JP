---
title: Web 変更の管理
description: Journey Optimizer Web ページコンテンツの変更を管理する方法について説明します。
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: da12c416-3dcb-4c45-806c-ebe298c386f4
source-git-commit: d5b283a9c9b0e3e4104dddb3bcb4b47bbd749113
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 18%

---

# Web 変更の管理 {#manage-web-modifications}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_modifications"
>title="すべての変更を簡単に管理"
>abstract="このパネルを使用すると、web ページに追加したすべての調整とスタイルを移動して管理できます。"

Web ページに追加したすべてのコンポーネント、調整およびスタイルを簡単に管理できます。また、専用パネルから直接変更を追加することもできます。

## 変更パネルの操作 {#use-modifications-pane}

1. **[!UICONTROL 変更]**&#x200B;アイコンを選択して、対応するパネルを左側に表示します。

   ![](assets/web-designer-modifications-pane.png)

1. ページに加えた各変更を確認できます。

1. 不要な変更を選択し、 **[!UICONTROL 変更を削除]** オプションを **[!UICONTROL その他のアクション]** ボタンをクリックして削除します。

   ![](assets/web-designer-modifications-delete.png)

   >[!CAUTION]
   >
   >アクションを削除する場合は後続のアクションに影響する可能性があるので、慎重に作業を進めてください。

1. 複数の変更を同時に削除するには、 **[!UICONTROL 選択]** ボタン **[!UICONTROL 変更]** ウィンドウで、変更内容を確認し、 **[!UICONTROL 削除]** アイコン。

   ![](assets/web-designer-modifications-select-delete.png)

1. **[!UICONTROL 変更]**&#x200B;パネルの上部にある&#x200B;**[!UICONTROL その他のアクション]** ボタンから、すべての変更を一度に削除できます。

   ![](assets/web-designer-delete-modifications.png)

1. また、無効な変更のみを削除することもできます。つまり、他の変更によって上書きされた変更を削除できます。 例えば、テキストのカラーを変更してそのテキストを削除すると、テキストが存在しなくなったためにカラーの変更が無効になります。

1. アクションのキャンセルとやり直しは、 **[!UICONTROL 取り消し/やり直し]** ボタンを使用して、画面の右上に表示されます。

   ![](assets/web-designer-undo-redo.png)

   「**[!UICONTROL 取り消し]**」オプションと「**[!UICONTROL やり直し]**」オプションを切り替えるには、ボタンをクリックしたままにします。次に、ボタン自体をクリックして、目的のアクションを適用します。

## 専用パネルから変更を追加 {#add-modifications}

Web デザイナーを使用してページを編集する場合、 **[!UICONTROL 変更]** パネル — コンポーネントを選択し、web デザイナーインターフェイスから編集する必要はありません。 次の手順に従います。

1. 次から： **[!UICONTROL 変更]**&#x200B;をクリックし、 **[!UICONTROL その他のアクション]** 」ボタンをクリックします。

1. 選択 **[!UICONTROL 変更を追加]**.

   ![](assets/web-designer-add-modification.png)

1. 変更タイプを選択します。

   * **[!UICONTROL CSS セレクター]**- [詳細情報](#css-selector)
   * **[!UICONTROL ページ`<Head>`]** - [詳細情報](#page-head)

1. コンテンツを入力し、 **[!UICONTROL 保存]** 変更内容。

1. 次をクリック： **[!UICONTROL その他のアクション]** ボタンをクリックし、 **[!UICONTROL 情報]** をクリックして、詳細を表示します。

   ![](assets/web-designer-add-modification-info.png)

### CSS セレクター {#css-selector}

を追加するには、以下を実行します。 **CSS セレクター** タイプの変更：次の手順に従います。

1. 選択 **[!UICONTROL CSS セレクター]** を変更タイプとして使用します。

1. The **[!UICONTROL CSS 要素セレクター]** 「 」フィールドを使用すると、変更を適用するHTML要素（DOM ツリー内のノード）を見つけて選択できます。 <!--specify the desired CSS element that you want to modify.-->

   ![](assets/web-designer-add-modification-css.png)

1. アクションタイプを選択します (**[!UICONTROL コンテンツを設定]** または **[!UICONTROL 属性を設定]**) をクリックし、必要な情報/コンテンツを入力します。

   * **[!UICONTROL コンテンツを設定]**: **[!UICONTROL CSS 要素セレクター]** フィールドに入力します。

   * **[!UICONTROL 属性を設定]**：現在の CSS セレクターに関連付ける属性を指定して、このセレクターをこの属性でも識別できるようにします。 これをおこなうには、 **[!UICONTROL 属性名]** フィールドと、 **[!UICONTROL コンテンツ]** フィールドに入力します。 属性が既に存在する場合は値が更新されます。存在しない場合は、指定した名前と値で新しい属性が追加されます。

     ![](assets/web-designer-add-modification-css-attribute.png)

### ページ `<head>` {#page-head}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_head"
>title="カスタムコードを追加"
>abstract="HEAD要素は、メタデータのコンテナで、HTMLタグと BODY タグの間に配置されます。 SCRIPT 要素と STYLE 要素のみを追加します。 DIV タグやその他の要素を追加すると、残りのHEAD要素が BODY に表示される場合があります。"

カスタムコードを追加するには、 **[!UICONTROL ページ`<head>`]** 変更タイプ。

The `<head>` 要素は、メタデータ（データに関するデータ）のコンテナで、 `<html>` タグと `<body>` タグを使用します。 この場合、コードは本文やページの読み込みイベントを待たずに、ページの読み込みの開始時に実行されます。

The `<head>` 要素は、通常、ページの上部に JavaScript または CSS コードを追加するために使用されます。 後続のビジュアルアクションのセレクターは、このタブに追加されるHTML要素に応じて異なります。

を追加するには、以下を実行します。 **ページ`<head>`** タイプの変更：次の手順に従います。

1. 選択 **[!UICONTROL ページ`<head>`]** を変更タイプとして使用します。

   ![](assets/web-designer-add-modification-head-type.png)

1. カスタムコードを **[!UICONTROL コンテンツ]** ボックス。

   >[!CAUTION]
   >
   >追加できるのは `<script>` および `<style>` 要素を `<head>` 」セクションに入力します。 `<div>` タグなどの要素を追加すると、残りの `<head>` 要素が `<body>` に表示される場合があります。

1. 次をクリック： **[!UICONTROL 詳細編集オプション]** 」ボタンをクリックします。 式エディターが開きます。

   ![](assets/web-designer-add-modification-head-advanced.png)

   次の条件を満たす場合に、 [!DNL Journey Optimizer] 式エディターには、パーソナライゼーションおよびオーサリング機能がすべて含まれています。 [詳細情報](../personalization/personalization-build-expressions.md)

#### カスタムコードの例 {#custom-code-examples}

以下を使用すると、 **[!UICONTROL ページ`<head>`]** 変更タイプ：

* JavaScript をインラインで使用するか、外部 JavaScript ファイルにリンクします。

  例えば、要素の色を変更するには、次の手順を実行します。

  ```
  <script type="text/javascript">
  document.getElementById("element_id").style.color = "blue";
  </script>
  ```

* スタイルをインラインで設定するか、外部スタイルシートにリンクするかを設定します。

  例えば、オーバーレイ要素のクラスを定義するには、次のようにします。

  ```
  <style>
  .overlay
  { position: absolute; top:0; left: 0; right: 0; bottom: 0; background: red; }
  </style>
  ```

#### カスタムコードのベストプラクティス {#custom-code-best-practices}

+++ **カスタムコードは、必ず 1 つの要素にまとめます。**

以下に例を示します。

```
<script>
// Code goes here
</script>
```

変更が必要な場合は、このコンテナ内で変更を加えます。

カスタムコードが不要になった場合は、このコンテナを空のままにし、削除しないでください。 これにより、他のエクスペリエンスの変更が影響を受けなくなります。

+++

+++ **カスタムコードスクリプトで document.write アクションを実行しないでください。**

スクリプトは、非同期で実行されます。これにより、document.write アクションがページ上の誤った場所に表示されることがよくあります。 カスタムコードで作成されるスクリプトで document.write を使用することはお勧めしません。

+++

+++ **要素を作成して変更した場合は、元の要素を削除しないでください。**

変更を行うたびに、 **[!UICONTROL 変更]** パネル。 2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、その操作で変更する対象となる要素がなくなるので、変更が機能しなくなります。

+++

+++ **を使用する際は注意が必要です**[!UICONTROL &#x200B;ページ `<head>`]**同じ URL に影響を与える 2 つのキャンペーンの変更タイプ。**

を使用する場合、 **[!UICONTROL ページ`<head>`]** 同じ URL に影響を与える 2 つのキャンペーンの変更タイプを指定すると、両方のキャンペーンからページに JavaScript が挿入されます。 [!DNL Journey Optimizer] は、配信されるコンテンツの順序を自動的に決定します。 コードが配置に依存しないことを確認します。 コード内に競合がないことを確認するかどうかは、ユーザーが決定します。

+++

