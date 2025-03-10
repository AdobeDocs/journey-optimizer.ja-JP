---
solution: Journey Optimizer
product: journey optimizer
title: パーソナライゼーションの追加
description: パーソナライゼーションエディターを使用してパーソナライゼーションを追加する方法を説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター, 説明, 開始
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: 78c1464ccddec75e4827cbb1877d8fab5ac08b90
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 47%

---

# パーソナライゼーションの追加 {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="パーソナライゼーションエディターについて"
>abstract="パーソナライゼーションエディターを使用すると、すべてのデータを選択、整理、カスタマイズ、検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。"

パーソナライゼーションエディターは、[!DNL Journey Optimizer] のパーソナライズ機能の中核です。メール、プッシュ、オファーなど、パーソナライゼーションを定義する必要があるすべてのコンテキストで利用できます。

パーソナライゼーションエディターインターフェイスでは、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。

![](assets/perso_ee1.png)

## パーソナライゼーションを追加できる場所

![ パーソナライゼーションアイコンを追加 ](assets/do-not-localize/add-perso-icon.svg) アイコンを使用して、すべてのフィールドの **[!DNL Journey Optimizer]** にパーソナライゼーションを追加できます。

### メッセージ

メッセージでは、「**[!UICONTROL 件名]** フィールドなど、メッセージ内の様々な場所にパーソナライゼーションを追加できます。

![](assets/perso_subject.png)

コンテンツの他のセクションに追加することもできます。 例えば、[ プッシュ通知 ](../push/push-gs.md) の場合、パーソナライゼーションは **タイトル**、**本文**、**カスタムサウンド**、**バッジ**、**カスタムデータ** フィールドに追加できます。

### E メールデザイナー

[ メールDesigner](../email/get-started-email-design.md) でメールコンテンツを編集する際に、コンテキストツールバーのアイコンを使用して、テキストブロックや URL にパーソナライゼーションを追加できます。

![](assets/perso_insert.png)

### オファー

**オファーの表示域** でテキストタイプのコンテンツを使用する場合、パーソナライゼーションを追加できます。 [ パーソナライズされたオファーを作成する方法を学ぶ ](../offers/offer-library/creating-personalized-offers.md)

### URL

Journey Optimizerでは、メッセージ内の **URL** をパーソナライズすることもできます。  パーソナライズされた URL は、プロファイル属性に応じて、受信者を web サイトの特定のページに誘導するか、パーソナライズされたマイクロサイトに誘導します。URL のパーソナライゼーションは、**外部リンク**、**購読解除リンク** および **オプトアウト** のリンクで使用できます。

+++パーソナライズされた URL のサンプルを参照

* `https://www.adobe.com/users/{{profile.person.name.lastName}}`
* `https://www.adobe.com/users?uid={{profile.person.name.firstName}}`
* `https://www.adobe.com/usera?uid={{context.journey.technicalProperties.journeyUID}}`
* `https://www.adobe.com/users?uid={{profile.person.crmid}}&token={{context.token}}`

+++

![](assets/perso-url.png){width="50%"}

>[!NOTE]
>
>パーソナライゼーションエディターでパーソナライズされた URL を編集する場合、セキュリティ上の理由から、ヘルパー関数とオーディエンスメンバーシップが無効になります。
>
>スペースは、URL 内で使用されるパーソナライゼーショントークンではサポートされていません。

## Personalization ソース {#sources}

画面の左側には、パーソナライゼーションのソースを選択できるドメインセレクターが表示されます。利用可能なソースは次のとおりです。

* **[!UICONTROL プロファイル属性]**：[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}に記載のプロファイルスキーマに関連付けられているすべての参照をリストします。
* **[!UICONTROL オーディエンス]**：Adobe Experience Platform セグメント化サービスで作成されたすべてのオーディエンスをリストします。セグメント化について詳しくは、[こちら](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target="_blank"}を参照してください。
* **[!UICONTROL オファー決定]**：特定のプレースメントに関連付けられているすべてのオファーを一覧表示します。配置を選択し、コンテンツにオファーを挿入します。オファーの管理方法に関する詳細なドキュメントについては、[この節](../offers/get-started/starting-offer-decisioning.md)を参照してください。
* **[!UICONTROL コンテキスト属性]**：チャネルアクションアクティビティ（メール、プッシュ、SMS）をジャーニーまたはキャンペーンで使用する場合、イベントやプロパティに関連するコンテキスト属性をパーソナライズに使用できます。コンテキスト属性を活用したパーソナライゼーションの例については、[この節](personalization-use-case.md)を参照してください。

>[!NOTE]
>
>コンポジションワークフローを使用して生成されたエンリッチメント属性でオーディエンスをターゲットにしている場合は、これらのエンリッチメント属性を活用してメッセージをパーソナライズできます。[オーディエンスのエンリッチメント属性の使用方法を学ぶ](../audience/about-audiences.md#enrichment)

## パーソナライゼーションの追加 {#add}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor_autocomplete"
>title="オートコンプリート"
>abstract="このオプションを切り替えると、入力中にコードが自動的に提案され、完了します。 この機能は、HTMLとテキストのフォーマットでのみ使用でき、プロファイルとコンテキストの属性をサポートしています。 切替スイッチで無効にした場合、エディターは代わりにネイティブのHTML コードのオートコンプリートを提供します。"

中央のワークスペースは、パーソナライゼーション構文を構築する場所です。 属性を使用してメッセージをパーソナライズするには、左側のナビゲーションパネルで属性を見つけ、「`+`」ボタンをクリックして式に追加します。

`+` アイコンの横にある省略記号メニューを使用すると、各属性の詳細を取得したり、使用頻度の高い属性をお気に入りに追加したりできます。 お気に入りに追加した属性には、左側のナビゲーションパネルの **[!UICONTROL お気に入り]** メニューからアクセスできます。

さらに、文字列タイプのプロファイル属性が空の場合に表示されるデフォルトの代替テキストを定義できます。これを行うには、属性の横にある省略記号ボタンをクリックし、「**[!UICONTROL 代替テキストで挿入]**」を選択します。プロファイルの属性の値が空の場合にデフォルトで表示するテキストを書き込み、「**[!UICONTROL 追加]**」をクリックします。

![](assets/attribute-details.png)

次の例では、パーソナライゼーションエディターを使用して、本日が誕生日のプロファイルを選択し、この日に対応する特定のオファーを挿入してカスタマイズを完了します。

![](assets/perso_ee2.png)

## 式を編集するツール

中央のワークスペースには、パーソナライゼーション式を記述するのに役立つ様々なツールが用意されています。

![](assets/perso-workspace.png)

利用可能なオプションは次のとおりです。

1. **[!UICONTROL 検索]** / **[!UICONTROL 検索と置換]**：式を検索して、コードの一部を自動的に置換します。
1. **[!UICONTROL 取り消し]** / **[!UICONTROL やり直し]**：最後の操作を取り消し/やり直します。
1. **[!UICONTROL オートコンプリート]**：入力中にコードを自動的に提案して完了します。 この機能は、HTMLとテキストのフォーマットでのみ使用でき、プロファイルとコンテキストの属性をサポートしています。 切替スイッチで無効にした場合、エディターは代わりにネイティブのHTML コードのオートコンプリートを提供します。

   ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"}

1. **[!UICONTROL HTML]** / **[!UICONTROL JSON]** / **[!UICONTROL テキスト]**: コードのフォーマットを識別します。 これにより、選択した言語に基づいて検証およびオートコンプリート機能を適応させることができます。
1. **[!UICONTROL Validate]**：式の構文を確認します。 詳しくは、[この節](../personalization/personalization-build-expressions.md)を参照してください。
1. **[!UICONTROL フラグメントとして保存]**：式を式フラグメントとして保存します。 詳しくは、[この節](../content-management/save-fragments.md#save-as-expression-fragment)を参照してください。
1. **[!UICONTROL フォントサイズ]**：読みやすくするために、エディター内のコンテンツのフォントサイズを調整します。
1. **[!UICONTROL ワードラップ]**：ワードラップを有効または無効にして、長い式を 1 行に表示したり、エディター内で折り返したりできます。 次のようなオプションがあります。
   * **オフ** （デフォルト） – 単語の折り返しを行いません。 長い線がエディタービューを超えて伸び、水平スクロールが必要な場合。
   * **オン** - エディターの幅で行を折り返します。
   * **ワードラップ列** – 行文字が 80 文字に達すると行を折り返します。
   * **境界付き** - エディターの幅または 80 文字のいずれか小さい方で行を折り返します。

ナビゲーションウィンドウでは、パーソナライゼーション式を作成するのに役立つ追加機能を使用できます。

![](assets/perso-features.png)

* **[!UICONTROL ヘルパー関数]** - ヘルパー関数を使用すると、データの操作（計算、データのフォーマットやコンバージョン、条件、パーソナライゼーションのコンテキストでの操作など）を実行できます。 [ 使用可能なヘルパー関数について詳しくはこちらを参照 ](functions/functions.md)

* **[!UICONTROL お気に入り]** – お気に入りに追加した属性がこのリストに表示されます。 これにより、最も頻繁に使用する項目にすばやくアクセスできます。 属性をお気に入りに追加するには、「。..」メニューをクリックし、**[!UICONTROL お気に入りに追加]** を選択します。

* **[!UICONTROL 条件]** - ライブラリで作成した条件付きルールを活用して、メッセージに動的コンテンツを追加します。 これにより、条件に基づいてメッセージの複数のバリアントを作成できます。 [ 動的コンテンツの作成方法を学ぶ ](../personalization/get-started-dynamic-content.md)

* **[!UICONTROL フラグメント]** – 作成または現在のサンドボックスに保存された式フラグメントを活用します。 フラグメントは、[!DNL Journey Optimizer] キャンペーンおよびジャーニー全体で参照できる、再利用可能なコンポーネントです。この機能を使用すると、複数のカスタムコンテンツブロックを事前に構築し、マーケティングユーザーはそのコンテンツブロックを使用して、改善されたデザインプロセスでコンテンツを迅速に組み立てることができます。[ パーソナライゼーションに式フラグメントを使用する方法を学ぶ ](../personalization/use-expression-fragments.md)

パーソナライゼーション式を準備できたら、パーソナライゼーションエディターで検証する必要があります。詳しくは、[この節](../personalization/personalization-build-expressions.md)を参照してください。

## 検証メカニズム {#validation-mechanisms}

「**追加**」ボタンをクリックしてエディターウィンドウを閉じると、式の検証は自動的に実行されます。 「**検証**」ボタンを使用して、パーソナライゼーション構文を確認することもできます。

![](assets/perso_validation1.png)

以下のセクションを展開して、パーソナライゼーションの検証時に発生する可能性のある一般的なエラーを確認します。

+++一般的なエラー

* **パス「XYZ」が見つかりません**

スキーマで定義されていないフィールドを参照しようとしたとき。

この場合、**firstName1** は、プロファイルスキーマの属性として定義されていません。

```
{{profile.person.name.firstName1}}
```

* **変数「XYZ」のタイプが一致しません。予想される配列です。文字列が見つかりました。**

配列ではなく文字列を反復処理する場合。

この場合、**product** は配列ではありません。

```
{{each profile.person.name.firstName as |product|}}
 {{product.productName}}
{{/each}}
```

* **ハンドルバー構文が無効です。`‘[XYZ}}’`** が見つかりました

無効なハンドルバー構文が使用される場合。

ハンドルバー式は **{{expression}}** で囲まれます

```
   {{[profile.person.name.firstName}}
```

* **無効なセグメント定義**

```
No segment definition found for 988afe9f0-d4ae-42c8-a0be-8d90e66e151
```

+++

オファーの場合、特定のエラーが発生する場合があります。 詳細については、以下のセクションを展開してください。

+++ オファーに関連する特定のエラー

メールまたはプッシュメッセージ内のオファー統合に関連するエラーは、次のパターンになります。

```
Offer.<offerType>.[PlacementID].[ActivityID].<offer-attribute>
```

検証は、パーソナライゼーションエディターでのパーソナライゼーションコンテンツの検証中に実行されます。

<table> 
 <thead> 
  <tr> 
   <th> エラータイトル<br /> </th> 
   <th> 検証／解決 <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>ID が placementID でタイプが OfferPlacement のリソースが見つかりません <br/>
IDが activityID でタイプが OfferActivity のリソースが見つかりません<br/></td> 
   <td>ActivityID または PlacementID、あるいはその両方が使用可能かどうかを確認します</td> 
  </tr> 
   <tr> 
   <td>リソースを検証できませんでした。</td> 
   <td>プレースメントの componentType は、offerType オファーと一致する必要があります</td> 
  </tr> 
   <tr> 
   <td>オファー offerId にパブリック URL が存在しません。</td> 
   <td>画像オファー（決定とプレースメントのペアに関連付けられたすべてのパーソナライズオファーおよびフォールバック）には、パブリック URL を入力する必要があります（deliveryURL を空にすることはできません）。</td> 
  </tr> 
  <tr> 
   <td>決定にプロファイル以外の属性が含まれています。</td> 
   <td>オファーモデルの使用には、プロファイル属性のみを含める必要があります。</td> 
  </tr> 
  <tr> 
   <td>決定の使用状況の取得中にエラーが発生しました。</td> 
   <td>このエラーは、API がオファーモデルを取得しようとしているときに発生する可能性があります。</td> 
  </tr>
  <tr> 
   <td>オファー属性 offer-attribute が無効です。</td> 
   <td>オファー drp で参照されている offer-attribute が有効かどうかを確認します。有効な属性は次のとおりです。<br/>
画像：deliveryURL, linkURL<br/>
テキスト：content<br/>
HTML：content<br/></td> 
  </tr> 
 </tbody> 
</table>

+++
