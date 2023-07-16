---
solution: Journey Optimizer
product: journey optimizer
title: クラウドストレージの場所へのデータセットの書き出し
description: Adobe Experience Platform クラウドストレージの宛先を使用してデータセットを書き出す方法について説明します。
role: User
level: Beginner
badge: label="Beta" type="Informative"
keywords: Platform, データレイク, 作成, レイク, データセット, プロファイル
exl-id: 66b5c691-ddc4-4e9b-9386-2ce6c307451c
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 93%

---

# クラウドストレージの場所へのデータセットの書き出し {#export-datasets}

>[!AVAILABILITY]
>
>データセットの書き出し機能は、現在ベータ版です。すべての Adobe Journey Optimizer ユーザーがご利用いただけます。アクセス権がない場合は、アドビ担当者に相談して、宛先へのアクセス権を取得してください。

Journey Optimizer では、データセットの内容を書き出すために、クラウドストレージの場所とのライブ接続を確立できます。

データを定期的に書き出すことにより、お客様とのやり取りの完全かつ最新の記録を保持し、この情報をレポートや分析目的で使用し、法的要件への準拠を維持することができます。

## ご利用いただけるクラウドストレージの宛先 {#destinations}

「**[!UICONTROL カタログ]**」タブの&#x200B;**[!UICONTROL 宛先]**&#x200B;メニューからアクセスできる 6 つのクラウドストレージの宛先にデータセットを書き出すことができます。

![](assets/dataset-export-setup.png)

>[!AVAILABILITY]
>
>これらの宛先はすべてベータ版で利用でき、変更される場合があります。

各宛先について詳しくは、 Adobe Experience Platform のドキュメントを参照してください。

* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=ja)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=ja)
* [Azure Data Lake Gen 2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=ja)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=ja)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=ja)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=ja)

## 前提条件 {#prerequisites}

データセットの書き出しを開始する前に、次の前提条件を確認してください。

* データセットを書き出すには、**宛先の管理**、**宛先の表示**、**宛先のアクティブ化**、**データセット宛先の管理とアクティブ化**&#x200B;の各[アクセス制御権限](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja#permissions)が必要です。 必要な権限を取得するには、[アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/overview.html?lang=ja)を参照するか、製品管理者に問い合わせてください。

* 書き出すデータセットに第 2 世代のデータが含まれていないことを確認してください。この機能は、第 1 世代データのみの書き出しをサポートします。つまり、[Real-Time Customer Data Platform 製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/real-time-customer-data-platform-b2c-edition-prime-and-ultimate-packages.html)で定義されている生データをサポートします。第 1 世代データには、Adobe Experience Platform ソース経由で取り込んだデータセットや、Analytics コネクタおよび Journey Optimizer のログ／レポートデータセットなどのアドビソリューションを使用して収集したデータセットが含まれます。

## データセットを書き出す主な手順 {#main-steps}

データセットをクラウドストレージの場所に書き出す主な手順を以下に示します。

![](assets/dataset-export-process.png)

各手順について詳しくは、 Adobe Experience Platform のドキュメントの[クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)を参照してください。

1. **クラウドストレージの宛先を設定します**。まだ行っていない場合は、宛先カタログからクラウドストレージの宛先に接続します。[新しい宛先接続を作成する方法については、こちらを参照してください](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=ja#setup)

   <!--![](assets/dataset-export-setup.png)-->

1. データセットを書き出す&#x200B;**クラウドストレージの宛先を選択**&#x200B;します。宛先カタログで、目的のカードにある「**[!UICONTROL データセットを書き出し]**」ボタンをクリックし、使用する接続を選択します。

   <!--![](assets/dataset-export-destination.png)-->

   >[!NOTE]
   >
   >Adobe Journey Optimizerをリアルタイム顧客プロファイルと共に使用している場合、宛先カードには「アクティブ化」ボタンが表示され、有効にした権限に応じて、データセットの書き出しとこの宛先のオーディエンスのアクティブ化の両方が可能です。

1. 選択した宛先に書き出す&#x200B;**データセットを選択**&#x200B;します。

   <!--![](assets/dataset-export-dataset-selection.png)-->

1. データセットの&#x200B;**書き出しをスケジュール**&#x200B;します。書き出しを開始するタイミングと実行する頻度を指定します。

   <!--![](assets/dataset-export-schedule.png)-->

1. 設定の最後に表示される概要を確認して、**書き出しをレビューして確認**&#x200B;します。

   <!--![](assets/dataset-export-review.png)-->

書き出しが完了すると、設定したスケジュールに従って、データセットの内容がクラウドストレージの場所に保存されます。[データセットの書き出しが成功したことを確認する方法については、こちらを参照してください](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja#verify)
