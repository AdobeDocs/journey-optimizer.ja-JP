---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのアクティビティの基本を学ぶ
description: ジャーニーのアクティビティの基本を学ぶ
feature: Journeys, Activities, Overview
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: ジャーニー, アクティビティ, 開始, イベント, アクション
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/8M5qgoXuziyVXMHPOwiM3xztCSNmglc2fBu-BaXn9mc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: d0a62d3c-b79e-47e4-929e-40ef3cffa037id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: b5e335a9-0e5f-4dda-8845-c4ac5dca2be4id: cfba2953-2ce9-4b00-a00c-71cd338ae63fid: d8353d85-5da7-453d-bd68-40ad33fa0ab7id: e57d1da4-32c2-4cc6-945c-9feb219156ffid: fa683eda-48de-4558-af32-2673edcd44feid: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 82c3ff093eef40fa31fc0f3bb7baa32c857ff6ea
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 71%

---

# ジャーニーのアクティビティの基本を学ぶ {#about-journey-activities}

イベント、オーケストレーション、アクションアクティビティを組み合わせて、マルチステップのクロスチャネルシナリオを構築できます。

## イベントアクティビティ {#event-activities}

パーソナライズされたジャーニーは、オンライン購入などのイベントから始まります。 プロファイルがジャーニーにエントリすると、プロファイル自体がジャーニー内を移動します。 各プロファイルは、異なるパスとペースを取ることができます。 イベントで開始すると、イベントが発生したときにジャーニーがトリガーします。 各プロファイルは、ジャーニーで定義されたステップに従います。

テクニカルユーザーが設定したイベント（[このページ ](../event/about-events.md)を参照）は、パレットの最初のカテゴリに表示されます。 このカテゴリは、画面の左側にあります。 次のイベントアクティビティを使用できます。

* [一般イベント](../building-journeys/general-events.md)
* [反応](../building-journeys/reaction-events.md)
* [オーディエンスの選定](../building-journeys/audience-qualification-events.md)

![ジャーニー designer のイベントアクティビティパレット](assets/journey43.png)

ジャーニーを開始するには、イベントアクティビティをドラッグ＆ドロップします。 ダブルクリックでも開始できます。

![ジャーニー designer のイベントアクティビティのドラッグ＆ドロップ](assets/journey44.png)

## オーケストレーションアクティビティ {#orchestration-activities}

オーケストレーションは、カスタマージャーニーの次のステップを判断するのに役立つ条件です。 これらの条件には、その人がオープンサポートケースを持っているか、購入を完了したかが含まれます。 また、現地の天気予報や、顧客が10,000 ポイントに達したかどうかも確認できます。

画面左側にあるパレットで、次のオーケストレーションアクティビティを使用できます。

* [最適化](optimize.md)
* [オーディエンスを読み取り](read-audience.md)
* [待機](wait-activity.md)
* [ジャーニーフラグ](journey-fragments.md)
* [コンテンツの決定](content-decision.md)
* [データセットの参照](dataset-lookup.md)

![ジャーニー designer のオーケストレーションアクティビティパレット](assets/journey-orchestration-activities.png)

## アクションアクティビティ {#action-activities}

アクションは、メッセージの送信など、何らかのトリガーの結果として発生させるもので、 顧客が体験するジャーニーの一部です。

画面の左側にある&#x200B;**[!UICONTROL イベント]**&#x200B;および&#x200B;**[!UICONTROL オーケストレーション]**&#x200B;の下のパレットから、**[!UICONTROL アクション]** カテゴリを見つけることができます。 次のアクションアクティビティを使用できます。

* [組み込みのチャネルアクション ](../building-journeys/journey-action.md)が&#x200B;**アクション** アクティビティから利用可能です
* [カスタムアクション](../building-journeys/using-custom-actions.md)
* [ジャンプ](../building-journeys/jump.md)

![ジャーニー designer のアクションアクティビティパレット](assets/journey58.png)

これらのアクティビティは、様々な通信チャネルを表します。 これらを組み合わせて、クロスチャネルシナリオを作成できます。

また、メッセージを送信する特定のアクションを設定することもできます。

* サードパーティシステムを使用してメッセージを送信する場合は、特定のカスタムアクションを作成できます。 [詳細情報](../action/action.md)

* [!DNL Adobe Campaign]および[!DNL Adobe Journey Optimizer]を使用している場合は、次の節を参照してください。

   * [[!DNL Adobe Journey Optimizer]および [!DNL Adobe Campaign] v7/v8](../action/acc-action.md)
   * [[!DNL Adobe Journey Optimizer]および [!DNL Adobe Campaign] 標準](../action/acs-action.md)
   * [[!DNL Adobe Journey Optimizer]および [!DNL Adobe Marketo Engage]](../action/marketo-engage.md)

## ベストプラクティス {#best-practices}

これらのレコメンデーションは、ジャーニーを読みやすく、一貫性を保ち、トラブルシューティングを容易にするために使用できます。

### ラベルの追加

ほとんどのアクティビティでは、**[!UICONTROL ラベル]**&#x200B;を定義できます。 これにより、キャンバスのアクティビティの下に表示される名前にサフィックスが追加されます。 これは、ジャーニーで同じアクティビティを複数回使用し、より簡単に識別したい場合に便利です。 また、エラーが発生した場合のデバッグも容易になり、レポートも読みやすくなります。 また、オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を追加することもできます。

![ジャーニーアクティビティプロパティの「ラベル」および「説明」フィールド](assets/journey-action-label.png)

>[!NOTE]
>
>一部のアクティビティでは、その ID もパネルに表示されます。 この ID は、変更される可能性があるラベルよりも安定したキーとしてレポートに使用できます。

### 詳細パラメーターの管理 {#advanced-parameters}

ほとんどのアクティビティには、変更できない多数の詳細なパラメーターや技術的なパラメーターが表示されます。

![ジャーニーアクティビティプロパティの詳細パラメーターフィールド](assets/journey-advanced-parameters.png)

読みやすくするには、右側のパネルの上部にある「**[!UICONTROL 読み取り専用フィールドを非表示]**」ボタンを使用して、これらのパラメーターを非表示にします。

![ジャーニーアクティビティプロパティの読み取り専用フィールドを非表示アイコン](assets/journey-hide-read-only-fields.png)

一部のコンテキストでは、特定の用途でこれらのパラメーターの値を上書きできます。 値を強制的に指定するには、フィールドの右側にある「**[!UICONTROL パラメーターの上書きを有効にする]**」アイコンをクリックします。 [詳細情報](../configuration/primary-email-addresses.md#override-execution-address-journey)

![メールアクティビティプロパティの「パラメーターの上書きを有効にする」オプション](assets/journey-enable-parameter-override.png)

>[!NOTE]
>
>詳細設定パラメーターが非表示になっている場合は、「**[!UICONTROL 読み取り専用フィールドを表示]**」ボタンをクリックします
>
>![ジャーニーアクティビティプロパティの読み取り専用フィールドを表示アイコン](assets/journey-show-read-only-fields.png){width=60%}

### 代替パスの追加

アクションまたは条件でエラーが発生すると、個人のジャーニーが停止します。 続行するには、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスをオンにするだけです。 [このセクション ](../building-journeys/using-the-journey-designer.md#paths)を参照

![条件アクティビティプロパティの「代替パスを追加」オプション](assets/journey42.png)

## トラブルシューティング {#troubleshooting}

ジャーニーをテストおよび公開する前に、すべてのアクティビティが正しく設定されていることを確認します。 システムでエラーが検出される場合は、テストまたは公開を実行できません。

アクティビティとジャーニーでのエラーのトラブルシューティング方法について詳しくは、[このページ](troubleshooting.md)を参照してください。

[監視とトラブルシューティング ](../../rp_landing_pages/troubleshoot-journey-landing-page.md)も参照してください
