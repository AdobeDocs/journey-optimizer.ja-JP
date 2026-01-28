---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer でのメッセージのエクスポート
description: メッセージを書き出す方法について説明します。
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: 書き出し, メッセージ, HIPAA, メール, SMS, 設定
exl-id: 7b50c933-9738-4b1b-acae-08f0a8d41dab
source-git-commit: ab0f100d53cb987919eb134442bf05e64c30719a
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 44%

---

# メッセージコンテンツの書き出し {#message-export}

>[!CONTEXTUALHELP]
>id="ajo_admin_msg_export"
>title="送信済みコンテンツを保持および書き出し"
>abstract="このオプションを選択すると、この設定を使用して、送信されたメールまたは SMS メッセージのコンテンツを [!DNL Experience Platform] データセットに書き込むことができます。 レコードは取り込み後 7 日間保持され、その間、独自のストレージに書き出すことができます。"

>[!AVAILABILITY]
>
>この機能は、メッセージ書き出しアドオン機能を購入した組織のメールおよび SMS チャネルでのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。

**メッセージの書き出し** を使用すると、送信されたメールと SMS メッセージのコンテンツを [!DNL Journey Optimizer] から [!DNL Adobe Experience Platform] の宛先を介して独自のストレージに転送できます。これにより、[!DNL Experience Platform] から外部エンドポイントにデータを配信できます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/home){target="_blank"}

この機能により、書き出し用にマークされた [!DNL Journey Optimizer] を介して送信されたメールおよび SMS メッセージのコンテンツは、[!DNL Experience Platform] **AJO Message Export Dataset** に書き込まれます。 [詳しくは、データセットを参照してください](../data/get-started-datasets.md)

その後、レコードは取り込みから 7 暦日間データセットに保持され、その間、選択した外部システムに書き出すことができます。

## ガードレール

* この機能は、**メール** および **SMS** チャネルのみをサポートします。
* AJO メッセージ書き出しデータセットのレコードは、**取り込みから 7 暦日間保持** されます。
* 以下に説明するように、メッセージの書き出しを有効にする前に送信されたメッセージでは、バックフィルはサポートされません。

## メッセージの書き出しを有効化 {#enable-message-export}

メッセージの書き出し機能のオンボーディングプロセスは、次の 2 つの手順で構成されます。

1. [!DNL Experience Platform] で[書き出しデータフローを設定](#set-up-export-dataflow)。
1. [!DNL Journey Optimizer] のチャネル設定で[メッセージの書き出しを有効化](#config-message-export)。

>[!WARNING]
>
>書き出しを有効にしてメッセージを送信した後の新しいレコードのみが表示されます。書き出しプロセスを設定し、「メッセージの書き出し」オプションを有効にする前のコンテンツのバックフィルはサポートされていません。

### 書き出しデータフローを設定 {#set-up-export-dataflow}

データを書き出す前に、[!DNL Experience Platform] の宛先と使用するデータセットを定義して、書き出しプロセスを設定する必要があります。次の手順に従います。

>[!NOTE]
>
>この設定は、サンドボックスごとに設定する必要があります。

1. Experience Platform の[宛先タイプ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/destination-types){target="_blank"}を選択します。データを受信する準備が整った、使用可能な宛先プラットフォームのリストについて詳しくは、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/overview){target="_blank"}を参照してください。

1. [!DNL Experience Platform] では、資格情報、バケット／コンテナ、パスプレフィックス、セキュリティオプションを定義して、宛先を設定します。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets){target="_blank"}

1. 次のデータを使用して、データセット書き出しフローを作成します。

   * ソースデータセット:「**AJO メッセージの書き出しデータセット**」を選択します。
   * ファイル形式：「JSON」または「Parquet」を選択します（ダウンストリームツールに基づいていずれかを選択します）。
   * スケジュール：7 日間の保持期間内に実行されるようにします。

### チャネル設定でメッセージの書き出しを有効化 {#config-message-export}

キャンペーンやジャーニーにメッセージの書き出しを適用するには、チャネル設定レベルで専用オプションを有効にする必要があります。次の手順に従います。

1. [!DNL Journey Optimizer] で、目的のメールまたは SMS [チャネル設定](channel-surfaces.md#create-channel-surface)を編集または作成します。

1. 「**[!UICONTROL メッセージの書き出しを有効化]**」オプションを選択します。

   ![](assets/config-message-export.png)

1. 変更を保存し、チャネル設定を送信します。

このチャネル設定を使用してキャンペーンまたはジャーニー経由でメッセージを送信すると、メールおよび SMS メッセージが **0}AJO メッセージエクスポートデータセット } に書き込まれます。**&#x200B;その後、データセット内の [ レコードにアクセス ](#access-exported-data) し、定義した書き出しデータフローに基づいて、選択したストレージ宛先に書き出すことができます。

>[!NOTE]
>
>**[!UICONTROL メッセージの書き出しの有効化]**&#x200B;切替スイッチを無効にすると、このチャネル設定の新しいレコードがデータセットに取り込まれなくなります。既存のレコードは保持が期限切れになるまで残ります。

## 書き出したメッセージデータへのアクセス {#access-exported-data}

メッセージの書き出しを有効にしたチャネル設定を使用してメッセージが送信されたら、**AJO メッセージの書き出しデータセット** で、書き出したデータにアクセスして確認できます。

書き出されたメッセージデータを表示するには：

1. [!DNL Journey Optimizer] では、左側のナビゲーションで **[!UICONTROL データ管理]**/**[!UICONTROL データセット]** に移動します。 [詳しくは、データセットを参照してください](../data/get-started-datasets.md)

1. システム生成データセットを表示していることを確認します。

1. リストから **AJO メッセージ書き出しデータセット** を選択します。

   ![](assets/datasets-list.png)

1. データセットの詳細ページで **[!UICONTROL データセットをプレビュー]** をクリックして、最新のレコードを表示します。

   ![](assets/ajo-message-export-dataset.png)

データセットには、メッセージエクスポートが有効なチャネル設定を介して送信される各メッセージに関する包括的な情報が含まれています。これには、件名行、メッセージ本文、受信者のメールアドレスまたは電話番号、送信者のアドレスまたは電話番号、送信日時、パーソナライゼーションデータなどが含まれます。

データセット内のすべてのレコードは、**取り込みから 7 カレンダー日** 保持されます。 この保存期間中は、コンプライアンス監査や法的問い合わせ用にデータにアクセスしたり、構成されたExperience Platformの出力先を介してデータを独自のストレージ・システムにエクスポートしたりできます。

