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
badge: label="限定提供" type="Informative"
hide: true
hidefromtoc: true
exl-id: 7b50c933-9738-4b1b-acae-08f0a8d41dab
source-git-commit: c62653af3c1eacaaf55dcf181d33f2253521e33d
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 100%

---

# メッセージコンテンツの書き出し {#message-export}

>[!CONTEXTUALHELP]
>id="ajo_admin_msg_export"
>title="送信済みコンテンツを保持および書き出し"
>abstract="このオプションを選択すると、この設定を使用して送信済みメールまたは SMS メッセージのコンテンツを [!DNL Experience Platform] データセットに書き込むことができます。レコードは 3 日間保持され、その間、独自のストレージに書き出すことができます。"

>[!AVAILABILITY]
>
>この機能は現在、一連の組織でのみ使用できます（限定提供）。詳しくは、アドビ担当者にお問い合わせください。

**メッセージの書き出し**&#x200B;を使用すると、送信済みメールと SMS メッセージのコンテンツを [!DNL Journey Optimizer] から [!DNL Adobe Experience Platform] の宛先経由で独自のストレージに転送でき、これにより [!DNL Experience Platform] から外部エンドポイントにデータを配信できます。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/home){target="_blank"}

この機能を使用すると、[!DNL Journey Optimizer] 経由で送信され、書き出し対象としてマークされたメールと SMS メッセージのコンテンツが、[!DNL Experience Platform] **AJO メッセージの書き出しデータセット**&#x200B;に書き込まれます。

その後、レコードは **AJO メッセージの書き出しデータセット**&#x200B;に 3 日間保持され、その間に任意の外部システムに書き出しすることができます。
<!--
## Terminology

* **[!DNL Experience Platform] destinations** - Framework to deliver data out of Experience Platform into external endpoints. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home){target="_blank"}
* **AJO Message Export Dataset** - An [!DNL Experience Platform] dataset which stores the message content of email and SMS messages sent via [!DNL Journey Optimizer] which have been marked for export.
* **Retention**: Records in the AJO Message Export Dataset are retained for 3 calendar days from ingestion.-->

## ガードレール

* この機能は、メールと SMS チャネルのみをサポートします。
* AJO メッセージの書き出しデータセット内のレコードは、取り込みから 3 日間保持されます。
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
   * スケジュール：3 日間の保持期間内に実行されることを確認します。

### チャネル設定でメッセージの書き出しを有効化 {#config-message-export}

キャンペーンやジャーニーにメッセージの書き出しを適用するには、チャネル設定レベルで専用オプションを有効にする必要があります。次の手順に従います。

1. [!DNL Journey Optimizer] で、目的のメールまたは SMS [チャネル設定](channel-surfaces.md#create-channel-surface)を編集または作成します。

1. 「**[!UICONTROL メッセージの書き出しを有効化]**」オプションを選択します。

   ![](assets/config-message-export.png)

1. 変更を保存し、チャネル設定を送信します。

このチャネル設定を使用してキャンペーンまたはジャーニー経由で送信されたメールと SMS メッセージは、**AJO メッセージの書き出しデータセット**&#x200B;に書き込まれます。その後、定義済みの書き出しデータフローに基づいて、レコードは選択したストレージの宛先に書き出されます。

**[!UICONTROL メッセージの書き出しの有効化]**&#x200B;切替スイッチを無効にすると、このチャネル設定の新しいレコードがデータセットに取り込まれなくなります。既存のレコードは保持が期限切れになるまで残ります。
