---
title: パーソナライゼーションの検証
description: パーソナライゼーションの検証とトラブルシューティングの方法の詳細
source-git-commit: 7e20bef085d0fa6983f9ebd84f8cbc3bee2f4542
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---


# パーソナライゼーションの検証 {#personalization-validation}

![](../assets/do-not-localize/badge.png)

## 検証メカニズム

式エディター画面で、「**検証**」ボタンを使用すると、パーソナライゼーション構文を検証できます。

>[!NOTE]
> **追加**&#x200B;をクリックしてエディターウィンドウを閉じると、検証は自動的に実行されます。


![](assets/perso_validation1.png)

>[!IMPORTANT]
> パーソナライゼーション構文が無効な場合、式エディターウィンドウを閉じることはできません。


## 一般的なエラー

* **パス「XYZ」が見つかりません**

スキーマで定義されていないフィールドを参照しようとしたとき。

この場合、**firstName1** は、プロファイルスキーマの属性として定義されていません。

```
{{profile.person.name.firstName1}}
```

* **変数「XYZ」のタイプが一致しません。 予想される配列です。 文字列が見つかりました。**

配列ではなく文字列を反復処理する場合：

この場合、**製品** は配列ではありません。

```
{{each profile.person.name.firstName as |product|}}
 {{product.productName}}
{{/each}}
```

* **ハンドルバー構文が無効です。 見つかりました`‘[XYZ}}’`**

無効なハンドルバー構文が使用される場合。

ハンドルバー式は **{{expression}}** で囲まれます

```
   {{[profile.person.name.firstName}}
```

* **無効なセグメント定義**

```
No segment definition found for 988afe9f0-d4ae-42c8-a0be-8d90e66e151
```

### オファーに関連する特定のエラー

E メールまたはプッシュメッセージ内のオファー統合に関連するエラーは、次のパターンになります。

```
Offer.<offerType>.[PlacementID].[ActivityID].<offer-attribute>
```

検証は、メッセージの公開中、または式エディターでのパーソナライゼーションコンテンツの検証中に実行されます。

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
   <td>配置の componentType は、offerType オファーと一致する必要があります</td> 
  </tr> 
   <tr> 
   <td>パブリック URL はオファー offerId に存在しません。</td> 
   <td>画像オファー（決定と配置のペアに関連付けられたすべてのパーソナライズおよびフォールバック）には、パブリック URL を入力する必要があります（deliveryURL は空にできません）。</td> 
  </tr> 
  <tr> 
   <td>決定（旧称オファーアクティビティ）には、プロファイル以外の属性が含まれています。</td> 
   <td>オファーモデルの使用法には、プロファイル属性のみを含める必要があります。</td> 
  </tr> 
  <tr> 
   <td>決定の使用法の取得中にエラーが発生しました。</td> 
   <td>このエラーは、API がオファーモデルを取得しようとしているときに発生する可能性があります。</td> 
  </tr>
  <tr> 
   <td>オファー属性 offer-attribute が無効です。</td> 
   <td>offer drp で参照されている offer-attribute が有効かどうかを確認します。 有効な属性は次のとおりです。<br/>
画像：deliveryURL, linkURL<br/>
テキスト：content<br/>
HTML：content<br/></td> 
  </tr> 
 </tbody> 
</table>

