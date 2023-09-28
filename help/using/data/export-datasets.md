---
solution: Journey Optimizer
product: journey optimizer
title: クラウドストレージの場所へのデータセットの書き出し
description: Adobe Experience Platform クラウドストレージの宛先を使用してデータセットを書き出す方法について説明します。
role: User
level: Beginner
keywords: Platform, データレイク, 作成, レイク, データセット, プロファイル
exl-id: 66b5c691-ddc4-4e9b-9386-2ce6c307451c
source-git-commit: a5cb591a3340f2af27806967e5a1403be9fe26e4
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 47%

---

# クラウドストレージの場所へのデータセットの書き出し {#export-datasets}

Journey Optimizer では、データセットの内容を書き出すために、クラウドストレージの場所とのライブ接続を確立できます。

データを定期的にエクスポートすることで、顧客とのやり取りの完全で最新の記録を作成し、レポート、アーカイブ、データ分析の目的で容易に利用できるようにします。

## ご利用いただけるクラウドストレージの宛先 {#destinations}

「**[!UICONTROL カタログ]**」タブの&#x200B;**[!UICONTROL 宛先]**&#x200B;メニューからアクセスできる 6 つのクラウドストレージの宛先にデータセットを書き出すことができます。

![](assets/dataset-export-setup.png)


各宛先について詳しくは、 Adobe Experience Platform のドキュメントを参照してください。

* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=ja)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=ja)
* [Azure Data Lake Gen 2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=ja)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=ja)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=ja)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=ja)

## 書き出しに使用できるJourney Optimizerデータセット {#datasets}

製品層に応じて書き出すJourney Optimizerデータセットについて、次の表で説明します ( [Journey Optimizer Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}) |データセット|説明|層| | — | — | — | | AJO BCC フィードバックイベントデータセット | AJO BCC フィードバックイベントデータセット | Prime | | AJO 分類データセット |電子メールおよびプッシュアプリケーションのフィードバックイベントをJourney Optimizerから取り込むデータセット。 SDK を通じて作成されます。 | Prime | | AJO 同意サービスデータセット |プロファイルの同意情報を保存します。 | Prime | | AJO メールトラッキングエクスペリエンスイベントデータセット |レポートおよびオーディエンス作成の目的で使用される、E メールチャネルのインタラクションログ。  | Prime | | AJO エンティティデータセット |エンドユーザーに送信されたメッセージのエンティティメタデータを保存するデータセット。  | Prime | | AJO インバウンドアクティビティイベントデータセット | Journey Optimizer Web および配信およびインタラクションイベント用のアプリ内チャネルのデータセット。 | Prime | | AJO インタラクティブメッセージプロファイルデータセット | API トリガーキャンペーンをサポートするために作成されたプロファイルを保存します | Prime | | AJO メッセージフィードバックイベントデータセット |メッセージ配信ログ。 レポートやオーディエンス作成を目的とした Journey Optimizer からのすべてのメッセージ配信に関する情報です。バウンスに関するメール ISP からのフィードバックも、このデータセットに記録されます。| Prime | | AJO プロファイルカウンター拡張機能 | counter_id でキー指定された counter_value と expiryDate を含むオブジェクトのマップを保持します | Prime | | AJO プッシュプロファイルデータセット |プロファイルのプッシュトークンを格納します。 | Prime | | AJO プッシュトラッキングエクスペリエンスイベントデータセット |プッシュチャネルのインタラクションログ。レポートおよびオーディエンス作成の目的で使用されます。  | Prime | | AJO サーフェスデータセット | Journey Optimizer Inbound Surfaces スキーマに関連する空のデータセット | Prime | | AOOutputForUPSDataset | UPS に書き戻す AO オーディエンスメンバーシップがすべて含まれます | Prime | | Audience Orchestration プロファイルデータセット |オーディエンス構成オーディエンス用のオーディエンス構成によって生成されます。 すべての Audience Composition オーディエンス、その属性およびエンリッチメントデータが含まれます | Prime | |決定オブジェクトリポジトリ — アクティビティ |は、ユーザーインターフェイスでの決定とも呼ばれます。 ただし、判定ロジックを含むすべての構築ブロックをまとめる、ユーザーが作成するオブジェクトです。 例えば、考慮する必要のある特定の配置（場所）の場合（オファーコレクション）と、それらのオファーで使用するランキング方法。 | Ultimate | |決定オブジェクトリポジトリ — フォールバックオファー |これは、ユーザーが作成する他のタイプのオファーのリポジトリです。 特に、パーソナライズされたオファーを閲覧する資格がなく、何かを見る必要がある場合は、少なくともフォールバックオファーが表示されます。 このデータセットには、このタイプのオファーの属性が含まれています | Ultimate | |決定オブジェクトリポジトリ — パーソナライズされたオファー |これは、ユーザーが作成するオファーのタイプのリポジトリです。 したがって、このデータセットには、このタイプのオファーに関する属性が含まれます | Ultimate | |決定オブジェクトリポジトリ — 配置 |オファーを表示する場所を定義するオブジェクトのリポジトリです。 | Ultimate | |ジャーニーステップイベント | Journey Optimizerから生成され、レポートなどのサービスで使用されるすべてのジャーニーステップエクスペリエンスイベントをキャプチャします。 | Prime | |ジャーニー |ジャーニーの各ステップの情報を格納するメタデータデータセット | Prime | | ODE DecisionEvents - prod decisioning |リクエストに基づいて決定を下すたびに、それを決定イベントとしてカウントします | Ultimate |

## 前提条件 {#prerequisites}

データセットを書き出すには、 [アクセス制御権限](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja#permissions) 以下に示します。 [アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/overview.html?lang=ja)を参照するか、製品管理者に問い合わせて必要な権限を取得してください。

| カテゴリ | 権限 |
|--|--|
| 宛先 | データセット宛先の管理とアクティブ化 |
| データ管理 | データセットの表示 |
| 宛先 | 宛先の表示 |

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
   >Adobe Journey Optimizer をリアルタイム顧客プロファイルと共に使用している場合、宛先カードに「アクティベート」ボタンが表示され、有効にした権限に応じて、データセットの書き出しとこの宛先に対するオーディエンスのアクティブ化の両方が可能になります。

1. 選択した宛先に書き出す&#x200B;**データセットを選択**&#x200B;します。[書き出しに使用できるJourney Optimizerデータセットの詳細を説明します](#datasets)

   <!--![](assets/dataset-export-dataset-selection.png)-->

1. データセットの&#x200B;**書き出しをスケジュール**&#x200B;します。書き出しを開始するタイミングと実行する頻度を指定します。

   <!--![](assets/dataset-export-schedule.png)-->

1. 設定の最後に表示される概要を確認して、**書き出しをレビューして確認**&#x200B;します。

   <!--![](assets/dataset-export-review.png)-->

書き出しが完了すると、設定したスケジュールに従って、データセットの内容がクラウドストレージの場所に保存されます。[データセットの書き出しが成功したことを確認する方法については、こちらを参照してください](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja#verify)
