---
solution: Journey Optimizer
product: journey optimizer
title: 単一イベントの設定
description: 単一イベントの設定方法を説明します
feature: Journeys, Events
topic: Administration
role: Developer, Admin
level: Intermediate, Experienced
keywords: イベント、単一、作成、ジャーニー
exl-id: e22e2bc7-0c15-457a-8980-97bea5da7784
TQID: https://experienceleague.adobe.com/kADXordq0QBDchciYaOzFb-3plU0JruiGQJXwq-1sB8
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: d08afb72-92f6-4856-88e3-11ec34313c2fid: fa683eda-48de-4558-af32-2673edcd44fe
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1729
ht-degree: 0%

---

# 単一イベントの設定 {#configure-an-event}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_unitary"
>title="単一イベント"
>abstract="イベント設定を使用すると、Journey Optimizerがイベントとして受け取る情報を定義できます。 複数のイベント（ジャーニーの異なるステップ）を使用でき、複数のジャーニーで同じイベントを使用できます。 単一イベントは、特定のプロファイルにリンクされています。 ルールベースとシステム生成のどちらかにすることもできます。"

>[!CONTEXTUALHELP]
>id="ajo_journey_event_parameters"
>title="パラメーター"
>abstract="スキーマやペイロードフィールドなどのイベントのパラメーターを定義します。 ルールベースのイベントの場合、**[!UICONTROL イベント ID条件]** フィールドを使用して、ジャーニーをトリガーするイベントを特定するためにシステムで使用される条件を定義します。 イベントに使用するID タイプとプロファイル IDを追加します。"

単一イベントは、特定のプロファイルにリンクされています。 ルールベースとシステム生成のどちらかにすることもできます。  単一イベント [このセクション ](../event/about-events.md)の詳細をご覧ください。

新しいイベントを設定する最初の手順を以下に示します。

1. 管理メニューセクションで、**[!UICONTROL 設定]**&#x200B;を参照し、**[!UICONTROL イベント]** セクションで、**[!UICONTROL 管理]**&#x200B;をクリックします。 イベントのリストが表示されます。

   ![](assets/jo-event1.png)

1. 「**[!UICONTROL イベントを作成]**」をクリックして、新しいイベントを作成します。 画面の右側にイベント設定ペインが開きます。

   ![](assets/jo-event2.png)

1. イベントの名前を入力します。 また、説明を追加することもできます。

   >[!NOTE]
   >
   >英数字とアンダースコアのみ使用できます。 最大長は30文字です。

   ![](assets/jo-event3.png)

1. **[!UICONTROL Type]** フィールドで、**単一**&#x200B;を選択します。

1. 「**[!UICONTROL イベント ID タイプ]**」フィールドで、使用するイベント ID タイプを選択します。**ルールベース**&#x200B;または&#x200B;**システム生成**。 イベント ID タイプについて詳しくは、[このセクション ](../event/about-events.md#event-id-type)を参照してください。

   ![](assets/jo-event4.png)

1. このイベントを使用するジャーニーの数は、**[!UICONTROL で使用]** フィールドに表示されます。 「**[!UICONTROL ジャーニーを表示]**」アイコンをクリックすると、このイベントを使用するジャーニーのリストを表示できます。

1. スキーマとペイロードフィールドを定義します。これは、ジャーニーが受信するイベント情報（通常はペイロードと呼ばれます）を選択する場所です。 その後、この情報をジャーニーで使用できるようになります。 [このセクション ](../event/about-creating.md#define-the-payload-fields)を参照してください。

   ![](assets/jo-event5.png)

   >[!NOTE]
   >
   >「**[!UICONTROL システム生成]**」タイプを選択すると、eventID タイプフィールドを持つスキーマのみが使用できます。 「**[!UICONTROL ルールベース]**」タイプを選択すると、すべてのエクスペリエンスイベントスキーマを使用できます。

1. ルールベースのイベントの場合は、**[!UICONTROL イベント ID条件]** フィールド内をクリックします。 シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーをトリガーするイベントを特定するためにシステムで使用する条件を定義します。

   この例では、プロファイルの都市に基づいて条件を作成しました。 つまり、システムがこの条件（**[!UICONTROL City]** フィールドと&#x200B;**[!UICONTROL Paris]**&#x200B;値）に一致するイベントを受信するたびに、それをジャーニーに渡します。

   >[!NOTE]
   >
   >単純な式エディターでは、すべての演算子が使用できるわけではなく、データタイプに依存します。 例えば、フィールドの文字列タイプの場合、「contains」または「equal to」を使用できます。
   >
   >イベントの作成後に新しい列挙値でスキーマを変更する場合は、次の手順に従って変更を既存のイベントに適用する必要があります。イベントフィールドから列挙フィールドの選択を解除し、選択を確認してから、列挙フィールドを再度選択します。 新しい列挙値が表示されます。

1. ID タイプを追加します。 この手順はオプションですが、ID タイプを追加すると、Real-time Customer Profile Serviceに保存されている情報を活用できるので推奨されます。 イベントが持つキーのタイプを定義します。 詳しくは、[このセクション ](../event/about-creating.md#select-the-namespace)を参照してください。

1. プロファイル識別子を定義する：ペイロードフィールドからフィールドを選択するか、イベントに関連付けられた人物を識別するための式を定義します。 このキーは、ID タイプを選択した場合に自動的に設定されます（ただし、まだ編集できます）。 実際、ジャーニーはID タイプに対応するキーを選択します（例えば、メール ID タイプを選択すると、メールキーが選択されます）。 詳しくは、[このセクション ](../event/about-creating.md#define-the-event-key)を参照してください。

1. **[!UICONTROL 保存]**&#x200B;をクリックします。

   イベントが設定され、ジャーニーにドロップする準備が整います。 イベントを受信するには、追加の設定手順が必要です。 [このページ ](../event/additional-steps-to-send-events-to-journey.md)を参照してください。

## ペイロードフィールドの定義 {#define-the-payload-fields}

ペイロード定義を使用すると、ジャーニー内のイベントからシステムが受け取ると予想される情報と、イベントに関連付けられているユーザーを識別するキーを選択できます。 ペイロードは、Experience Cloud XDM フィールド定義に基づいています。 XDMについて詳しくは、[Adobe Experience Platform ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target="_blank"}を参照してください。

1. リストからXDM スキーマを選択し、**[!UICONTROL フィールド]** フィールドまたは&#x200B;**[!UICONTROL 編集]** アイコンをクリックします。

   ![](assets/journey8.png)

   スキーマで定義されているすべてのフィールドが表示されます。 フィールドのリストは、スキーマごとに異なります。 特定のフィールドを検索するか、フィルターを使用してすべてのノードとフィールドを表示するか、選択したフィールドのみを表示できます。 スキーマ定義によると、一部のフィールドは必須で事前に選択されている場合があります。 選択を解除することはできません。 ジャーニーでイベントを正しく受信するために必須のフィールドはすべて、デフォルトで選択されます。

   >[!NOTE]
   >
   >システム生成イベントの場合：
   >* XDM スキーマに`orchestration` フィールドグループを追加したことを確認してください。これにより、スキーマに[!DNL Journey Optimizer]を操作するために必要なすべての情報が含まれるようになります。
   >* **[!UICONTROL eventID]** フィールドは、選択したフィールドのリストに自動的に追加されるので、[!DNL Journey Optimizer]はイベントを識別できます。 イベントをプッシュするシステムはIDを生成しないでください。代わりに、ペイロードプレビューで使用可能なIDを使用してください。 [詳細情報](../event/about-creating.md#preview-the-payload)

   ![](assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 ビジネスユーザーがジャーニーで活用するフィールドです。 また、イベントに関連付けられているユーザーを識別するために使用するキーも含める必要があります（[このセクション ](../event/about-creating.md#define-the-event-key)を参照）。

1. 必要なフィールドの選択が完了したら、**[!UICONTROL OK]**&#x200B;をクリックするか、**[!UICONTROL Enter]**&#x200B;を押します。

   選択したフィールドの数が&#x200B;**[!UICONTROL フィールド]**&#x200B;に表示されます。

   ![](assets/journey12.png)

## ID タイプを選択 {#select-the-namespace}

>[!CONTEXTUALHELP]
>id="ajo_journey_namespace"
>title="ID タイプ"
>abstract="キーを選択して、イベントに関連付けられている顧客プロファイルを特定します。"

ID タイプ（以前は「名前空間」と呼ばれていました）を使用すると、イベントに関連付けられた人物を識別するために使用されるキーのタイプを定義できます。 設定はオプションです。 ジャーニー内で、[ リアルタイム顧客プロファイル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html){target="_blank"}から得られる追加情報を取得する場合に必要です。 カスタムデータソースを介してサードパーティシステムから取得したデータのみを使用する場合は、ID タイプ定義は必要ありません。

Adobe Experience Platform Identity Serviceを使用して、既存のID タイプを作成することも、新しいID タイプを作成することもできます。 詳しくは、[Adobe Experience Platform ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html){target="_blank"}を参照してください。

プライマリ IDを持つスキーマを選択した場合、**[!UICONTROL プロファイラー識別子]**&#x200B;および&#x200B;**[!UICONTROL ID タイプ]** フィールドが事前入力されます。 IDが定義されていない場合は、プライマリキーとして&#x200B;_identityMap > id_&#x200B;を選択します。 次に、ID タイプを選択する必要があります。キーは、_identityMap > id_&#x200B;を使用して、**[!UICONTROL ID タイプ]** フィールドの下に事前入力されます。

フィールドを選択すると、プライマリ ID フィールドにタグ付けされます。

![](assets/primary-identity.png)

ドロップダウンリストからID タイプを選択します。

![](assets/journey17.png)

ジャーニーごとに1つのID タイプのみが許可されます。 同じジャーニーで複数のイベントを使用する場合は、同じID タイプを使用する必要があります。 [このページ ](../building-journeys/journey.md)を参照してください。

>[!NOTE]
>
>人物ベースのID タイプのみを選択できます。 ルックアップテーブルのID タイプを定義している場合（例：製品ルックアップのProductID ID ID タイプ）、**ID タイプ** ドロップダウンリストでは使用できません。

## プロファイル IDの定義 {#define-the-event-key}

キーは、イベントペイロードデータの一部であり、システムがイベントに関連付けられた人物を識別できるフィールド、つまりフィールドの組み合わせです。 キーには、例えば、Experience Cloud ID、CRM ID、メールアドレスなどがあります。

Adobe Real-time Customer Profile データベースに保存されているデータを使用するには、イベントキーは、[Real-time Customer Profile Service](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html){target="_blank"}でプロファイルのIDとして定義した情報である必要があります。

プロファイル識別子を使用すると、イベントと個人プロファイルの間の紐付けをシステムで実行できます。 プライマリ IDを持つスキーマを選択すると、**[!UICONTROL プロファイル ID]**&#x200B;および&#x200B;**[!UICONTROL ID タイプ]** フィールドが事前入力されます。 IDが定義されていない場合、_identityMap > id_&#x200B;がプライマリキーになります。 次に、ID タイプを選択する必要があり、キーは&#x200B;_identityMap > id_&#x200B;を使用して自動的に事前入力されます。

フィールドを選択すると、プライマリ ID フィールドにタグ付けされます。

![](assets/primary-identity.png)

CRM IDや電子メールアドレスなど、別のキーを使用する必要がある場合は、次のように手動で追加する必要があります。

1. **[!UICONTROL プロファイル ID]** フィールド内または鉛筆アイコンをクリックします。

   ![](assets/journey16.png)

1. ペイロードフィールドのリストでキーとして選択したフィールドを選択します。

イベントが受信されると、キーの値により、システムはイベントに関連付けられた人物を識別できます。 [ID タイプ ](../event/about-creating.md#select-the-namespace)に関連付けられたこのキーを使用して、Adobe Experience Platformでクエリを実行できます。 [このページ ](../building-journeys/about-journey-activities.md#orchestration-activities)を参照してください。
このキーは、個人がジャーニー内にいることを確認するためにも使用されます。 実際、人は同じジャーニーの中で2つの異なる場所にいることはできません。 その結果、同じジャーニー内の異なる場所に同じキー（例えば、キーCRMID=3224）を配置することはできません。

## 高度な式エディター {#adv-exp-editor}

イベント ID条件またはプロファイル識別子を定義する場合は、高度な式エディターに切り替えて、より複雑なキー（イベントの2つのフィールドの連結など）を作成できます。

![](assets/journey20.png)

追加の操作を実行する場合は、**[!UICONTROL 詳細モード]** ボタンから高度な式の関数にアクセスできます。 これらの関数を使用すると、フィールドの一部（最初の10文字など）のみを考慮して、形式の変更やフィールド連結の実行など、特定のクエリを実行するために使用される値を操作できます。 この[ ページ ](../building-journeys/expression/expressionadvanced.md)を参照してください。


## ペイロードのプレビュー {#preview-the-payload}

ペイロードのプレビューでは、ペイロード定義を検証できます。

>[!NOTE]
>
>システム生成イベントの場合、イベントを作成する際に、ペイロードプレビューを表示する前に、イベントを保存して再度開きます。 この手順は、ペイロードでイベント IDを生成するために必要です。

1. 「**[!UICONTROL ペイロードを表示]**」アイコンをクリックして、システムで想定されるペイロードをプレビューします。

   ![](assets/journey13.png)

   選択したフィールドが表示されます。

   ![](assets/journey14.png)

1. プレビューを確認して、ペイロード定義を検証します。

1. 次に、ペイロードのプレビューをイベント送信の担当者と共有できます。 このペイロードは、[!DNL Journey Optimizer]にプッシュするイベントの設定を設計するのに役立ちます。 [このページ ](../event/additional-steps-to-send-events-to-journey.md)を参照してください。
