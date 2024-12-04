---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアップロード（CSV）と連合オーディエンス構成
description: カスタムアップロード（CSV）と連合オーディエンス構成オーディエンスを操作する際の、重要な情報とベストプラクティスについて説明します。
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
exl-id: d2365e3f-fbef-43c2-bf2a-0a868cb93015
source-git-commit: a98312d9ac5a457bfd6789bf79ad80a24d894a0b
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---

# カスタムアップロード（CSV）と連合オーディエンス構成 {#csv-fac}

## カスタムアップロードと連合オーディエンス構成について {#about}

セグメント定義とオーディエンス構成に加えて、[!DNL Journey Optimizer] を使用すると、CSV ファイルから読み込んだり、データウェアハウスのデータを活用したりして、オーディエンスを生成してターゲットにすることができます。

* **カスタムアップロード**：CSV ファイルを使用してオーディエンスを読み込みます。オーディエンスを読み込む方法については、Adobe Experience Platform の[セグメント化サービスに関するドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}を参照してください。

* **連合オーディエンス構成**：既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。[連合オーディエンス構成](https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home)に関するガイドを参照してください。

Journey Optimizer でこれらのオーディエンスをターゲットにするか、Adobe Experience Platform でサポートされる任意の宛先に対してアクティブ化できます。

➡️ [これらの機能をビデオで確認](#video)

## 必読 {#must-read}

このセクションでは、カスタムアップロード（CSV ファイル）と連合オーディエンス構成オーディエンスを使用する際に留意すべき重要な情報を示します。

* **プレビューと配達確認のサポート：**&#x200B;現在、CSV アップロードまたは連合オーディエンス構成を使用して作成されたオーディエンスでは、プレビューと配達確認はサポートされていません。キャンペーンを計画する際には、次の点に注意してください。

* **アクティベーションの遅延：**&#x200B;オーディエンスは、取り込みが完了するとすぐに、Journey Optimizer で使用できるようになります。これは通常 1 時間以内ですが、何らかの変動が生じる可能性があります。

* **アクティブ化されたレコードと ID ステッチ：**&#x200B;重複を含め、オーディエンス内のすべてのレコードがアクティブ化されます。次回の UPS プロファイルの書き出し時に、これらのレコードに対して ID ステッチが実行されます。その結果、アクティブ化されたレコードの数は、ID ステッチ後のプロファイルの数と異なる場合があります。

* **新しいプロファイルのターゲティング：**&#x200B;レコードと UPS プロファイルの間に一致が見つからない場合、新しい空のプロファイルが作成されます。このプロファイルは、データレイクに保存されるエンリッチメント属性にリンクされています。この新しいプロファイルは空なので、Journey Optimizer で通常使用されるターゲティングフィールド（personalEmail.address、mobilePhone.number など）は空であり、ターゲティングに使用できません。

  これを解決するには、チャネル設定の「実行フィールド」（またはチャネルに応じて「実行アドレス」）を「identityMap」として指定できます。これにより、オーディエンスの作成時に ID として選択した属性が、Journey Optimizer でのターゲティングに使用される属性になります。

## チュートリアルビデオ {#video}

オーディエンスを CSV 形式で Adobe Experience Platform にアップロードする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)

連合オーディエンス構成について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3432261?quality=12)
