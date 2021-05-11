---
title: パーソナライズ追加オファー
description: メッセージにパーソナライズされたオファーを追加する方法を説明します。
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 3%

---

# パーソナライズ追加オファー{#deliver-personalized-offers}

![](assets/do-not-localize/badge.png)

## Decision Managementについて{#about-offer-decisioning}

[!DNL Journey Optimizer]を使うと、オファーの判断エンジンを利用して顧客に提供する最適なオファーを選ぶための決定事項(オファーアクティビティ)を電子メールに挿入できます。

例えば、受信者の忠誠度に応じて変わる特別割引オファーを電子メールに表示する決定を追加できます。

オファーの作成と管理の方法について詳しくは、[このセクション](offers/get-started/starting-offer-decisioning.md)を参照してください。

## 電子メールに決定を挿入{#insert-offers}

電子メールメッセージに決定を挿入するには、次の手順に従います。

1. 電子メールを作成し、電子メールデザイナーを開いてその内容を設定します。

1. 追加&#x200B;**[!UICONTROL オファーの判断]**&#x200B;コンテンツコンポーネント（[コンテンツコンポーネントの使用](content-components.md)を参照）。

   ![](assets/deliver-offer-component.png)

1. **[!UICONTROL オファー決定]**&#x200B;タブがコンポーネントに追加されます。 **[!UICONTROL パーソナライゼーション —オファー決定]**&#x200B;追加をクリックして、オファーアクティビティを追加します。

   ![](assets/deliver-offer-tab.png)

1. 表示するオファーに対応する配置を選択します。

   プレースメントは、オファーの表示に使用するコンテナです。 この例では、「トップイメージの電子メール送信」を使用します。 この配置は、オファーの上部に配置された画像タイプオファーを表示するために、メッセージライブラリで作成されました。

1. コンテンツコンポーネントで使用するオファーアクティビティを選択し、追加&#x200B;****&#x200B;をクリックします。

   >[!NOTE]
   >
   >選択した配置と互換性のある決定のみがリストに表示されます。 この例では、「電子メールの最上位オファー」の配置に一致する画像アクティビティは1つだけです。

   ![](assets/deliver-offer-placement.png)

1. これで、オファーアクティビティがコンポーネントに追加されます。 **[!UICONTROL オファー]**&#x200B;セクションまたはコンテンツコンポーネントの矢印を使用して、決定の一部となる異なるオファーをプレビューできます。

   ![](assets/deliver-offer-preview.png)
