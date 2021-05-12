---
title: Decision Managementの概要
description: Decision Managementの概要を説明します。 アーキテクチャ、オファー、決定、および実行に役立つ一般的な使用例について詳しく説明します。
translation-type: tm+mt
source-git-commit: b527186d0722492f5f509f1ae0a5315b9a9f771e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 38%

---


# Decision Managementについて{#about-offer-decision}

[!DNL Journey Optimizer] を使用すると、すべてのタッチポイントにわたって適切なタイミングで最高のオファーとエクスペリエンスを顧客に提供できます。設計が完了すると、パーソナライズされたオファーを使用してオーディエンスをターゲットできます。

Decision Management機能は、2つの主なコンポーネントで構成されています。

* **集中オファーライブラリ**&#x200B;は、オファーを構成する様々な要素を作成および管理し、それらの規則と制約を定義するインターフェイスです。
* 適切な時間、顧客、およびオファーを配信するチャネルを選択するために、Adobe Experience Platformのデータとリアルタイムの顧客プロファイルをオファーライブラリと共に活用する&#x200B;**オファー決定エンジン**。

![](../../assets/architecture.png)

次のような利点があります。

* 複数のチャネルをまたいでパーソナライズされたオファーを提供することで、キャンペーンのパフォーマンスが向上します。
* ワークフローの向上：マーケティングチームは、配信やキャンペーンを複数作成する代わりに、単一の配信を作成し、テンプレートの各部分のオファーを変えることでワークフローを向上させることができます。
* キャンペーンと顧客全体にオファーを表示する回数を制御します。

![](../../assets/do-not-localize/how-to-video.png) [Decision Managementについて詳しくは、次のチュートリアル](#tutorial-videos) ビデオをご覧ください。

## オファーと決定について{#offers-offer-activities}

**オファー**&#x200B;は、顧客に提示する条件を定義するコンテンツ、実施要件ルール、制約で構成されます。

オファーは&#x200B;**オファーライブラリ**&#x200B;を使用して作成されます。このライブラリは、実施要件ルールや制約を複数のコンテンツに関連付けてオファーを作成および公開できる中央オファーカタログを提供します（「[オファーライブラリユーザーインターフェイス](../get-started/user-interface.md)」を参照）。

![](../../assets/offer_structure.png)

オファーライブラリがオファーで強化されたら、オファーを&#x200B;**決定**(旧称「オファーアクティビティ」)に統合できます。

決定は、オファーのコンテナです。配信のターゲットに応じて提供すべき最適なオファーを選択するために、オファー決定エンジンを利用します。

## 一般的な使用例

意思決定管理機能とAdobe Experience Platformとの統合により、顧客の関与やコンバージョンを高めるのに役立つ多くの使用例をカバーできます。

* Adobe Experience Platform からのデータに基づいて、訪問顧客の興味ポイントに一致する Web サイトのホームページオファーを表示します。

   ![](../../assets/website.png)

* 顧客がいずれかの店舗のそばを通りかかった場合、属性（ロイヤルティ、性別、以前の購入など）に応じて利用可能なオファーを通知するプッシュ通知を送信します。

   ![](../../assets/push_sample.png)

* また、意思決定管理は、サポートチームに連絡する際の顧客体験を強化するのに役立ちます。 Decision Management APIを使用すると、お客様の引き換え後のベストオファーに関する情報をコールセンターエージェントのポータルに表示できます。

   ![](../../assets/call-center.png)

## チュートリアルビデオ {#tutorial-videos}

>[!NOTE]
>
>これらのビデオは、Adobe Experience Platformで構築されたOffer decisioningアプリケーションサービスに適用され、[!DNL Adobe Journey Optimizer]に固有のものではありません。 ただし、[!DNL Journey Optimizer]のコンテキストでデシジョン管理を使用する際の一般的なガイダンスを提供します。

### Decision Managementとは{#what-is-offer-decisioning}

次のビデオでは、Decision Managementの主な機能、アーキテクチャ、使用例について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/326961?quality=12&learn=on)

### オファーの定義と管理 {#use-offer-decisioning}

次のビデオでは、Decision Managementを使用してオファーを定義、管理し、リアルタイムの顧客データを活用する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/326841?quality=12&learn=on)
