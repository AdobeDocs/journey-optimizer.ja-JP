---
title: テンプレートPersonalizationの例
description: Journey Optimizer Personalizationの例
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
source-git-commit: f1d6c293fb8b22085911ab45c18f944a63b9655b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---


# 医療保険処方箋のメール {#plan-prescription}

1 つのプロファイルには医療プランが含まれ、各プランには処方箋が含まれる。 処方箋には、「準備完了」、「思い出す」、「拾う」など、様々な状態がある。

このユースケースでは、受け取りの準備ができているかリコールされるすべての処方箋を含め、1 通のメールを各プロファイルに送信します。 このユースケースの実装に使用する構文について詳しくは、以下の各タブをクリックしてください。

>[!BEGINTABS]

>[!TAB  レンダリングされたメッセージ ]

<p>こんにちは、John Doe 様、</p>
<p>回収の準備ができている、または回収された処方箋は次のとおりです。</p>

**健康保険 A**

<ul>

<li>
      <strong> 処方箋 ID:</strong> pres1<br>
      <strong> 名前：</strong> Medication A<br>
      <strong> 状態：</strong> 準備完了
   </li>

<li>
      <strong> 処方箋 ID:</strong> pres2<br>
      <strong> 名前：</strong> Medication B<br>
      <strong> 状態：</strong> リコール
   </li>

</ul>

**健康保険 B**

<ul>

<li>
      <strong> 処方箋 ID:</strong> pres4<br>
      <strong> 名前：</strong> Medication D<br>
      <strong> 状態：</strong> 準備完了
   </li>

</ul>

>[!TAB HTMLテンプレート ]

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

>[!TAB  プロファイルデータ ]

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
