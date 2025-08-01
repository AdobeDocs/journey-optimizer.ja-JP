---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーイベントの活用
description: ジャーニーでのイベントの使用方法を学ぶ
feature: Journeys, Events
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate, Experienced
keywords: イベント, ジャーニー, 定義, 開始
exl-id: fb3e51b5-4cbb-4949-8992-1075959da67d
source-git-commit: e4ea791dbc4362bff1d822f0b36add829e7a259d
workflow-type: ht
source-wordcount: '1079'
ht-degree: 100%

---

# ジャーニーイベントの活用 {#about-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_list"
>title="ジャーニーイベント"
>abstract="イベントは人物と結び付いています。これは、人物の行動（例えば、人物が製品を購入した、ショップを訪問した、web サイトを離脱したなど）または人物と結び付いて起こったこと（例えば、人物が 10,000 ロイヤルティポイントに到達したなど）に関連しています。Journey Optimizer は、ジャーニーで単一イベントをリッスンして、次の最適なアクションを編成します。"

イベントを使用すると、ジャーニーを個別にトリガーし、ユーザーがジャーニーにエントリする際に各ユーザーにリアルタイムのメッセージを配信できます。

イベントの設定では、ジャーニーで想定されるイベントを設定します。受信イベントのデータは、Adobe エクスペリエンスデータモデル（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取得 API から取り込みます。複数のイベントを（ジャーニーの様々なステップで）使用できます。また、同じイベントを複数のジャーニーで使用することもできます。

イベントの設定は&#x200B;**必須**&#x200B;であり、データエンジニアが実施する必要があります。

**単一イベント**&#x200B;と&#x200B;**ビジネスイベント**&#x200B;の 2 つのタイプのイベントを設定できます。


➡️ [この機能をビデオで確認](#video)

## 単一イベント {#unitary-events}

**単一**&#x200B;イベントは、ユーザーに関連付けられます。これは、ユーザーの行動（例えば、ユーザーが製品を購入した、ショップを訪問した、web サイトを離脱したなど）またはユーザーとリンクして発生した事象（例えば、ユーザーが 10,000 ロイヤルティポイントに到達したなど）に関連しています。[!DNL Journey Optimizer] はジャーニーでこのイベントをリッスンして、次の最適なアクションを編成します。単一のイベントは、ルールベースとすることも、システム生成とすることもできます。単一イベントの作成方法について詳しくは、この[ページ](../event/about-creating.md)を参照してください。

（イベントまたはオーディエンスの選定で始まる）単一ジャーニーには、同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぐガードレールが含まれています。プロファイルの再エントリは、デフォルトで 5 分間一時的にブロックされます。例えば、あるイベントが特定のプロファイルのジャーニーを 12:01 にトリガーし、12:03 に別のイベントが到着した場合（それが同じイベントであっても、同じジャーニーをトリガーする別のイベントであっても）、このプロファイルのジャーニーが再び開始されることはありません。

## ビジネスイベント {#business-events}

**ビジネス**&#x200B;イベントは、特定のプロファイルにリンクされません。例えば、ニュースアラート、スポーツの最新情報、航空便の変更やキャンセル、在庫の更新、気象情報などがあります。これらのイベントは一人ひとりのプロファイルに固有のものではなく、特定のニューストピックの購読者、航空便の乗客、在庫切れ商品に興味を持つ買い物客など 、関心を持つプロファイルの数は任意です。ビジネスイベントは常にルールベースです。ビジネスイベントをジャーニーにドロップすると、その直後に&#x200B;**オーディエンスを読み取り**&#x200B;アクティビティが自動的に追加されます。ビジネスイベントの作成方法について詳しくは、[このページ](../event/about-creating-business.md)を参照してください。


## イベント ID のタイプ {#event-id-type}

**ビジネス**&#x200B;イベントの場合、イベント ID のタイプは常にルールベースです。

**単一**&#x200B;イベントの場合、イベント ID には次の 2 つのタイプがあります。

* **ルールベース**&#x200B;イベント：このタイプのイベントでは、eventID は生成されません。簡単な式エディターを使用して、システムがジャーニーをトリガーする関連イベントの特定に使用するルールを定義します。このルールは、イベントペイロードで使用可能な任意のフィールドに基づくことができます。例えば、プロファイルの場所や、プロファイルの買い物かごに追加された項目数などです。

  >[!CAUTION]
  >
  >キャッピングルールは、ルールベースのイベントに対して定義します。ジャーニーが処理できる対象イベントの数を、特定の組織で 1 秒あたり 5,000 件に制限します。これは Journey Optimizer の SLA に対応しています。Journey Optimizer ライセンスおよび [Journey Optimizer Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html) を参照します。

* **システム生成**&#x200B;イベント：このイベントでは eventID が必要です。eventID フィールドは、イベントの作成時に自動的に生成されます。イベントをプッシュするシステムでは、ID を生成せずに、ペイロードプレビューにある ID を渡す必要があります。

>[!NOTE]
>
>Journey Optimizer でジャーニーをトリガーするには、イベントをデータ収集コアサービス（DCCS）にストリーミングする必要があります。バッチで取り込まれたイベントや、内部 Journey Optimizer データセット（メッセージフィードバック、メールトラッキングなど）からのイベントを、ジャーニーのトリガーに使用することはできません。ストリーミングイベントを取得できないユースケースについては、代わりに、それらのイベントに基づいてオーディエンスを作成し、**オーディエンスを読み取り**&#x200B;アクティビティを使用してください。オーディエンスの選定は技術的に使用できますが、使用されるアクションに応じて、ダウンストリームの課題が生じる可能性があります。このデータは、必ずしもリアルタイムプロファイルに移動する必要はありません。イベントをセグメント化に使用する場合は、プロファイルのデータセットを有効にすることをお勧めします。

## データサイクル {#data-cycle}

イベントは POST API 呼び出しです。イベントは、ストリーミング取り込み API を使用して Adobe Experience Platform に送信されます。トランザクションメッセージング API を通じて送信されるイベントの URL 宛先は「インレット」と呼ばれます。イベントのペイロードは、XDM 形式に従います。

ペイロードには、ストリーミング取得 API が機能するために必要な情報（ヘッダー内）、[!DNL Journey Optimizer] が機能するために必要な情報、ジャーニー内で使用する情報（本文内で使用する、放棄された買い物かごの金額など）が含まれます。ストリーミング取り込みには、認証済みと非認証の 2 つのモードがあります。ストリーミング取得 API の詳細については、[このリンク](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=ja){target="_blank"}を参照してください。

ストリーミング取り込み API を通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、その後 Adobe Experience Platform に送られます。イベントスキーマで「リアルタイム顧客プロファイルサービス」フラグが有効になっていて、データセット ID にも「リアルタイム顧客プロファイル」フラグが設定されている場合は、リアルタイム顧客プロファイルサービスに移動します。

システム生成イベントの場合、パイプラインがフィルタリングするイベントは、[!DNL Journey Optimizer] が提供する [!DNL Journey Optimizer] eventID（以下のイベント作成プロセスを参照）がペイロードに含まれているイベントです。ルールベースのイベントの場合は、eventID 条件を使用してイベントを識別します。これらのイベントは [!DNL Journey Optimizer] がリッスンし、対応するジャーニーがトリガーされます。

## イベントの更新と削除

既存のジャーニーの中断を避けるには、ドラフトジャーニー、ライブジャーニーまたはクローズドジャーニーで使用されるイベントを編集する場合、名前と説明の変更およびペイロードフィールドの追加のみが可能です。

ライブジャーニー、ドラフトジャーニーまたはクローズドジャーニーで使用されるイベントは、削除できません。使用済みイベントを削除するには、そのイベントを使用しているジャーニーを停止するか、そのイベントを使用しているドラフトジャーニーからそのイベントを削除する必要があります。「**[!UICONTROL 使用場所]**」フィールドを確認できます。特定のイベントを使用するジャーニーの数が表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、対応するジャーニーのリストを表示できます。

## チュートリアルビデオ {#video}

イベントの設定方法と、ストリーミングエンドポイントとイベントのペイロードの指定方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3431517?quality=12&captions=jpn)

ビジネスイベントに適用できる使用例を理解します。ビジネスイベントを使用したジャーニーの構築方法と、適用するベストプラクティスについて説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3416427?quality=12&captions=jpn)
