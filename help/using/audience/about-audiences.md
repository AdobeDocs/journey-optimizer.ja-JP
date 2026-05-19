---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform オーディエンスについて
description: Adobe Experience Platform オーディエンスの使用方法を説明します
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
TQID: https://experienceleague.adobe.com/OL0VFfxegvbTbSLKeqFaUNTeZllmFtjMW6bmh1XDF00
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: fa683eda-48de-4558-af32-2673edcd44fe
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 629
ht-degree: 96%

---

# オーディエンスの基本を学ぶ {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="オーディエンス"
>abstract="Adobe Experience Platform では、リアルタイム顧客プロファイルデータを活用することで、セグメント定義を簡単に作成して、顧客の固有の行動や好みを取り込むターゲットオーディエンスを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="キャンペーンオーディエンスを選択"
>abstract="このリストには、使用可能なすべての Adobe Experience Platformオーディエンスが表示されます。 キャンペーンのターゲットにするオーディエンスを選択します。 キャンペーンで設定したメッセージは、選択したオーディエンスに属するすべての個人に送信されます。 [詳しくは、オーディエンスを参照してください](../audience/about-audiences.md)"

オーディエンスとは、類似した行動や特性を共有するユーザーのコレクションです。 Adobe Experience Platform セグメント化サービスを使用すると、Adobe Experience Platform 上で一元的に設定および管理され、Journey Optimizer 内で簡単にアクセスして、ジャーニーやキャンペーンでアクティブ化できます。

Adobe Journey Optimizer には、マーケティング活動を強化する目的で、オーディエンスの作成、管理、強化を行う堅牢なツールが用意されています。 Journey Optimizer を Adobe Real-Time Customer Data Platform と組み合わせると、オーディエンスをレイヤー化してより複雑なセグメント化を実現し、他の Adobe Experience Cloud ソリューションとオーディエンスを双方向に共有できます。

リアルタイムのデータストリームやバッチアップロードが発生すると、データセットが更新され、Journey Optimizer はリアルタイムで個人をオーディエンスとジャーニーに動的に移動させます。

>[!BEGINSHADEBOX]

このドキュメントでは、[!DNL Adobe Journey Optimizer] 内でオーディエンスを操作する方法について説明します。 オーディエンスポータルについて詳しくは、Adobe Experience Platform のセグメント化サービスのドキュメントを参照してください。 詳しくは、次の節を参照してください。

* [セグメント化サービス UI ガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/overview){target="_blank"}

* [セグメンテーションサービス – よくある質問](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq){target="_blank"}

>[!ENDSHADEBOX]

## オーディエンスの参照 {#browse}

オーディエンスは、**[!UICONTROL 顧客]**／**[!UICONTROL オーディエンス]**&#x200B;メニューから使用できます。

ダッシュボードでは、重要なオーディエンス間の重複を視覚的に表示し、貴重なオーディエンスのトレンドを探索することをサポートします。 例えば、特定の期間にわたるオーディエンスサイズの変化やオーディエンスの急増により、成功したオファーなど、オーディエンスの縮小や増加の原因となったイベントやアクションをハイライト表示できます。

![](assets/audiences-overview.png)

オーディエンスポータルから、標準化されたラベル付け、ガバナンスコントロール、検索可能なフォルダー、タグを使用して、オーディエンスを簡単に管理、検索、探索できます。

オーディエンスポータルでオーディエンスを操作する方法について詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target="_blank"}を参照してください。

## オーディエンスタイプ {#types}

オーディエンスは、様々な方法で生成できます。

* **セグメントの定義**：Adobe Experience Platform セグメント化サービスを使用して、新しいオーディエンス定義を作成します。 オーディエンスは、セグメント定義から生成され、評価タイプに応じて様々なタイミングで更新されます。

   * ストリーミングセグメント化：新しいデータが流入すると、オーディエンスはリアルタイムで更新されるので、ユーザーアクティビティに基づいて継続的な関連性が確保されます。
   * バッチセグメント化：オーディエンスは 24 時間ごとに更新され、一定の間隔でプロファイルのスナップショットが取得されます。 ジャーニーで使用する場合、新しく選定されたセグメントメンバーは、次のスナップショットまで表示されない場合があります。 [&#x200B; タイミングの詳細](../building-journeys/audience-qualification-events.md#timing-segment-membership)。
   * エッジセグメント化：オーディエンスはエッジ上で即座に評価されるので、リアルタイムのパーソナライゼーションが可能になります。

  [詳しくは、セグメント定義の作成方法を参照してください。](creating-a-segment-definition.md)

* **カスタムアップロード**：CSV ファイルを使用してオーディエンスを読み込みます。 [詳しくは、カスタムアップロードオーディエンスの作成方法を参照してください](custom-upload.md)

* **オーディエンス構成**：構成ワークフローを作成し、既存のオーディエンスをビジュアルキャンバスに組み合わせ、ランク、分割、結合などのアクションを適用して新しいオーディエンスを作成します。 [詳しくは、オーディエンス構成の操作方法を参照してください](get-started-audience-orchestration.md)

* **連合オーディエンス構成**：既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。 [詳しくは、連合オーディエンス構成の操作方法を参照してください](federated-audience-composition.md)。

## ジャーニーとキャンペーンのターゲットオーディエンス {#target-audiences}

オーディエンスの準備が整ったら、ジャーニーの作成やキャンペーンの作成時にオーディエンスを選択し、関連するメッセージを適切なタイミングで適切な人物にリーチできます。 [詳しくは、Journey Optimizer の Audience Activation を参照してください](target-audiences.md)。

## チュートリアルビデオ {#video}

Journey Optimizer の統合顧客プロファイルおよびオーディエンスについて説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3432671?quality=12)
