---
solution: Journey Optimizer
product: journey optimizer
title: 式フラグメントの使用
description: ' [!DNL Journey Optimizer] パーソナライゼーションエディターで式フラグメントを使用する方法を説明します。'
feature: Personalization, Fragments
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター, ライブラリ, パーソナライゼーション
exl-id: 74b1be18-4829-4c67-ae45-cf13278cda65
source-git-commit: abd5f388a41cc85c710cdb8c8e51c7fe381714ad
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 100%

---

# 式フラグメントを活用 {#use-expression-fragments}

**パーソナライゼーションエディター**&#x200B;を使用すると、現在のサンドボックスに作成または保存されたすべての式フラグメントを活用できます。

フラグメントは、[!DNL Journey Optimizer] キャンペーンおよびジャーニー全体で参照できる、再利用可能なコンポーネントです。この機能を使用すると、複数のカスタムコンテンツブロックを事前に構築し、マーケティングユーザーはそのコンテンツブロックを使用して、改善されたデザインプロセスでコンテンツを迅速に組み立てることができます。[詳しくは、フラグメントの作成と管理の方法を参照してください](../content-management/fragments.md)。

➡️ [フラグメントの管理、作成、使用方法について詳しくは、このビデオをご覧ください](../content-management/fragments.md#video-fragments)

## 式フラグメントの使用 {#use-expression-fragment}

コンテンツに式フラグメントを追加するには、次の手順に従います。

>[!NOTE]
>
>1 回の配信で最大 30 個のフラグメントを追加できます。フラグメントをネストできるのは 1 レベルまでです。

1. [パーソナライゼーションエディター](personalization-build-expressions.md)を開き、左側のパネルで「**[!UICONTROL フラグメント]**」ボタンを選択します。

   リストには、現在のサンドボックスで作成またはフラグメントとして保存されたすべての式フラグメントが表示されます。フラグメントは作成日で並べ替えられます。最近追加した式フラグメントがリストの最初に表示されます。[詳細情報](../content-management/fragments.md#create-expression-fragment)

   ![](assets/expression-fragments-pane.png)

   また、このリストを更新することもできます。

   >[!NOTE]
   >
   >コンテンツの編集中に一部のフラグメントが変更または追加された場合、リストは最新の変更内容に更新されます。

1. 式フラグメントの横にある「+」アイコンをクリックして、対応するフラグメント ID をエディターに挿入します。

   ![](assets/expression-fragment-add.png)

   >[!CAUTION]
   >
   >任意の&#x200B;**ドラフト**&#x200B;または&#x200B;**ライブ**&#x200B;フラグメントをコンテンツに追加できます。ただし、ジャーニーまたはキャンペーンで&#x200B;**ドラフト**&#x200B;ステータスのフラグメントを使用している場合、そのジャーニーまたはキャンペーンはアクティブ化できません。ジャーニーまたはキャンペーンの公開時に、ドラフトフラグメントにエラーが表示されるので、公開するには承認する必要があります。

1. フラグメント ID を追加したら、対応する式フラグメントを開いてインターフェイスから[編集](../content-management/fragments.md#edit-fragments)すると、変更が同期されます。これらは、そのフラグメント ID を含むすべてのドラフトまたはライブジャーニー／キャンペーンに自動的に生成されます。

1. フラグメントの横にある「**[!UICONTROL その他のアクション]**」ボタンをクリックします。開いたコンテキストメニューから「**[!UICONTROL フラグメントを表示]**」を選択すると、そのフラグメントに関する詳細情報が表示されます。また、**[!UICONTROL フラグメント ID]** も表示され、ここからコピーできます。

   ![](assets/expression-fragment-view.png)

1. コンテキストメニューの「**[!UICONTROL フラグメントを開く]**」オプションを使用するか、**[!UICONTROL フラグメント情報]**&#x200B;パネルから式フラグメントを別のウィンドウで開き、そのコンテンツとプロパティを編集できます。[詳しくは、フラグメントの編集方法を参照してください](../content-management/fragments.md#edit-fragments)

   ![](assets/expression-fragment-open.png)

1. その後、[パーソナライゼーションエディター](personalization-build-expressions.md)のパーソナライズ機能とオーサリング機能をすべて使用して、通常どおりコンテンツをカスタマイズして検証できます。

>[!NOTE]
>
>複数の改行を含む式フラグメントを作成し、[SMS](../sms/create-sms.md#sms-content) または[プッシュ](../push/design-push.md)コンテンツで使用する場合、改行は保持されます。したがって、[SMS](../sms/send-sms.md) または[プッシュ](../push/send-push.md)メッセージを送信する前に必ずテストしてください。

## 暗黙的変数の使用 {#implicit-variables}

暗黙的変数は、既存のフラグメント機能を強化して、コンテンツの再利用性とスクリプトのユースケースの効率を向上させます。フラグメントは入力変数を使用し、キャンペーンおよびジャーニーコンテンツで使用できる出力変数を作成できます。

この機能は、例えば、現在のキャンペーンやジャーニーに基づいてメールのトラッキングパラメーターを初期化し、これらのパラメーターをメールコンテンツに追加されたパーソナライズされたリンクに使用できます。

次のようなユースケースが考えられます。

1. フラグメントでの入力変数の使用

   フラグメントをキャンペーン／ジャーニーアクションコンテンツで使用すると、フラグメント外で宣言された変数を活用できます。以下に例を示します。

   ![](../personalization/assets/variable-in-a-fragment.png)

   `utm_content` 変数がキャンペーンコンテンツで宣言されていることがわかります。**ヒーローブロック**&#x200B;というフラグメントが使用されると、`utm_content` パラメーター値が追加されるリンクが表示されます。最終結果は、`https://luma.enablementadobe.com?utm_campaign= Product_launch&utm_content= start_shopping` です。

1. フラグメントの出力変数の使用

   フラグメント内で計算または定義された変数は、コンテンツ内で使用できます。次の例では、フラグメント **F1** によって、一連の変数が宣言されています。

   ![](../personalization/assets/personalize-with-variables.png)

   メールコンテンツでは、次のパーソナライズ機能を使用できます。

   ![](../personalization/assets/use-fragment-variable.png)

   フラグメント F1 は、変数 `utm_campaign` および `utm_content` を初期化します。次に、メッセージコンテンツ内のリンクに、これらのパラメーターが追加されます。最終結果は、`https://luma.enablementadobe.com?utm_campaign= Product_launch&utm_content= start_shopping` です。

>[!NOTE]
>
>実行時に、システムはフラグメント内の内容を展開し、パーソナライゼーションコードを上から下に解釈します。このことを念頭に置くと、より複雑なユースケースを実現できます。例えば、フラグメント F1 がその下にある別のフラグメント F2 に変数を渡すことができます。また、ビジュアルフラグメント F1 から、ネストされた式フラグメント F2 に変数を渡すこともできます。


## 編集可能フィールドのカスタマイズ {#customize-fields}

変数を使用して式フラグメントの特定の部分が編集可能になっている場合は、特定の構文を使用して、それらのデフォルト値を上書きできます。[詳しくは、フラグメントをカスタマイズ可能にする方法を参照してください](../content-management/customizable-fragments.md)

フィールドをカスタマイズするには、次の手順に従います。

1. **フラグメント**&#x200B;メニューからコードにフラグメントを挿入します。

1. 構文の最後にある `<fieldId>="<value>"` コードを使用して、変数のデフォルト値を上書きします。

   次の例では、ID が「sports」である変数の値を「yoga」値で上書きしています。これにより、フラグメントコンテンツで「sport」変数が参照されているすべての箇所に「yoga」が表示されます。

   ![](../content-management/assets/fragment-expression-use.png)

メールの作成時に編集可能なフィールドを式フラグメントに追加し、その値を上書きする方法を示す例について詳しくは、[この節](../content-management/customizable-fragments.md#example)を参照してください。

## 継承の解除 {#break-inheritance}

パーソナライゼーションエディターにフラグメント ID を追加すると、元の式フラグメントに行った変更が同期されます。

ただし、式フラグメントのコンテンツをエディターにペーストすることもできます。コンテキストメニューから「**[!UICONTROL フラグメントをペースト]**」を選択して、そのコンテンツを挿入します。

![](assets/expression-fragment-paste.png)

その場合、元のフラグメントからの継承は壊れます。フラグメントのコンテンツはエディターにコピーされ、変更内容は同期されなくなります。

これは、元のフラグメントにリンクされなくなったスタンドアロン要素になります。コード内の他の要素として編集できます。

