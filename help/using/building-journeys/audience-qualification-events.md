---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスの選定イベント
description: オーディエンスの選定イベントについて説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: 選定，イベント，オーディエンス，ジャーニー，プラットフォーム
exl-id: 7e70b8a9-7fac-4450-ad9c-597fe0496df9
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 39%

---

# オーディエンスの選定イベント {#segment-qualification}

## オーディエンスの選定イベントについて{#about-segment-qualification}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_segment_qualification"
>title="オーディエンスの選定イベント"
>abstract="このアクティビティを使用すると、ジャーニーはAdobe Experience Platformオーディエンス内のプロファイルのエントリと離脱をリッスンして、個人をジャーニーにエントリさせたり、ジャーニーを進めたりできます。"

このアクティビティを使用すると、ジャーニーはAdobe Experience Platformオーディエンス内のプロファイルのエントリと離脱をリッスンして、個人をジャーニーにエントリさせたり、ジャーニーを進めたりできます。 オーディエンスの作成について詳しくは、 [セクション](../audience/about-audiences.md).

「シルバーカスタマー」オーディエンスがあるとします。 このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送ることができます。

このタイプのイベントは、ジャーニーの最初または後半に配置できます。

>[!IMPORTANT]
>
>Adobe Experience Platformオーディエンスは 1 日 1 回 (**バッチ** オーディエンス ) またはリアルタイム (**ストリーミング** オーディエンス (Adobe Experience Platformの「高頻度オーディエンス」オプションを使用 ) に関連付けられます )。
>
>選択したオーディエンスがストリーミングされると、このオーディエンスに属する個人は、潜在的にリアルタイムでジャーニーにエントリします。 オーディエンスがバッチの場合、新たにこのオーディエンスの対象として認定されたユーザーは、Adobe Experience Platformでオーディエンスの計算を実行すると、ジャーニーにエントリする可能性があります。
>
>エクスペリエンスイベントフィールドグループは、オーディエンスの読み取り、オーディエンスの選定、ビジネスイベントアクティビティで始まるジャーニーでは使用できません。


1. 「 **[!UICONTROL イベント]** カテゴリとドロップ **[!UICONTROL オーディエンスの選定]** アクティビティをキャンバスに追加します。

   ![](assets/segment5.png)

1. アクティビティに&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します。この手順はオプションです。

1. をクリックします。 **[!UICONTROL 対象ユーザ]** 」フィールドに値を入力し、活用するオーディエンスを選択します。

   >[!NOTE]
   >
   >リストに表示される列はカスタマイズして並べ替えることができます。

   ![](assets/segment6.png)

   オーディエンスを追加すると、 **[!UICONTROL コピー]** ボタンを使用すると、その名前と ID をコピーできます。

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/segment-copy.png)

1. 内 **[!UICONTROL 動作]** 「 」フィールドで、オーディエンスのエントリ、出口、またはその両方をリッスンするかどうかを選択します。

   >[!NOTE]
   >
   >注意： **[!UICONTROL 入力]** および **[!UICONTROL 終了]** に対応する **実現済み** および **終了** Adobe Experience Platformからのオーディエンスパーティシペーションステータス。 オーディエンスの評価方法について詳しくは、 [セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results){target="_blank"}.

1. 名前空間を選択します。これは、イベントがジャーニーの最初のステップとして位置付けられている場合にのみ必要です。デフォルトでは、このフィールドには、最後に使用した名前空間が事前に入力されています。

   >[!NOTE]
   >
   >ユーザーベースの ID 名前空間のみ選択できます。名前空間を参照テーブルに対して定義した場合（例：ProductID 名前空間を Product 参照に対して定義した場合）、その名前空間を&#x200B;**名前空間**&#x200B;ドロップダウンリストで使用することはできません。

   ![](assets/segment7.png)

ペイロードには、条件とアクションで使用できる次のコンテキスト情報が含まれています。

* 行動（エントリ、離脱）
* 選定のタイムスタンプ
* オーディエンス id

式エディターを、 **[!UICONTROL オーディエンスの選定]** アクティビティの **[!UICONTROL AudienceQualification]** ノード。 **[!UICONTROL 前回の選定時間]**&#x200B;と&#x200B;**[!UICONTROL ステータス]**&#x200B;のどちらかを選択できます（エントリまたは離脱）。

[条件アクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。

![](assets/segment8.png)

オーディエンスの選定イベントを含む新しいジャーニーは、公開してから 10 分後に動作します。 この時間間隔は、専用サービスのキャッシュ更新間隔に対応します。したがって、このジャーニーを使用する前に 10 分待つ必要があります。

## ベストプラクティス {#best-practices-segments}

この **[!UICONTROL オーディエンスの選定]** 「 」アクティビティを使用すると、Adobe Experience Platformオーディエンスから資格を得る、または資格を失う個人のジャーニーに直ちに参加できます。

この情報は瞬時に処理されます。測定した値は、1 秒あたり 10,000 件の速度でイベントを受信したことを示しています。その結果、エントリのピークがどのように発生するか、その回避方法やジャーニーの準備方法を理解する必要があります。

### バッチオーディエンス{#batch-speed-segment-qualification}

バッチオーディエンスにオーディエンス資格を使用する場合、入口のピークは日次計算の時点で発生することに注意してください。 ピークのサイズは、1 日にオーディエンスに入る（または出る）個人の数によって異なります。

さらに、バッチオーディエンスが新しく作成され、ジャーニーで即座に使用される場合、最初の計算バッチでは、非常に多くの人がジャーニーにエントリする可能性があります。

### ストリーミングオーディエンス{#streamed-speed-segment-qualification}

ストリーミングオーディエンスにオーディエンス資格を使用する場合、オーディエンスの継続的な評価が原因で、入口/出口のピークが大きくなるリスクが少なくなります。 ただし、オーディエンス定義によって大量の顧客が同時に認定される場合は、ピークも生じる可能性があります。

ストリーミングセグメント化について詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html?lang=ja#api)を参照してください。

### オーバーロードの回避方法 {#overloads-speed-segment-qualification}

ジャーニーで使用するシステム（データソース、カスタムアクション、チャネルアクションアクティビティ）の過負荷を回避するのに役立つ、いくつかのベストプラクティスを示します。

では、 **[!UICONTROL オーディエンスの選定]** アクティビティ：作成直後のバッチオーディエンス。 最初の計算のピークは回避されます。まだ計算されていないオーディエンスを使用しようとすると、ジャーニーキャンバスに黄色い警告が表示されます。

![](assets/segment-error.png)

ジャーニーで使用するデータソースとアクションのキャッピングルールを設定して、データソースの過負荷を避けます。詳しくは、[Journey Orchestration のドキュメント](https://experienceleague.adobe.com/docs/journeys/using/working-with-apis/capping.html?lang=ja){target="_blank"}を参照してください。キャッピングルールには再試行がないことに注意してください。再試行が必要な場合は、条件やアクションで「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」ボックスをオンにし、ジャーニーで代替パスを使用する必要があります。

実稼動ジャーニーでオーディエンスを使用する前に、は常に、毎日、このオーディエンスの対象となる個人の数を最初に評価します。 これをおこなうには、 **[!UICONTROL 対象ユーザ]** メニューを開き、オーディエンスを開いて、 **[!UICONTROL プロファイルの推移]** グラフ。

![](assets/segment-overload.png)
