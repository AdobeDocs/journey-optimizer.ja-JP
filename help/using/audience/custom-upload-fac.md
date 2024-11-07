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
source-git-commit: 26d311802236a1f9e8f6273c1291bcb54138aad2
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 38%

---

# カスタムアップロード（CSV）と Federated Audience Composition {#csv-fac}

## カスタムアップロードと Federated Audience コンポジションについて {#about}

セグメントの定義とオーディエンスの構成に加えて、[!DNL Journey Optimizer] を使用すると、CSV ファイルから読み込んだり、データウェアハウスのデータを活用したりして、オーディエンスを生成およびターゲットにすることができます。

* **カスタムアップロード**：CSV ファイルを使用してオーディエンスを読み込みます。オーディエンスを読み込む方法については、Adobe Experience Platform の[セグメント化サービスに関するドキュメント](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}を参照してください。

* **連合オーディエンス構成**：既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。[連合オーディエンス構成](https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home)に関するガイドを参照してください。

  >[!AVAILABILITY]
  >
  >連合オーディエンス構成は現在、一連の組織でのみ使用できます（限定的に利用可能）。詳しくは、アドビ担当者にお問い合わせください。

これらのオーディエンスをJourney Optimizerでターゲットにするか、Adobe Experience Platformでサポートされる任意の宛先に対してアクティブ化できます

➡️ [ ビデオでこれらの機能を確認する ](#video)

## 必読 {#must-read}

この節では、カスタムアップロード（CSV ファイル）および Federated Audience Composition オーディエンスを使用する際に留意すべき重要な情報を示します。

* **プレビューと配達確認のサポート：** 現在、プレビューと配達確認は、CSV アップロードまたは Federated Audience Composition を使用して作成されたオーディエンスではサポートされていません。 キャンペーンを計画する際には、次の点に注意してください。

* **アクティベーションの遅延：** オーディエンスは、取り込みが完了するとすぐに、Journey Optimizerで使用できるようになります。 これは通常 1 時間以内ですが、何らかの変動が生じる可能性があります。

* **アクティブ化されたレコードと ID ステッチ：** オーディエンス内のすべてのレコード（重複を含む）がアクティブ化されます。 次回の UPS プロファイルの書き出し時に、これらのレコードは ID ステッチを経ます。 そのため、アクティブ化されたレコードの数が、ID ステッチ後のプロファイルの数と異なる場合があります。

* **新しいプロファイルのターゲット設定：** レコードと UPS プロファイルの一致が見つからない場合、新しい空のプロファイルが作成されます。 このプロファイルは、データレイクに保存されるエンリッチメント属性にリンクされています。この新しいプロファイルは空なので、Journey Optimizer で通常使用されるターゲティングフィールド（personalEmail.address、mobilePhone.number など）は空であり、ターゲティングに使用できません。

  これを解決するには、チャネル設定の「実行フィールド」（またはチャネルに応じて「実行アドレス」）を「identityMap」として指定できます。これにより、オーディエンス作成時に ID として選択された属性が、Journey Optimizerでのターゲティングに使用される属性になります。

## ハウツービデオ {#video}

オーディエンスを CSV 形式でAdobe Experience Platformにアップロードする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)

Federated Audience コンポジションの詳細情報。

>[!VIDEO](https://video.tv.adobe.com/v/3432261?quality=12)
