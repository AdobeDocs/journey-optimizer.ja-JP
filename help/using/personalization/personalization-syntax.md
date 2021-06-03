---
title: パーソナライゼーション構文
description: パーソナライゼーション構文の使用方法を説明します。
source-git-commit: 5b7f3f58e7376b45993b6a2edc6e96f824fa2f44
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 69%

---


# パーソナライゼーション構文 {#personalization-syntax}

![](../assets/do-not-localize/badge.png)

[!DNL Journey Optimizer]でのパーソナライゼーションは、Handlebarsと呼ばれるテンプレート構文に基づいています。
Handlebars構文の詳細は、[HandlebarsJSのドキュメント](https://handlebarsjs.com/)を参照してください。

テンプレートと入力オブジェクトを使用して、HTMLやその他のテキスト形式を生成します。Handlebars テンプレートは、埋め込まれた Handlebars 式を含む標準のテキストのように見えます。

簡単な式のサンプル：

```
{{profile.person.name}}
```

各パラメーターの意味は次のとおりです。

* **profile** は、名前空間です。
* **person.name** は、属性で構成されるトークンです。属性構造は、Adobe Experience PlatformXDM スキーマで定義されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja).

## 構文の一般的なルール

識別子には、次を除く任意の Unicode 文字を使用できます。

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

構文では大文字と小文字が区別されます。

**true**, **false**, **null** and **undefined**&#x200B;という語は、パス式ーの最初の部分でのみ使用できます。

Handlebars では、{{式}} から返される値は、**HTML-escaped**&#x200B;です。 式に`&`が含まれる場合、返されたHTMLエスケープ出力は`&amp;`として生成されます。 Handlebars の値をエスケープしない場合は、「triple-stash」を使用します。

## プロファイル

この名前空間を使用すると、[Adobe Experience Platform Data Model (XDM)ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)で説明されているプロファイルスキーマで定義されているすべての属性を参照できます。

属性は、[!DNL Journey Optimizer]パーソナライゼーションブロックで参照する前に、スキーマで定義する必要があります。

>[!NOTE]
>
>[この節](functions/helpers.md#if-function)では、条件でプロファイル属性を活用する方法を説明します。

**サンプルリファレンス：**

```
{{profile.person.name.fullName}}
{{profile.person.name.firstName}}
{{profile.person.gender}}
{{profile.personalEmail.address}}
{{profile.mobilePhone.number}}
{{profile.homeAddress.city}}
{{profile.faxPhone.number}}
```

## セグメント{#perso-segments}

[この節](functions/helpers.md#if-function)では、条件でプロファイル属性を活用する方法を説明します。

>[!NOTE]
>セグメント化とセグメント化サービスについて詳しくは、[この節](../segment/about-segments.md)を参照してください。


## オファー

この名前空間では、既存のオファー決定を参照できます。
オファーを参照するには、オファーを定義する別の情報を使用してパスを宣言する必要があります。

このパスは次の構造を持ちます。

```
offers.Type.[Placement Id].[Activity Id].Attribute
```

各パラメーターの意味は次のとおりです。

* `offers` オファー名前空間に属するパス式を識別します。
* `Type`  は、オファー表示域のタイプを決定します。次の値を指定できます。`image`、`html`および`text`
* `Placement Id` とは配置 `Activity Id` とアクティビティの識別子です。
* `Attributes` は、オファータイプに依存するオファー固有の属性です。例：`deliveryUrl`（画像の場合）

Decisions APIとオファー表示域について詳しくは、[このページ](../../using/offers/api-reference/decisions-api/deliver-offers.md)を参照してください。

すべての参照は、[このページ](personalization-validation.md)で説明されている検証メカニズムを使用して、オファースキーマに対して検証されます。

**サンプルリファレンス：**

* 画像がホストされる場所 :

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

* 画像をクリックしたときのターゲット URL :

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

* 意思決定エンジンからのオファーのテキストコンテンツ：

   `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

* 決定エンジンからのオファー HTMLコンテンツ：

   `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`


## ヘルパー{#helpers-all}

ハンドルバーヘルパーは、パラメーターの後に続く単純な識別子です。
各パラメータは、Handlebars 式です。 これらのヘルパーは、テンプレート内の任意のコンテキストからアクセスできます。

これらのブロックヘルパーは、ヘルパー名の前に # を付けることで識別され、/ で同じ名前を閉じる必要があります。ブロックとは、ブロックの開き({{# }})と閉じ({{/}})を持つ式です。


>[!NOTE]
>
>ヘルパー関数について詳しくは、[この節](functions/helpers.md)を参照してください。


## リテラル型

[!DNL Adobe Journey Optimizer] では、次のリテラル型をサポートしています。

| リテラル | 定義 |
| ------- | ---------- |
| 文字列 | 1 つ以上の文字で構成され、二重引用符で囲まれたデータタイプです。<br>例: `"prospect"`, `"jobs"`, `"articles"` |
| ブール | true か false のいずれかであるデータタイプです。 |
| 整数 | 整数を表すデータタイプです。正、負、ゼロのいずれかです。<br>例: `-201`, `0`, `412` |
| 配列 | 他のリテラル値のグループとして構成されるデータ型です。複数の値を区切る場合は、角括弧で囲んでグループ化し、カンマで区切ります。<br> **注意**：配列内の項目のプロパティに直接アクセスすることはできません。<br> 例: `[1, 4, 7]`, `["US", "FR"]` |

>[!CAUTION]
>
>**xEvent**&#x200B;変数は、パーソナライズ式では使用できません。 xEvent を参照すると、検証エラーが発生します。
