---
solution: Journey Optimizer
product: journey optimizer
title: サンドボックス間での Journey Optimizer オブジェクトのコピー
description: サンドボックス間でジャーニー、コンテンツテンプレートおよびフラグメントをコピーする方法について説明します。
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer, Data Engineer
level: Experienced
keywords: サンドボックス, ジャーニー, コピー, 環境
exl-id: 356d56a5-9a90-4eba-9875-c7ba96967da9
source-git-commit: 4aaef970b76002c72e3c28f55078d96fdc3cd882
workflow-type: ht
source-wordcount: '1450'
ht-degree: 100%

---

# 別のサンドボックスへのオブジェクトのエクスポート {#copy-to-sandbox}

パッケージのエクスポート機能とインポート機能を使用して、複数のサンドボックス間でジャーニー、カスタムアクション、コンテンツテンプレート、フラグメントなどのオブジェクトをコピーできます。パッケージは、1 つのオブジェクトまたは複数のオブジェクトで構成できます。パッケージに含まれるオブジェクトは、同じサンドボックスからのものである必要があります。

このページでは、Journey Optimizer のコンテキストにおけるサンドボックスツールのユースケースについて説明します。機能自体について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html?lang=ja)を参照してください。

>[!NOTE]
>
>この機能には、**サンドボックス管理**&#x200B;機能の権限（サンドボックスの管理（またはサンドボックスの表示）とパッケージの管理）が必要です。[詳細情報](../administration/ootb-permissions.md)

コピープロセスは、ソースサンドボックスとターゲットサンドボックス間のパッケージの書き出しおよび読み込みを介して実行されます。1 つのサンドボックスから別のサンドボックスにジャーニーをコピーする一般的な手順を以下に示します。

1. パッケージとして書き出すオブジェクトをソースサンドボックスに追加します。
1. パッケージをターゲットサンドボックスに書き出します。

## エクスポートしたオブジェクトとベストプラクティス {#objects}

Journey Optimizer では、ジャーニー、カスタムアクション、コンテンツテンプレートおよびフラグメントを別のサンドボックスにエクスポートすることができます。次の節では、各タイプのオブジェクトに関する情報とベストプラクティスについて説明します。

### 一般的なベストプラクティス {#global}

* オブジェクトをコピーすると、依存関係（ネストされたフラグメント、ジャーニーオーディエンス、アクションなど）が親オブジェクトで正しく更新され、ターゲットサンドボックスに適切にマッピングされます。

* 書き出したオブジェクトにプロファイルのパーソナライゼーションが含まれている場合は、パーソナライゼーションの問題を回避するのに、適切なスキーマがターゲットサンドボックスに存在することを確認します。

* ランディングページは現在、サンドボックス間の移行ではサポートされていません。ジャーニーを別のサンドボックスにコピーすると、ジャーニーまたはメールコンテンツ内のランディングページへの参照は、引き続き元の（ソース）サンドボックスランディングページ ID を指します。移行後、ターゲット（宛先）サンドボックスの正しいランディングページ ID を使用するには、ジャーニーとメールコンテンツ内のすべてのランディングページ参照を手動で更新する必要があります。[ランディングページの作成と公開](../landing-pages/create-lp.md)を参照してください。


### ジャーニー {#journeys}

* ジャーニーをエクスポートすると、Journey Optimizer では、ジャーニー自体に加えて、ジャーニーに必要なほとんどのオブジェクト（オーディエンス、カスタムアクション、スキーマ、イベントおよびアクション）もコピーします。コピーされたオブジェクトについて詳しくは、この[節](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html?lang=ja#abobe-journey-optimizer-objects)を参照してください。

* リンクされたすべての要素が宛先サンドボックスにコピーされるとは限りません。例えば、ジャーニーを公開する前に、徹底的に確認することを強くお勧めします。これにより、欠けている可能性のあるオブジェクトを特定できます。

* ターゲットサンドボックスにコピーされたオブジェクトは一意で、既存の要素が上書きされるリスクはありません。ジャーニーとジャーニー内のあらゆるメッセージは、両方ともドラフトモードで引き継がれます。これにより、ターゲットサンドボックスで公開する前に、徹底的な検証を実行できます。

* コピープロセスでは、ジャーニーとそのジャーニー内のオブジェクトに関するメタデータのみをコピーします。プロファイルまたはデータセットのデータは、このプロセスの一環としてコピーされません。

### カスタムアクション {#custom-actions}

* カスタムアクションをエクスポートすると、URL 設定とペイロードパラメーターがコピーされます。ただし、セキュリティ上の理由から、認証パラメーターはコピーされず、「INSERT SECRET HERE」に置き換えられます。また、定数リクエストヘッダーとクエリパラメーター値も「INSERT SECRET HERE」に置き換えられます。

  これには、特別な目的のカスタムアクション（[!DNL Adobe Campaign Standard]、[!DNL Campaign Classic]、[!DNL Marketo Engage]）が含まれます。

* ジャーニーを別のサンドボックスにコピーする際に、インポートプロセス中にカスタムアクションに対して「既存を使用」を選択した場合、選択する既存のカスタムアクションはソースカスタムアクションと同じにする必要があります（例：同じ設定、パラメーターなど）。それ以外の場合は、新しいジャーニーのコピーにキャンバスで解決できないエラーが発生します。

### キャンペーン {#campaigns}

キャンペーンは、プロファイル、オーディエンス、スキーマ、インラインメッセージおよび依存オブジェクトに関連するすべての項目と共にコピーされます。ただし、次の項目はコピーされ&#x200B;**ません**。

* 多言語バリアントと言語設定、
* ビジネスルール、
* タグ、
* データ使用のラベル付けと適用（DULE）ラベル。

キャンペーンをコピーする際は、誤った設定を回避するために、以下にリストされているオブジェクトがターゲットサンドボックスで検証されていることを確認します。

* **チャネル設定**：チャネル設定は、キャンペーンと共にコピーされます。キャンペーンをコピーしたら、ターゲットサンドボックスでチャネル設定を手動で選択する必要があります。
* **実験のバリアントと設定**：実験のバリアントと設定は、キャンペーンのコピープロセスに含まれます。インポート後、ターゲットサンドボックスでこれらの設定を検証します。
* **統合決定**：決定ポリシーと決定項目は、エクスポートとインポートでサポートされています。決定関連の依存関係がターゲットサンドボックスで正しくマッピングされていることを確認します。

### コンテンツテンプレート {#content-templates}

* コンテンツテンプレートを書き出す際、ネストされたすべてのフラグメントも一緒にコピーされます。

* コンテンツテンプレートを書き出すと、フラグメントが重複する場合があります。例えば、2 つのテンプレートが同じフラグメントを共有し、別々のパッケージにコピーされた場合、両方のテンプレートはターゲットサンドボックスで同じフラグメントを再利用する必要があります。重複を回避するには、読み込みプロセス中に「既存のものを使用」オプションを選択します。[詳しくは、パッケージの読み込み方法を参照してください。](#import)

* 重複をさらに回避するには、コンテンツテンプレートを 1 つのパッケージで書き出すことをお勧めします。こうすることで、システムでは重複排除を効率的に管理できます。

### 決定 {#decisioning}

* 決定オブジェクトをコピーする前に、以下のオブジェクトが宛先サンドボックスに存在している必要があります。

   * 決定オブジェクト全体で使用されるプロファイル属性、
   * カスタムオファー属性のフィールドグループ、
   * ルール、ランキングまたはキャップをまたいだコンテキスト属性に使用されるデータストリームのスキーマ。

* AI モデルを使用したランキング式のサンドボックスコピーは、現在サポートされていません。

* 決定エンティティをコピーする際は、他のオブジェクトの&#x200B;**前**&#x200B;に決定項目をコピーします。例えば、最初にコレクションをコピーし、新しいサンドボックスにオファーがない場合、その新しいコレクションは空のままになります。

### フラグメント {#fragments}

* フラグメントには、ライブ、ドラフト、ドラフトが進行中のライブなど、複数のステータスがあります。フラグメントを書き出す際、最新のドラフト状態がターゲットサンドボックスにコピーされます。

* フラグメントを書き出す際、ネストされたすべてのフラグメントも一緒にコピーされます。

## パッケージとしてのオブジェクトの追加{#export}

オブジェクトを別のサンドボックスにコピーするには、まずオブジェクトをパッケージとしてソースサンドボックスに追加する必要があります。次の手順に従います。

1. ジャーニーリストなど、コピーする最初のオブジェクトが保存されているインベントリに移動します。**その他のアクション**&#x200B;アイコン（オブジェクト名の横にある 3 つのドット）をクリックし、「**パッケージに追加**」をクリックします。

   ![](assets/journey-sandbox1.png)

1. **パッケージに追加**&#x200B;ウィンドウで、オブジェクトを既存のパッケージに追加するか、新しいパッケージを作成するかを選択します。

   ![](assets/journey-sandbox2.png)

   * **既存のパッケージ**：ドロップダウンメニューからパッケージを選択します。
   * **新しいパッケージを作成**：パッケージ名を入力します。説明を追加することもできます。

1. これらの手順を繰り返して、パッケージと共に書き出すすべてのオブジェクトを追加します。

>[!NOTE]
>
>ジャーニーの書き出しでは、Journey Optimizer では、ジャーニー自体に加えて、ジャーニーに必要なほとんどのオブジェクト（オーディエンス、スキーマ、イベントおよびアクション）もコピーします。ジャーニーの書き出しについて詳しくは、[この節](../building-journeys/copy-to-sandbox.md)を参照してください。

## 書き出すパッケージの公開 {#publish}

パッケージを書き出す準備が整ったら、次の手順に従って公開します。

1. **[!UICONTROL 管理]**／**[!UICONTROL サンドボックス]**&#x200B;メニューに移動し、「**パッケージ**」タブを選択します。

1. 書き出すパッケージを開き、書き出すオブジェクトを選択して、「**公開**」をクリックします。

   この例では、ジャーニー、コンテンツテンプレートおよびフラグメントを書き出します。

   ![](assets/journey-sandbox4.png)

1. 「**[!UICONTROL ジョブ]**」タブからパッケージの公開ステータスを追跡します。ジョブについて詳しくは、リストからジョブを選択し、「**[!UICONTROL 読み込みの詳細を表示]**」ボタンをクリックします。

   ![](assets/journey-sandbox9.png)

## ターゲットサンドボックスへのパッケージの読み込み {#import}

パッケージを公開したら、ターゲットサンドボックスに読み込む必要があります。次の手順に従います。

1. **[!UICONTROL サンドボックス]**&#x200B;メニューに移動し、「**[!UICONTROL 参照]**」タブを選択します。

1. パッケージを読み込むサンドボックスを検索し、名前の横にある「+」アイコンをクリックします。

   ![](assets/journey-sandbox5.png)

   >[!NOTE]
   >
   >組織内のサンドボックスのみ使用できます。

1. 「**ターゲットサンドボックス**」フィールドで、正しいターゲットサンドボックスが選択されていることを確認し、**[!UICONTROL パッケージ名]**&#x200B;ドロップダウンリストから読み込むパッケージを選択します。「**次へ**」をクリックします。

   ![](assets/journey-sandbox6.png)

1. パッケージオブジェクトと依存関係を確認します。これは、パッケージに追加したオブジェクトと、オーディエンス、スキーマ、イベント、アクションなど、ジャーニーが依存するその他のオブジェクトのリストです。

   各オブジェクトに対して、新しいオブジェクトを作成するか、ターゲットサンドボックス内の既存のオブジェクトを使用するかを選択できます。これにより、例えば、共通のフラグメントを使用してコンテンツテンプレートを読み込む際に発生する場合があるフラグメントの重複を回避できます。

   ![](assets/journey-sandbox7.png)

1. 右上隅の「**終了**」ボタンをクリックして、ターゲットサンドボックスへのパッケージのコピーを開始します。コピー処理は、オブジェクトの複雑さや、コピーする必要のあるオブジェクトの数によって異なります。

1. 読み込みジョブをクリックして、コピー結果を確認します。

   * 「**読み込み済みオブジェクトを表示**」ボタンをクリックし、コピーした個々のオブジェクトを表示します。
   * 「**読み込みの詳細を表示**」ボタンをクリックして、各オブジェクトの読み込み結果を確認します。

   ![](assets/journey-sandbox8.png)

1. ターゲットサンドボックスにアクセスし、コピーしたすべてのオブジェクトを徹底的に確認します。
