---
title: ダイレクトメールメッセージの作成
description: Journey Optimizer でダイレクトメールメッセージを作成する方法を学ぶ
feature: Direct Mail
topic: Content Management
role: User
level: Beginner
keywords: ダイレクトメール, メッセージ, キャンペーン
exl-id: 6b438268-d983-4ab8-9276-c4b7de74e6bd
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 94%

---

# ダイレクトメールメッセージの作成 {#create-direct}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail"
>title="ダイレクトメールの作成"
>abstract="スケジュールされたキャンペーンでダイレクトメールメッセージを作成し、ダイレクトメールプロバイダーが顧客にメールを送信するために必要な抽出ファイルを設計します。"

ダイレクトメールメッセージを作成するには、スケジュール済みキャンペーンを作成し、抽出ファイルを設定します。このファイルは、ダイレクトメールプロバイダーが顧客にメールを送信するために必要です。

>[!IMPORTANT]
>
>ダイレクトメールメッセージを作成する前に、次の設定が完了していることを確認します。
>
>1. [ファイルのルーティング設定](../direct-mail/direct-mail-configuration.md#file-routing-configuration)：抽出ファイルをアップロードして保存するサーバーを指定します。
>1. [ダイレクトメールメッセージサーフェス](../direct-mail/direct-mail-configuration.md#direct-mail-surface)：ファイルのルーティング設定を参照します。


## ダイレクトメールキャンペーンの作成{#create-dm-campaign}

ダイレクトメールキャンペーンを作成するには、次の手順に従います。

1. 新しいスケジュール済みキャンペーンを作成し、アクションとして「**[!UICONTROL ダイレクトメール]**」を選択します。

1. 使用する&#x200B;**[!UICONTROL ダイレクトメールサーフェス]**&#x200B;を選択し、「**[!UICONTROL 作成]**」をクリックします。[ダイレクトメールサーフェスの作成方法についてはこちらを参照](direct-mail-configuration.md#direct-mail-surface)

   ![](assets/direct-mail-campaign.png){width="800" align="center"}

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの「**[!UICONTROL タイトル]**」と「**[!UICONTROL 説明]**」を編集します。

1. ターゲットオーディエンスを定義するには、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform オーディエンスから選択します。[詳細情報](../audience/about-audiences.md)

   >[!IMPORTANT]
   >
   >現時点では、オーディエンスの選択は 300 万プロファイルに制限されています。この制限は、アドビ担当者にリクエストすることで解除できます。

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したオーディエンス内の個人を識別するために適した名前空間を選択します。[詳細情報](../event/about-creating.md#select-the-namespace)

   ![](assets/direct-mail-campaign-properties.png){width="800" align="center"}

1. キャンペーンは特定の日付にスケジュールすることも、定期的に繰り返すように設定することもできます。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

これで、ダイレクトメールプロバイダーに送信する抽出ファイルの設定を開始できます。

## 抽出ファイルの設定 {#extraction-file}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail_data_fields"
>title="データフィールド"
>abstract="ダイレクトメールプロバイダーが顧客にメールを送信するために必要な抽出ファイルに表示する列と情報を追加および設定します。最大 50 列を追加できます。"

>[!CONTEXTUALHELP]
>id="ajo_direct_mail_formatting"
>title="抽出ファイルの書式設定"
>abstract="各フィールドで、パーソナライゼーションエディターを使用して表示するラベルと情報を指定します。 <br/><br/>「<b>並べ替え基準</b>」オプションを使用すると、選択したフィールドを使用して、抽出ファイルの列を並べ替えることができます。"

1. 抽出ファイルに表示する列と情報を設定します。

   1. 「**[!UICONTROL 追加]**」ボタンをクリックして、新しい列を作成します。

   1. 右側に&#x200B;**[!UICONTROL フォーマット]**&#x200B;パネルが表示され、選択した列をセットアップできます。列の「**[!UICONTROL ラベル]**」を指定します。

   1. が含まれる **[!UICONTROL データ]** フィールドで、表示するプロファイル属性を [パーソナライゼーションエディター](../personalization/personalization-build-expressions.md).

   1. 列を使用して抽出ファイルを並べ替えるには、列を選択し、「**[!UICONTROL 並べ替え基準]**」オプションの切替スイッチをオンにします。「**[!UICONTROL データフィールド]**」セクションで、列のラベルの横に&#x200B;**[!UICONTROL 並べ替え基準]**&#x200B;アイコンが表示されます。







抽出ファイルは、ダイレクトメールプロバイダーが顧客にメールを送信するために必要です。抽出ファイルの設定を定義するには、次の手順に従います。

1. キャンペーンの設定画面で、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、抽出ファイルのコンテンツを設定します。

1. 次のように、抽出ファイルのプロパティを調整します。

   1. 抽出ファイルの望ましい&#x200B;**[!UICONTROL ファイル名]**&#x200B;を指定します。

   1. 指定したファイル名に自動タイムスタンプを付加する場合は、「**[!UICONTROL 書き出しファイル名にタイムスタンプを追加]**」オプションを有効にします。

   1. 抽出ファイルの先頭または末尾に情報を追加することが必要になる場合があります。その場合は、「**[!UICONTROL メモ]**」フィールドを使用して、メモをヘッダーまたはフッターとして含めるかどうかを指定します。

      ![](assets/direct-mail-properties.png){width="800" align="center"}

1. 抽出ファイルに表示する列と情報を設定します。

   1. 「**[!UICONTROL 追加]**」ボタンをクリックして、新しい列を作成します。

   1. 右側に&#x200B;**[!UICONTROL フォーマット]**&#x200B;パネルが表示され、選択した列をセットアップできます。列の「**[!UICONTROL ラベル]**」を指定します。

   1. が含まれる **[!UICONTROL データ]** フィールドで、表示するプロファイル属性を [パーソナライゼーションエディター](../personalization/personalization-build-expressions.md).

   1. 列を使用して抽出ファイルを並べ替えるには、列を選択し、「**[!UICONTROL 並べ替え基準]**」オプションの切替スイッチをオンにします。「**[!UICONTROL データフィールド]**」セクションで、列のラベルの横に&#x200B;**[!UICONTROL 並べ替え基準]**&#x200B;アイコンが表示されます。

      ![](assets/direct-mail-content.png){width="800" align="center"}

   1. これらの手順を繰り返して、抽出ファイルに必要な数の列を追加します。なお、追加できる列数は最大 50 です。

      列の位置を変更するには、「**[!UICONTROL データフィールド]**」セクションで、目的の位置に列をドラッグ＆ドロップします。列を削除するには、列を選択し、**[!UICONTROL フォーマット]**&#x200B;パネルの「**[!UICONTROL 削除]**」ボタンをクリックします。

これで、ダイレクトメールメッセージをテストし、オーディエンスに送信できるようになりました。[ダイレクトメールメッセージのテストおよび送信の方法についてはこちらを参照](test-send-direct-mail.md)
