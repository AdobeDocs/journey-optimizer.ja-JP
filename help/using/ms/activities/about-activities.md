---
solution: Journey Optimizer
product: journey optimizer
title: 複数ステップのキャンペーンアクティビティの操作
description: 複数の手順から成るキャンペーンアクティビティの作成方法を学ぶ
hide: true
hidefromtoc: true
exl-id: 02f986b2-8200-4e0e-8918-44e528a6a3ec
source-git-commit: 323472ef9d6203cbbadc44ceb17ddcc7f6207323
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 59%

---

# マルチステップキャンペーンアクティビティについて {#ms-campaign-activities}

複数の手順からなるキャンペーンアクティビティは、3 つのカテゴリにグループ化されます。 使用可能なアクティビティは、コンテキストに応じて異なる場合があります。

すべてのアクティビティについて、以下の節で詳しく説明します。

* [ターゲティングとデータ管理アクティビティ](#targeting)
* [チャネルアクティビティ](#channel)
* [フロー制御アクティビティ](#flow-control)

![](../assets/workflow-activities.png)

## ターゲティングアクティビティ {#targeting}

これらのアクティビティは、ターゲティングに固有です。オーディエンスを定義するか、積集合、和集合、除外の各操作を使用して分割または結合することで、1 つまたは複数のターゲットを作成できます。

* [オーディエンスを作成](build-audience.md)：ターゲット母集団を定義します。既存のオーディエンスを選択するか、クエリモデラーを使用して独自のクエリを定義できます。
* [ ディメンションの変更 ](change-dimension.md)：複数手順キャンペーンを作成する際に、ターゲティングディメンションを変更します。
* [結合](combine.md)：インバウンド母集団に対してセグメント化を実行します。和集合、積集合または除外を使用できます。
* [重複排除 - 重複](deduplication.md)：インバウンドアクティビティの結果から重複を削除します。
* [ エンリッチメント ](enrichment.md)：複数ステップのキャンペーンで処理する追加データを定義します。 このアクティビティでは、インバウンドトランジションを利用し、追加データを活用して出力トランジションを補完するようにアクティビティを設定できます。
* [ 紐付け ](reconciliation.md):Journey Optimizer データのデータと作業用テーブル内のデータの間のリンクを定義します（外部ファイルから読み込まれたデータなど）。
* [ オーディエンスを保存 ](save-audience.md)：複数手順のキャンペーンで、アップストリームで計算された母集団から既存のオーディエンスを更新するか、新しいオーディエンスを作成します。
* [分割](split.md)：入力母集団を複数のサブセットにセグメント化します。

## データ管理アクティビティ {#data}

これらのアクティビティは、母集団データの操作およびエンリッチメントに固有です。

* [ファイルを読み込み](load-file.md)：外部ファイルに保存されたプロファイルとデータを操作します。
* [データを更新](update-data.md)：データベースのフィールドに対して一括更新を実行します。データ更新は、いくつかのオプションを使用してパーソナライズすることができます。

## チャネルアクティビティ {#channel}

Adobe Journey Optimizerを使用すると、複数のチャネルをまたいでマーケティングキャンペーンを自動化および実行できます。 チャネルアクティビティをキャンバスに組み合わせて、顧客の行動に基づいてアクションをトリガーにできるクロスチャネルのマルチステップキャンペーンを作成できます。 メール、SMS、Android および iOS プッシュ通知の&#x200B;**チャネル**&#x200B;アクティビティが使用可能です。[ 複数手順キャンペーンのコンテキストで配信を設定する方法を説明します ](channels.md)。

## フロー制御アクティビティ {#flow-control}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_end"
>title="終了アクティビティ"
>abstract="**終了**&#x200B;アクティビティを使用すると、マルチステップキャンペーンの終了をグラフィカルにマークできます。このアクティビティは、機能上の影響はないので、省略可能です。"

次のアクティビティは、複数手順のキャンペーンの整理と実行に固有です。 主なタスクは、他のアクティビティの調整です。

* [AND 結合 ](and-join.md)：複数手順キャンペーンの複数の実行分岐を同期します。
* **終了**：複数手順のキャンペーンの終了を視覚的に示します。 このアクティビティは、機能上の影響はないので、省略可能です。
* [分岐](fork.md)：アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始します。
* [ スケジューラー ](scheduler.md)：複数手順のキャンペーンが開始するタイミングをスケジュールします。
* [テスト](test.md)：指定した条件に基づいてトランジションを有効にします。
* [ 待機 ](wait.md)：複数手順キャンペーンの一部の実行を一時的に一時停止します。
