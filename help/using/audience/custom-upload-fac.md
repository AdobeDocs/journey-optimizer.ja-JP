---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアップロード（CSV）と Federated Audience Composition
description: カスタムアップロード（CSV）および Federated Audience Composition オーディエンスを操作する際に、主要な情報とベストプラクティスについて説明します。
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
exl-id: d2365e3f-fbef-43c2-bf2a-0a868cb93015
source-git-commit: a98312d9ac5a457bfd6789bf79ad80a24d894a0b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 52%

---

# カスタムアップロード（CSV）と Federated Audience Composition {#csv-fac}

## カスタムアップロードと Federated Audience コンポジションについて {#about}

セグメントの定義とオーディエンスの構成に加えて、[!DNL Journey Optimizer] を使用すると、CSV ファイルから読み込んだり、データウェアハウスのデータを活用したりして、オーディエンスを生成およびターゲットにすることができます。

* **カスタムアップロード**：CSV ファイルを使用してオーディエンスを読み込みます。オーディエンスを読み込む方法については、Adobe Experience Platform の[セグメント化サービスに関するドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}を参照してください。

* **連合オーディエンス構成**：既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。[連合オーディエンス構成](https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home)に関するガイドを参照してください。

これらのオーディエンスをJourney Optimizerでターゲットにするか、Adobe Experience Platformでサポートされる任意の宛先に対してアクティブ化できます

➡️ [ ビデオでこれらの機能を確認する ](#video)

## 必読 {#must-read}

この節では、カスタムアップロード（CSV ファイル）および Federated Audience Composition オーディエンスを使用する際に留意すべき重要な情報を示します。

* **プレビューと配達確認のサポート：**&#x200B;現在、CSV アップロードまたは連合オーディエンス構成を使用して作成されたオーディエンスでは、プレビューと配達確認はサポートされていません。キャンペーンを計画する際には、次の点に注意してください。

* **アクティベーションの遅延：** オーディエンスは、取り込みが完了するとすぐに、Journey Optimizerで使用できるようになります。 これは通常 1 時間以内ですが、何らかの変動が生じる可能性があります。

* **アクティブ化されたレコードと ID ステッチ：** オーディエンス内のすべてのレコード（重複を含む）がアクティブ化されます。 次回の UPS プロファイルの書き出し時に、これらのレコードは ID ステッチを経ます。 そのため、アクティブ化されたレコードの数が、ID ステッチ後のプロファイルの数と異なる場合があります。

* **新しいプロファイルのターゲティング：**&#x200B;レコードと UPS プロファイルの間に一致が見つからない場合、新しい空のプロファイルが作成されます。このプロファイルは、データレイクに保存されるエンリッチメント属性にリンクされています。この新しいプロファイルは空なので、Journey Optimizer で通常使用されるターゲティングフィールド（personalEmail.address、mobilePhone.number など）は空であり、ターゲティングに使用できません。

  これを解決するには、チャネル設定の「実行フィールド」（またはチャネルに応じて「実行アドレス」）を「identityMap」として指定できます。これにより、オーディエンスの作成時に ID として選択した属性が、Journey Optimizer でのターゲティングに使用される属性になります。

## ハウツービデオ {#video}

オーディエンスを CSV 形式でAdobe Experience Platformにアップロードする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)

Federated Audience コンポジションの詳細情報。

>[!VIDEO](https://video.tv.adobe.com/v/3432261?quality=12)
