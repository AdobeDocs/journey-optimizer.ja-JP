---
solution: Journey Optimizer
product: journey optimizer
title: パーソナル化の検証
description: パーソナル化の検証とそのトラブルシューティング方法について説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 7abeec5e-743f-48fb-a4a6-056665e8bfda
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# パーソナル化の検証 {#personalization-validation}

## 検証機構 {#validation-mechanisms}

**式エディター** 画面の検証 **ボタンを使用** して、パーソナル化の構文を確認します。

>[!NOTE]
> 「追加 **」ボタンをクリックし** てエディターウィンドウを閉じると、検証が自動的に実行されます。

![](assets/perso_validation1.png)

>[!IMPORTANT]
> パーソナル化構文が無効な場合は、エクスプレッションエディターウィンドウを閉じることはできません。

## 一般的なエラー {#common-errors}

* **パス &quot;XYZ&quot; は見つかりませんでした。**

スキーマで定義されていないフィールドを参照しようとすると発生します。

この場合 **、firstName1** は、プロファイルスキーマの属性として定義されていません。

```
{{profile.person.name.firstName1}}
```

* **変数 &quot;XYZ&quot; のタイプが一致しません。 配列が必要です。 ストリングが見つかりました。**

配列ではなく、文字列に対して反復処理しようとすると、次のようになります。

この場合 **、製品** は配列ではありません。

```
{{each profile.person.name.firstName as |product|}}
 {{product.productName}}
{{/each}}
```

* **Handlebars シンタックスが無効です。 見つかった`‘[XYZ}}’`**

無効な handlebars シンタックスが使用されている場合。

Handlebars 式は、 **{{expression}}**

```
   {{[profile.person.name.firstName}}
```

* **無効なセグメント定義**

```
No segment definition found for 988afe9f0-d4ae-42c8-a0be-8d90e66e151
```

## オファーに関する具体的なエラー {#specific-errors}

電子メールまたは Push メッセージにおける統合に関するエラーは、次のようなパターンになります。

```
Offer.<offerType>.[PlacementID].[ActivityID].<offer-attribute>
```

検証は、エクスプレッションエディターで、パーソナライズされたコンテンツの検証中に実行されます。

<table> 
 <thead> 
  <tr> 
   <th> エラータイトル<br /> </th> 
   <th> 検証/解決 <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Id が placementID および type OfferPlacement が <br/> 指定されていないリソース
Id activityID およびタイプ OfferActivity が指定されたリソースは見つかりません<br/></td> 
   <td>ActivityID と PlacementID が使用可能かどうかを確認します。</td> 
  </tr> 
   <tr> 
   <td>リソースを検証できませんでした。</td> 
   <td>配置されている componentType は offerType offer 版と同じである必要があります</td> 
  </tr> 
   <tr> 
   <td>パブリック URL は、オファーのパッケージに含まれていません。</td> 
   <td>イメージによって提供される (「意思決定」と「配置」ペアに関連付けられたすべての「個人用」と「フォールバック」) には、パブリック URL が設定されていること</td> 
  </tr> 
  <tr> 
   <td>この決定には、プロファイル以外の属性が含まれています。</td> 
   <td>モデルの用途には、プロファイル属性のみが含まれている必要があります。</td> 
  </tr> 
  <tr> 
   <td>意志決定の利用状況を取得中にエラーが発生しました。</td> 
   <td>このエラーは、API がオファーモデルを取得しようとしたときに発生する可能性があります。</td> 
  </tr>
  <tr> 
   <td>Offer 属性の offer 属性は無効です。</td> 
   <td>Drp の提供が有効になっているかどうかを確認してください。 有効な属性は以下のとおりです。 <br/>
イメージ: deliveryURL、linkURL <br/>
テキスト: コンテンツ <br/>
HTML: コンテンツ<br/></td> 
  </tr> 
 </tbody> 
</table>
