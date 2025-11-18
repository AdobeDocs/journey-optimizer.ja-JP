---
title: テンプレートのパーソナライゼーションの例
description: Journey Optimizer パーソナライゼーションの例
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 832b0bfa-ec74-4b1d-ad85-d4e4ea2f8863
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# 医療保険処方箋のメール {#plan-prescription}

プロファイルには医療保険が含まれ、各保険には処方箋が含まれます。処方箋には、「準備完了」、「リコール」、「受け取り済み」など、様々な状態があります。

このユースケースでは、受け取りの準備が整っている処方箋やリコールされた処方箋をすべて含めて、各プロファイルに 1 通のメールを送信します。このユースケースの実装に使用する構文について詳しくは、以下の各タブをクリックしてください。

>[!BEGINTABS]

>[!TAB レンダリングされたメッセージ]

<p>こんにちは、John Doe 様、</p>
<p>受け取りの準備が整っている処方箋やリコールされた処方箋は次のとおりです。</p>

**医療保険 A**

<ul>

<li>
      <strong>処方箋 ID：</strong> pres1<br>
      <strong>名前：</strong> Medication A<br>
      <strong>状態：</strong> 準備完了
   </li>

<li>
      <strong>処方箋 ID：</strong> pres2<br>
      <strong>名前：</strong> Medication B<br>
      <strong>状態：</strong> リコール
   </li>

</ul>

**医療保険 B**

<ul>

<li>
      <strong> 処方箋 ID：</strong> pres4<br>
      <strong>名前：</strong> Medication D<br>
      <strong>状態：</strong> 準備完了
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
