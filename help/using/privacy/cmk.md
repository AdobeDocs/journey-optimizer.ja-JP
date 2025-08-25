---
solution: Journey Optimizer
product: journey optimizer
title: 顧客管理キー
description: Adobe Journey Optimizer の顧客キーを設定および管理する方法について説明します。
feature: Privacy, Monitoring
role: Developer, User, Admin, Leader
level: Intermediate
exl-id: f0985d1f-0bcf-452f-bd46-dfeca0424f01
source-git-commit: f9e1ae68fcfb9ecc12e0b80a067ca29186fc01f7
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# 顧客管理キーの設定と管理 {#cmk}

>[!AVAILABILITY]
>
>[!DNL Customer Managed Keys] 機能は、現在、[Healthcare Shield またはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html?lang=ja){target="_blank"}アドオン製品を購入した組織でのみ利用できます。

Adobe Journey Optimizer、[Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html){target="_blank"} およびプライバシーとセキュリティシールドを使用すると、お客様は Azure 顧客管理キー（CMK）を活用してデータに適用できるようになります。

Journey Optimizer の設定プロセスには、Adobe Experience Platform と Customer Journey Analytics（CJA）の両方のテクノロジーを活用する、次の 2 つの部分が含まれます。

* [Adobe Experience Platform の顧客管理キー](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=ja){target="_blank"}ドキュメントに記載されている手順に従います。
* [Customer Journey Analytics の顧客管理キー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/cmk.html?lang=ja){target="_blank"}ドキュメントに記載されている手順に従います。

  Customer Journey Analytics（CJA）の特定のコンポーネントがバックグラウンドで使用されるので、CJA を購入していない場合でも、この設定プロセスを完了する必要があります。

設定プロセスを実行するには、[Adobe Experience Platform の顧客管理キー](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=ja){target="_blank"}ドキュメントの詳細手順を順を追って参照してください。

Adobe Experience Platform と顧客管理キーはどちらも、転送中および保存中のデータを暗号化することでデータのセキュリティを確保します。顧客管理キーを使用するかどうかに関係なく、データは引き続き保護されます。

Adobe Experience Platform でのデータ暗号化について詳しくは、データ暗号化に関する[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=ja){target="_blank"}を参照してください。
