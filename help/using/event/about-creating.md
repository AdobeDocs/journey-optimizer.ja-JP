---
solution: Journey Optimizer
product: journey optimizer
title: ユニタリイベントの設定
description: ユニタリイベントを設定する方法について説明します。
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: e22e2bc7-0c15-457a-8980-97bea5da7784
source-git-commit: ef838945e0c3595de8ad920203b278bb51671d16
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 0%

---

# ユニタリイベントの設定 {#configure-an-event}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_unitary"
>title="ユニタリイベント"
>abstract="このイベント設定を使用すると、オプティマイザーがイベントとして受け取る情報を定義することができます。 複数のイベントを使用して journeys を作成すると、複数のイベントを使用して同じイベントを使用することができます。 ユニタリイベントは特定のプロファイルにリンクされています。 ルールベースまたはシステムによって生成されたものでもかまいません。"

ユニタリイベントは特定のプロファイルにリンクされています。 ルールベースまたはシステムによって生成されたものでもかまいません。  このセクションでは、ユニタリイベント [ について詳しく説明 ](../event/about-events.md) しています。

次の手順では、新しいイベントを設定します。

1. 「管理メニュー」セクションで、を選択 **[!UICONTROL Configurations]** します。 **[!UICONTROL Events]**&#x200B;セクションのをクリック **[!UICONTROL Manage]** します。イベントのリストが表示されます。

   ![](assets/jo-event1.png)

1. をクリック **[!UICONTROL Create Event]** して、新しいイベントを作成します。 画面の右側にイベント設定ペインが表示されます。

   ![](assets/jo-event2.png)

1. イベントの名前を入力します。 説明を追加することもできます。

   ![](assets/jo-event3.png)

   >[!NOTE]
   >
   >スペースまたは特殊文字は使用しないでください。 30文字を超えないようにしてください。

1. **[!UICONTROL Type]**&#x200B;フィールドで「ユニタリ **」を選択** します。

   ![](assets/jo-event3bis.png)

1. **[!UICONTROL Event ID type]**&#x200B;フィールドで、使用 **するイベント ID タイプを選択します。ルールベースまたは** システムによっ **て生成さ** れます。この節 ](../event/about-events.md#event-id-type) のイベント ID タイプについて詳しくは、 [ ここを参照してください。

   ![](assets/jo-event4.png)

1. このイベントを使用している journeys の数がフィールドに **[!UICONTROL Used in]** 表示されます。 このアイコンをクリック **[!UICONTROL View journeys]** すると、このイベントを使用して journeys のリストが表示されます。

1. 「スキーマ」フィールドと「ペイロード」フィールドを定義します。これは、journeys が受け取るイベント情報 (通常はペイロードと呼ばれます) を選択する場合に使用されます。 これにより、これらの情報をお客様の旅に使用することができます。 この項 ](../event/about-creating.md#define-the-payload-fields) を参照してください [ 。

   ![](assets/jo-event5.png)

   >[!NOTE]
   >
   >タイプを選択 **[!UICONTROL System Generated]** すると、「イベント id タイプ」フィールドがあるスキーマだけが使用可能になります。 タイプを選択 **[!UICONTROL Rule Based]** すると、すべての操作イベントスキーマが使用可能になります。

1. ルールに基づいた **[!UICONTROL Event ID condition]** イベントの場合は、フィールド内をクリックします。 単純な式エディターを使用して、システムによって使用される条件を定義して、旅をトリガーするイベントを識別します。
   ![](assets/jo-event6.png)

   この例では、プロファイルの市町村に基づいて条件を作成しています。 これにより、この条件に一致するイベント ( **[!UICONTROL City]** フィールドと **[!UICONTROL Paris]** 値) がシステムに送信されるたびに、そのイベントが journeys に渡されることになります。

   >[!NOTE]
   >
   >アドバンスエクスプレッションエディターは、を **[!UICONTROL Event ID condition]** 定義するときには使用できません。 単純な式エディターでは、すべての演算子を使用できるわけではありません。データ型によって異なります。 例えば、フィールドのストリング型については、「次を含む」または「等しい」を使用できます。

1. 名前空間を追加します。 この手順はオプションですが、名前空間を追加することで、リアルタイムカスタマープロファイルサービスに格納されている情報を活用できるようになります。 これにより、イベントのキーの型が定義されます。 この項 ](../event/about-creating.md#select-the-namespace) を参照してください [ 。
1. 「ペイロード」フィールドでフィールドを選択するか、イベントに関連付けられた人物を識別するための数式を定義します。 このキーは、名前空間を選択した場合に自動的に設定されます (ただし、編集することもできます)。 実際に、journeys では、名前空間に対応する必要があるキーがピックされます (例えば、email 名前空間を選択した場合は、電子メールキーが選択されます)。 この項 ](../event/about-creating.md#define-the-event-key) を参照してください [ 。

   ![](assets/jo-event7.png)

1. をクリック **[!UICONTROL Save]** します。

   イベントが設定され、旅に出られる準備ができました。 イベントを受信するには、その他の設定手順が必要です。 このページ ](../event/additional-steps-to-send-events-to-journey.md) を参照してください [ 。

## ペイロードフィールドの定義 {#define-the-payload-fields}

ペイロード定義を使用すると、旅のイベントからシステムが受け取ると予想される情報と、そのイベントに関連付けられた人物を識別するためのキーを選択できます。 ペイロードは、「エクスペリエンス Cloud XDM」フィールド定義に基づいています。 XDM について詳しくは、『 Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) {target = &quot;_blank&quot;} を [ 参照してください。

1. リストから「XDM」スキーマを選択し、フィールドまたは **[!UICONTROL Edit]** アイコンをクリック **[!UICONTROL Fields]** します。

   ![](assets/journey8.png)

   スキーマに定義されているすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。 特定のフィールドを検索することも、フィルターを使用してすべてのノードとフィールドを表示することも、選択したフィールドのみを表示することもできます。 スキーマ定義に従って、一部のフィールドは必須で、事前に選択されている場合があります。 選択を解除することはできません。 初期設定では、journeys によって適切にイベントを受信するために必須のすべてのフィールドが選択されています。

   >[!NOTE]
   >
   >システムによって生成されたイベントについては、&quot;オーケストレーション&quot; フィールドグループが XDM スキーマに追加されていることを確認してください。 これにより、スキーマには、操作 [!DNL Journey Optimizer] に必要な情報がすべて含まれていることが確認されます。

   ![](assets/journey9.png)

1. イベントから受信することが予想されるフィールドを選択します。 これらのフィールドは、出張中にビジネスユーザーによって利用されます。 さらに、イベントに関連付けられた人物を識別するために使用するキーも含める必要があります (この項 ](../event/about-creating.md#define-the-event-key) を参照して [ ください)。

   >[!NOTE]
   >
   >システムによって生成されたイベント **[!UICONTROL eventID]** の場合は、選択したフィールドのリストに自動的にフィールドが追加されます。これ [!DNL Journey Optimizer] により、イベントを識別することができます。 イベントをプッシュするシステムでは、ID を生成しないようにする必要があります。これは、ペイロードプレビューで使用可能なものを使用する必要があります。 この項 ](../event/about-creating.md#preview-the-payload) を参照してください [ 。

1. 必要なフィールドを選択したら、 **[!UICONTROL Ok]** またはキーを押し **[!UICONTROL Enter]** ます。

   フィールドに **[!UICONTROL Fields]** は、選択したフィールドの数が表示されます。

   ![](assets/journey12.png)

## 名前空間を選択します。 {#select-the-namespace}

>[!CONTEXTUALHELP]
>id="ajo_journey_namespace"
>title="Identity 名前空間"
>abstract="イベントに関連付けられた顧客プロファイルを識別するためのキーを選択します。"

名前空間により、イベントに関連付けられた人物を識別するために使用するキーのタイプを定義できます。 この設定はオプションです。 Journeys では、に、リアルタイムのカスタマープロファイル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) から [ 取得された追加情報が必要な場合があります。 {target = &quot;_blank&quot;} のようになります。カスタムデータソースを使用して、サードパーティシステムからのデータのみを使用している場合は、名前空間定義は必要ありません。

事前に定義された定義のいずれかを使用するか、Id 名前空間サービスを使用して新しいものを作成することができます。 Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html) {target = &quot;_blank&quot;} を [ 参照してください。

Primary id を持つスキーマを選択した場合は、 **[!UICONTROL Profiler identifier]** および **[!UICONTROL Namespace]** フィールドが事前に入力されます。 Id が定義されていない場合は、> id _を主キーとして選択_ します。次に、名前空間を選択して、> id _を使用してキーに事前に値が入力されていることを確認します (このフィールドを&#x200B;**[!UICONTROL Namespace]**参照して_ ください)。

フィールドを選択する場合は、主な id フィールドにタグが付けられます。

![](assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](assets/journey17.png)

1つの旅に使用できる名前空間は1つだけです。 同じ旅で複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。 このページ ](../building-journeys/journey.md) を参照してください [ 。

## プロファイル id を定義します。 {#define-the-event-key}

キーとは、イベントペイロードデータの一部であり、システムがイベントに関連付けられた人物を識別できるようにする、フィールドまたはフィールドの組み合わせです。 このキーには、操作の対象となるクラウド ID、CRM ID、電子メールアドレスなどがあります。

Adobe リアルタイムカスタマープロファイルデータベースに格納されたデータを使用するには、イベントキーが、リアルタイムカスタマープロファイルサービス ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) ({target = &quot;_blank&quot;}) で [ プロファイル id として定義されている情報になっている必要があります。

プロファイル id を使用して、システムでは、イベントと個人のプロファイル間で調整を行うことができます。 Primary id を持つスキーマを選択した場合は、 **[!UICONTROL Profile identifier]** および **[!UICONTROL Namespace]** フィールドが事前に入力されます。 Id が定義されて _いない場合は、> map id_ がプライマリキーになります。 次に、名前空間を選択する必要があります。また、id _を使用して_ 自動的にキーを入力します。

フィールドを選択する場合は、主な id フィールドにタグが付けられます。

![](assets/primary-identity.png)

CRM ID や電子メールアドレスのような別のキーを使用する必要がある場合は、以下に説明するように手動で追加する必要があります。

1. フィールド内 **[!UICONTROL Profile identifier]** 、または鉛筆アイコンをクリックします。

   ![](assets/journey16.png)

1. ペイロードフィールドのリストのキーとして選択したフィールドを選択します。 また、高度な式エディターに切り替えて、さらに複雑なキーを作成することもできます (例えば、イベントの2つのフィールドを連結するなど)。

   ![](assets/journey20.png)

イベントの受信時に、システムはそのイベントに関連付けられた人物を識別することができます。 名前空間に関連付けられたキー (この項 ](../event/about-creating.md#select-the-namespace) を参照してください [ ) は、Adobe エクスペリエンスプラットフォーム上でクエリーを実行するために使用することができます。このページ ](../building-journeys/about-journey-activities.md#orchestration-activities) を参照してください [ 。このキーは、人が旅に参加しているかどうかを確認するためにも使用されます。 実際には、2つの異なる場所に参加することはできません。 その結果、システムでは、同じキー (例えば、キー CRMID = 3224) を同じ場所に配置することはできません。

また、その他の操作を実行する必要がある場合は、アドバンスエクスプレッション関数 ( **[!UICONTROL Advanced mode]** ) にアクセスすることもできます。 これらの関数を使用すると、このような特定のクエリーを実行するために使用される値を操作できます。これにより、フィールドの一部だけ (例えば、10番目の文字など) 考慮されます。 この [ ページ ](../building-journeys/expression/expressionadvanced.md) を参照してください。

## ペイロードのプレビュー {#preview-the-payload}

ペイロードの定義を検証することができます。

>[!NOTE]
>
>システムによって生成されたイベントの場合は、イベントを作成するときに、ペイロードプレビューを表示する前にイベントを保存してから再度開きます。 この手順は、ペイロードにイベント ID を生成するために必要です。

1. **[!UICONTROL View Payload]**&#x200B;アイコンをクリックして、システムで表示する必要があるペイロードをプレビューします。

   ![](assets/journey13.png)

   選択されたフィールドが表示されていることに注意してください。

   ![](assets/journey14.png)

1. プレビューを確認して、ペイロード定義を検証します。

1. これにより、ペイロードプレビューを、イベント送信の担当者に公開できます。 このようなペイロードにより、にプッシュする [!DNL Journey Optimizer] イベントの設定をデザインするのに役立ちます。 このページ ](../event/additional-steps-to-send-events-to-journey.md) を参照してください [ 。
