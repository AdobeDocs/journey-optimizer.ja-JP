---
solution: Journey Optimizer
product: journey optimizer
title: 顧客管理キー
description: Adobe Journey Optimizer の顧客キーを設定および管理する方法について説明します。
feature: Privacy, Monitoring
role: Developer, User, Admin, Leader
level: Intermediate
exl-id: f0985d1f-0bcf-452f-bd46-dfeca0424f01
TQID: https://experienceleague.adobe.com/yCl5CISD1-Xx6gfcK2sWdFWAeE0LicO-3r3YndB2cVQ
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
subfeature_v2:
  - id: a9cf78bf-e9e4-4836-85a5-b6b3cf93bf56
  - id: f365ec33-2b99-4b7f-b4ee-c743dd7f615f
  - id: c8d5f2ce-ba44-43e9-a2bf-94a3d7d85ec3
source-git-commit: 4e89993a998268ae2810c949d0669bf6dc458dd6
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 89%

---

# 顧客管理キーの設定と管理 {#cmk}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;お客様管理キー（CMK）を設定および管理して、お客様自身のキーでAdobe Journey Optimizer データを暗号化し、転送中および保存中にデータを保護しておくことができます。

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>[!DNL Customer Managed Keys] 機能は、現在、[Healthcare Shield またはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html?lang=ja){target="_blank"}アドオン製品を購入した組織でのみ利用できます。

Adobe Journey Optimizer、[Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html){target="_blank"} およびプライバシーとセキュリティシールドを使用すると、お客様は Azure 顧客管理キー（CMK）を活用してデータに適用できるようになります。

Journey Optimizer の設定プロセスには、Adobe Experience Platform と Customer Journey Analytics（CJA）の両方のテクノロジーを活用する、次の 2 つの部分が含まれます。

* [Adobe Experience Platform の顧客管理キー](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=ja){target="_blank"}ドキュメントに記載されている手順に従います。
* [Customer Journey Analytics の顧客管理キー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/cmk.html?lang=ja){target="_blank"}ドキュメントに記載されている手順に従います。

  Customer Journey Analytics（CJA）の特定のコンポーネントがバックグラウンドで使用されるので、CJA を購入していない場合でも、この設定プロセスを完了する必要があります。

設定プロセスを実行するには、[Adobe Experience Platform の顧客管理キー](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=ja){target="_blank"}ドキュメントの詳細手順を順を追って参照してください。

Adobe Experience Platform と顧客管理キーはどちらも、転送中および保存中のデータを暗号化することでデータのセキュリティを確保します。 顧客管理キーを使用するかどうかに関係なく、データは引き続き保護されます。

Adobe Experience Platform でのデータ暗号化について詳しくは、データ暗号化に関する[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=ja){target="_blank"}を参照してください。
