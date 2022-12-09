---
solution: Journey Optimizer
product: journey optimizer
title: パーソナル化構文
description: パーソナル化構文を使用する方法について説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 5a562066-ece0-4a78-92a7-52bf3c3b2eea
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# パーソナル化構文 {#personalization-syntax}

の [!DNL Journey Optimizer] パーソナル化は、Handlebars と呼ばれるテンプレート構文に基づいています。Handlebars シンタックスの詳細については、handlebarsjs のドキュメント ](https://handlebarsjs.com/) を [ 参照してください。

テンプレートと入力オブジェクトを使用して、HTML やその他のテキストフォーマットを生成します。 Handlebars テンプレートは、埋め込み Handlebars 式が設定された通常のテキストに似ています。

単純な式のサンプル:

`{{profile.person.name}}`

どこ：

* `profile` 名前空間です。
* `person.name` 属性によって構成されるトークンです。 属性構造は、Adobe 体験プラットフォームの XDM スキーマで定義されています。 [](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)詳しくは、「target = &quot;_blank&quot;}」を参照してください。

## シンタックスの一般的な規則 {#general-rules}

識別子には、次のような unicode 文字を使用できます。

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

このシンタックスでは、大文字と小文字が区別されます。

True **、** false **、** null **および** undefined **の語** は、path 式の最初の部分でのみ使用できます。

Handlebars では、によって返される値は HTML エスケープ **さ** れて {{expression}} います。式に値が含まれ `&` ている場合は、返される HTML によって生成される出力は、として `&amp;` 生成されます。 値をエスケープする必要がない場合は、Handlebars を使用してください。

Literal 関数の引数については、テンプレート言語パーサーは、1つのエスケープされていないバックスラッシュ ( `\` ) 記号をサポートしません。 この文字は、additionnal 円記号 ( `\` ) 記号でエスケープする必要があります。 一

`{%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}`

## 薄型

この名前空間を使用すると、Adobe エクスペリエンス Platform データモデル (XDM) マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) で説明 [ されているすべての属性を参照できるようになります (「target = &quot;_blank&quot;})。

属性は、個人用設定ブロック内で [!DNL Journey Optimizer] 参照される前に、スキーマで定義する必要があります。

>[!NOTE]
>
>このセクション ](functions/helpers.md#if-function) で [ は、条件でプロファイル属性を活用する方法について説明します。

**サンプルリファレンス:**

`{{profile.person.name.fullName}}`

`{{profile.person.name.firstName}}`

`{{profile.person.gender}}`

`{{profile.personalEmail.address}}`

`{{profile.mobilePhone.number}}`

`{{profile.homeAddress.city}}`

`{{profile.faxPhone.number}}`

## 層{#perso-segments}

このセクション ](functions/helpers.md#if-function) で [ は、条件でプロファイル属性を活用する方法について説明します。

>[!NOTE]
>セグメンテーションとセグメンテーションのサービスについて詳しくは、次の項 ](../segment/about-segments.md) を [ 参照してください。

## 一元化 {#offers-syntax}

この名前空間を使用すると、既存のオファーの決定を参照できます。オファーを参照するには、オファーを定義するさまざまな情報を使用してパスを宣言する必要があります。

このパスの構造は次のとおりです。

`offers.Type.[Placement Id].[Activity Id].Attribute`

どこ：

* `offers` オファー名前空間に属するパス式を指定します。
* `Type`  オファー表示の種類を指定します。 指定可能な値は次のとおりです。 `image` `html``text`
* `Placement Id``Activity Id`配置とアクティビティの識別子
* `Attributes` には、オファーの種類に応じた具体的な属性が用意されています。 例: `deliveryUrl` イメージの場合

決定 API および「オファー」の表示について詳しくは、このページを [ 参照してください。](../offers/api-reference/offer-delivery-api/decisioning-api.md)

すべての参照が、このページで [ 説明されている検証メカニズムを使用してスキーマと照らして検証されます。](personalization-validation.md)

**サンプルリファレンス:**

* イメージがホストされている場所。

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

* イメージをクリックしたときのターゲット URL:

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

* Decisioning エンジンによって提供されるオファーのテキストコンテンツ:

   `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

* Decisioning エンジンによって提供される HTML コンテンツ:

   `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`


## ヘルパー{#helpers-all}

Handlebars helper は、パラメーターが後に続く単純な識別子です。各パラメーターは Handlebars 式です。 このようなヘルパーには、テンプレート内の任意のコンテキストからアクセスできます。

これらのブロックヘルパーは、ヘルパー名の前に # 1 が付いた番号で識別されます。ブロックは、ブロックの開 ( {{# }}) and closing ({{/}} ) を持つ式です。


>[!NOTE]
>
>ヘルパー関数については、このセクション ](functions/helpers.md) で [ 詳しく説明しています。

## リテラル型 {#literal-types}

[!DNL Adobe Journey Optimizer] では、以下のリテラルタイプがサポートされています。

| 郵便 | 精細 |
| ------- | ---------- |
| 値 | 二重引用符で囲まれた文字で構成されるデータ型です。 <br>例: `"prospect"` 、 `"jobs"` 、 `"articles"` |
| 示す | True または false のデータ型を指定します。 |
| 整数 | 整数を表すデータ型。 正数、負数、ゼロのいずれかを指定できます。 <br>例: `-201` 、 `0` 、 `412` |
| 一連 | 他のリテラル値のグループとして &#39;8d&#39;5c 成されるデータ型。 グループとカンマを使用して異なる値間を区切るために、角カッコを使用します。 <br> **注意:** 配列内のアイテムのプロパティに直接アクセスすることはできません。 <br> 例: `[1, 4, 7]` 、 `["US", "FR"]` |

>[!CAUTION]
>
>XEvent **変数は、パーソナル化条件式では使用** できません。XEvent への参照によって検証エラーが発生します。

## URL の個人用設定{#perso-urls}

パーソナライズされた Url では、プロファイル属性に応じて、web サイトの特定のページ、またはパーソナライズされたマイクロサイトが宛先になります。 Adobe 旅のオプティマイザーでは、メッセージコンテンツ内の Url にパーソナライズ機能を追加することができます。 URL パーソナル化は、テキストとイメージに適用できます。また、プロファイルデータまたは文脈データを使用することもできます。

旅のオプティマイザーを使用すると、パーソナライズフィールドを追加することで、メッセージ内の1つまたは複数の Url を個人用に設定することができます。 URL をカスタマイズするには、次の手順に従います。

1. メッセージコンテンツ内にリンクを作成します。 [詳細情報](../email/message-tracking.md#insert-links)
1. パーソナル化アイコンから属性を選択します。 パーソナル化アイコンは、これらの種類のリンク **(外部リンク** 、Unsubscription link **** 、 **オプトアウト)** でのみ使用できます。

![](assets/perso-url.png)

>[!NOTE]
>
>式エディターでは、個人用の URL を編集すると、セキュリティ上の理由から、ヘルパー関数およびセグメントメンバーシップが無効化されます。

**パーソナライズされた Url のサンプル**

* `https://www.adobe.com/users/{{profile.person.name.lastName}}`
* `https://www.adobe.com/users?uid={{profile.person.name.firstName}}`
* `https://www.adobe.com/usera?uid={{context.journey.technicalProperties.journeyUID}}`
* `https://www.adobe.com/users?uid={{profile.person.crmid}}&token={{context.token}}`

>[!CAUTION]
>
>Url 内で使用されるパーソナル化トークンでは、スペースはサポートされていません。
