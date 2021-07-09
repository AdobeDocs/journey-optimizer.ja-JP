---
title: プライバシー [!DNL Journey Optimizer]  の場合
description: プライバシーの管理方法について学ぶ
topic: プライバシー
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# [!DNL Journey Optimizer] によるプライバシー管理{#privacy}

[!DNL Journey Optimizer] は、個人情報や機密データを含む膨大な量のデータを処理するための強力なツールです。より良い顧客体験を提供するためには、顧客の個人データを収集し、保存する必要があります。このデータを使用する場合、顧客のプライバシーを理解し、尊重することが重要です。新しい法規制や組織の規制により、ユーザーは要求に応じて、データストアから個人データにアクセスしたり、個人データを削除したりする権利が与えられます。

* **個人データ**&#x200B;は、生存する個人を直接または間接的に識別できる情報です。
* **個人の機密データ**&#x200B;は、個人の人種、政治観、宗教的信念、犯罪歴、遺伝情報、健康データ、性的嗜好、生体認証情報、および労働組合の組合員に関する情報です。

主な法律では、データを管理する様々なエンティティを次のように表します。

* **データ管理者**&#x200B;は、個人データの収集、使用、共有の方法と目的を決定する権限を有する関係者です。
* **データ処理者**&#x200B;は、データ管理者の指示に従って個人データを収集、使用、または共有する個人または関係者です。
* **データ主体**&#x200B;は、個人データが収集、使用、共有され、その個人データを参照して直接または間接的に識別できる、生存する個人のことです。

「データ管理者」とは個人データを収集し共有する企業のことで、クライアントは「データ主体」にあたります。Adobe Experience Cloud は、「データ処理者」としてお客様の指示に従って個人データを処理します。データ管理者は、データ主体との関係を取り扱う責任を負います。

## 一般的な推奨事項 {#general-recommendations}

個人データや機密データは慎重に管理する必要があります。次の一般原則に従います。

* 個人情報は常に、責任を持って倫理的に使用する。

* 迷惑メール（「スパム」）を送信しない。Adobeは、顧客の生涯価値とロイヤリティを促進するうえで許可型マーケティングの原則を強く信じているので、未承諾メッセージの送信に[!DNL Adobe Journey Optimizer]を使用することは厳しく禁止しています。

[!DNL Journey Optimizer] では、様々な事前定義済み製品やカスタム製品のプロファイルを使用して、ユーザーに割り当てられた権限を管理できます。これにより、会社内で様々なタイプのデータにアクセス、変更、書き出しできる人物を管理できます。[このページ](administration/permissions.md)でユーザー権限を管理する方法を説明します。

[!DNL Journey Optimizer]また、 では、リンクの開封やクリックを通して送信されたメッセージや、受信者の行動を追跡することもできます。[このページ](message-tracking.md)でのトラッキング管理について詳しく説明します。

## プライバシーの管理 {#privacy-management}

プライバシー管理とは、プライバシー規制の遵守に役立つすべてのプロセスとツールを指します。

プライバシーを正しく処理し、個人データを管理するには、事業をおこなう地域に適用される法律を遵守してください。次の規則が適用されます。

* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)（ヨーロッパの一般データ保護規則）
* [DPA](https://www.gov.uk/data-protection)（英国での GDPR）
* [プライバシーと電子通信に関する欧州指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM 法](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)（商用 E メールのルールと要件を設定する米国の法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)（カリフォルニア州消費者プライバシー法）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)（タイ個人データ保護法）

[!DNL Journey Optimizer] は、Adobe Experience Platform でおこなわれたデータセットの変更のほとんどを継承しています。

それにより、プライバシーリクエスト（アクセス権および忘れられる権利）は Experience Platform で管理されます。[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja){target=&quot;_blank&quot;}を使用してリクエストを送信し、[プライバシーリクエスト](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja#request-builder){target=&quot;_blank&quot;}を作成する際に、製品リストから&#x200B;**Profile**&#x200B;と&#x200B;**AEP Data Lake**&#x200B;を選択する必要があります。 <!--https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).-->

>[!NOTE]
>
>[同意管理](../../help/using/consent.md)は Journey Optimizer 内で直接取り扱います。

## Adobe Experience Cloud のプライバシー {#experience-cloud-privacy}

[!DNL Journey Optimizer] は、Adobe Experience Cloudソリューションの一部です。プライバシーの取り扱いは、Adobe Experience Cloud の原則に従います。Adobe Experience Cloudのプライバシーについて詳しくは、[このページ](https://www.adobe.com/jp/privacy/experience-cloud.html)を参照してください。

Adobe Experience Cloud ソリューションを使用する会社は、どの情報を収集してAdobe Experience Cloud アカウントに送信するかを選択します。収集される情報のタイプの例としては、web 閲覧アクティビティ、IP アドレス、モバイルデバイスからの位置情報、キャンペーン成功率、購入品目、買い物かごに入れた品目などがあります。詳しくは、[アドビのプライバシーポリシー](https://www.adobe.com/jp/privacy/policy.html)をご覧ください。

アドビから、次の内容を説明するプライバシーポリシーをお客様に提供するように求められます。

* Adobe Experience Cloud に関連するプライバシー方針
* Adobe Experience Cloud に関連して、ユーザーが情報の収集や使用に関する環境設定をおこなう方法

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer]ユーザーは、すべてのAdobe製品に関して、アプリやWebサイトを通じて収集した共有情報をオプトアウトできます。 詳しくは、[Adobe Experience Cloud の使用状況に関する FAQ](https://www.adobe.com/jp/privacy/experience-cloud-usage-info-faq.html) をご覧ください。

<!--Because Journey Optimizer integrates with Adobe Experience Platform, where audiences are transferred from one system to another, you need to pay extra care to personal data protection.-->
