---
title: テンプレートのパーソナライゼーションの例
description: Journey Optimizer パーソナライゼーションの例
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 832b0bfa-ec74-4b1d-ad85-d4e4ea2f8863
TQID: https://experienceleague.adobe.com/fZtkkz9pvdZ3G7ojmHlNhasxawVbXmBHX-uznq6hseY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fda7be7c-b81e-42c0-95a9-616e5b893c03
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2:
  - id: cb09dcb7-3367-4b63-b02c-8a1356eb876e
  - id: a757b957-83f3-4a4d-9775-a93854f84f77
source-git-commit: f552e98f370f96e9a99d2f1d604f840ac6069d65
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 21%

---

# 医療保険処方箋のメール {#plan-prescription}

>[!BEGINSHADEBOX]

**このページでは：**&#x200B;条件付きルールを使用してネストされたプロファイル配列を繰り返し処理するパーソナライゼーションの使用例に従って、受け取りや呼び出しの準備が整ったヘルスプランのメールリストの処方箋を作成します。

>[!ENDSHADEBOX]

プロファイルには医療保険が含まれ、各保険には処方箋が含まれます。 処方箋には、「準備完了」、「リコール」、「受け取り済み」など、様々な状態があります。

このユースケースでは、受け取りの準備が整っている処方箋やリコールされた処方箋をすべて含めて、各プロファイルに 1 通のメールを送信します。 このユースケースの実装に使用する構文について詳しくは、以下の各タブをクリックしてください。

>[!BEGINTABS]

>[!TAB レンダリングされたメッセージ]

<p>こんにちは、John Doe 様、</p>
<p>受け取りの準備が整っている処方箋やリコールされた処方箋は次のとおりです。</p>

**医療保険 A**

<ul>

<li>
      <strong>処方箋ID:</strong> pres1<br>
      <strong>名前：</strong>薬A<br>
      <strong>状態：</strong>準備完了
   </li>

<li>
      <strong>処方箋ID:</strong> pres2<br>
      <strong>名前：</strong>薬B<br>
      <strong>状態：</strong>のリコール
   </li>

</ul>

**医療保険 B**

<ul>

<li>
      <strong>処方箋ID:</strong> pres4<br>
      <strong>名前：</strong>薬D<br>
      <strong>状態：</strong>準備完了
   </li>

</ul>

>[!TAB HTML テンプレート]

```html
<p>Hi {{profile.person.firstName}} {{profile.person.lastName}},</p>
<p>Here are the prescriptions that are either ready for pick up or have been recalled:</p>
{{#each profile.plans as |plan|}}
<h3>{{plan.name}}</h3>
<ul>
   {{#each plan.prescriptions as |prescription|}}
   {%#if prescription.state = "ready" or prescription.state = "recall"%}
   <li>
      <strong>Prescription ID:</strong> {{prescription.prescription_id}}<br>
      <strong>Name:</strong> {{prescription.name}}<br>
      <strong>State:</strong> {{prescription.state}}
   </li>
   {%/if%}
   {{/each}}
</ul>
{{/each}}
```

>[!TAB プロファイルデータ]

```javascript
{
  "profile": {
    "person": {
      "firstName": "John",
      "lastName": "Doe"
    },
    "plans": [
      {
        "planId": "plan1",
        "name": "Health Plan A",
        "prescriptions": [
          {
            "prescription_id": "pres1",
            "name": "Medication A",
            "state": "ready"
          },
          {
            "prescription_id": "pres2",
            "name": "Medication B",
            "state": "recall"
          }
        ]
      },
      {
        "planId": "plan2",
        "name": "Health Plan B",
        "prescriptions": [
          {
            "prescription_id": "pres3",
            "name": "Medication C",
            "state": "picked up"
          },
          {
            "prescription_id": "pres4",
            "name": "Medication D",
            "state": "ready"
          }
        ]
      }
    ]
  }
}
```

>[!ENDTABS]

## クイックリファレンス {#quick-reference}

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

>[!BEGINTABS]

>[!TAB 概要]

**TL;DR**

このページでは、完全なパーソナライゼーションのユースケースを示します。ネストされたプロファイル配列（処方箋を含むヘルスプラン）を条件付きフィルタリングで繰り返し処理して、メールの「準備完了」または「想起」状態でのみ処方箋を表示します。

**インテント**

* パーソナライズされたヘルスプランのメールのレンダリングされた出力例を参照してください
* 条件付き配列の反復にネストされた`{{#each}}`および`{%#if%}` ブロックを使用して、HTML テンプレートについて説明します
* 必要なプロファイルデータ構造について説明します。各プランに`state`個のフィールドを含む`prescriptions`個の配列が含まれる`plans`配列

>[!TAB 用語集]

* **ネストされた反復**：他の`{{#each}}` ループ内の`{{#each}}` ループを使用して、プロファイルデータ内のマルチレベル配列構造（計画→処方など）をトラバースします。
* **処方状態**：この使用例では、各処方オブジェクトのライフサイクルステータスを示すフィールド。使用される値は、「準備完了」、「呼び出し」、「ピックアップ済み」です。 *（ユースケース固有）*
* **`{%#if%}`/`{%/if%}`**: メッセージテンプレート内で条件付きブロック構文を使用して、反復中に配列項目をフィルタリングします（二重巻き`{{#if}}` Handlebars構文とは異なります）。

>[!TAB 用語]

* **正規名：** ネストされた配列イテレーション – バリアント：ネストされたループ、ネストされた各、マルチレベルのイテレーション
* **混同しないでください：** `{{#each}}` / `{{/each}}` （Handlebars イテレーション構文、二重中括弧） ≠ `{%#if%}` / `{%/if%}` （条件付き構文、パーセント中括弧） – 両方がこのテンプレートで一緒に使用されます
* **混同しないでください：** 「準備完了」（処方箋を受け取り可能） ≠「リコール」（処方箋を回収しました） ≠「受け取り」（処方箋は既に収集されています。条件付きフィルターによる出力から除外されます）

>[!TAB FAQ]

**Q: メール出力にはどの処方箋の状態が含まれていますか？**

状態が「準備完了」または「呼び出し」の処方箋のみが表示されます。 状態「ピックアップ」の処方箋は、`{%#if prescription.state = "ready" or prescription.state = "recall"%}`条件フィルターによって除外されます。

**Q：この使用例に必要なプロファイルデータ構造は何ですか？**

`plans`配列を持つプロファイル。各プランオブジェクトには`prescriptions`配列が含まれます。 各処方箋オブジェクトには、`prescription_id`、`name`、`state`のフィールドが必要です。

**Q: テンプレートで計画と処方箋はどのように繰り返されますか？**

外側の`{{#each profile.plans as |plan|}}` ループは、各正常性プランに対して繰り返し実行されます。 その中で、`{{#each plan.prescriptions as |prescription|}}`は各プランの処方箋を繰り返し処理し、条件付きブロックフィルターは「準備完了」または「想起」の状態のみを返します。

>[!ENDTABS]

<!-- ai-section-version: 1 | source-hash: 4b68d597 -->
