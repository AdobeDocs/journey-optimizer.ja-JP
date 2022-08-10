---
title: ジャーニーのインラインオーサリングへの移行手順
description: ジャーニーのインラインオーサリングへの移行手順
exl-id: 8412a0bd-674c-4d6a-aa5b-443655d2943a
source-git-commit: 1ab038e8b2f0582ad947400c7d070a70e1a84b9b
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 100%

---

# インラインオーサリングの移行手順{#migration-steps}

Adobe Journey Optimizer でコンテンツをオーサリングする新しいプロセスについては、この[ページ](../rn/inline-messages.md)で説明します。ジャーニーの自動コンバージョンがおこなわれます。 とは言え、いくつかの手順に関してはユーザーの協力が必要です。

>[!VIDEO](https://video.tv.adobe.com/v/344699)

主なフェーズと手順を次に示します。

**[移行前](../rn/inline-messages-steps.md#migration-step-1)**

1. 非実稼動用サンドボックスで、ライブジャーニーおよびクローズ済みジャーニーをすべて停止します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-1-1)
1. 実稼動用サンドボックスで、プロファイルがもう残っていないすべてのライブアドホックジャーニーを停止します。[詳細情報](../rn/inline-messages-steps.md#migration-step-1-2)

**[最初のイテレーションの後](../rn/inline-messages-steps.md#migration-step-2)**

1. 移行したライブジャーニーでエラーが発生していないかを確認します。[詳細情報](../rn/inline-messages-steps.md#migration-step-2-1)
1. 移行で作成されたすべての新しいバージョンを一覧表示します。[詳細情報](../rn/inline-messages-steps.md#migration-step-2-2)
1. 1 つずつテストして公開します。[詳細情報](../rn/inline-messages-steps.md#migration-step-2-3)
1. すべてのライブバージョンを一覧表示します。[詳細情報](../rn/inline-messages-steps.md#migration-step-2-4)
1. 移行したドラフトバージョンでエラーが発生していないかを確認します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-5)

**[2 回目のイテレーションの後](../rn/inline-messages-steps.md#migration-step-3)**

1. 両方の移行フェーズを確認します。[詳細情報](../rn/inline-messages-steps.md#migration-step-3-1)
1. 以前のバージョンを停止します。[詳細情報](../rn/inline-messages-steps.md#migration-step-3-2)

**[3 回目と最後のイテレーションの前](../rn/inline-messages-steps.md#migration-step-4)**

廃止前に、すべてが移行されたことを検証します。

<br> 

## 移行前（7月25日（PT））{#migration-step-1}

### 1. ライブジャーニーおよびクローズ済みジャーニーをすべて停止する{#migration-step-1-1}

**非実稼動用サンドボックス**&#x200B;で、ライブジャーニーおよびクローズ済みジャーニーをすべて停止します。これにより、自動移行プロセスで、ユーザーが何も操作しなくても、これらのサンドボックスからすべてのジャーニーを移行できます。移行後、停止したジャーニーのバージョンを複製して使用できます。

### 2. プロファイルがまだ残っていないすべてのライブアドホックジャーニーを停止する{#migration-step-1-2}

**実稼動用サンドボックス**&#x200B;で、プロファイルを含まなくなったすべてのライブアドホックジャーニーを停止します。

+++これらのジャーニーを見つける方法は？

これらのジャーニーを見つけるには、**ジャーニー**&#x200B;メニューに移動し、「ステータス = ライブ」および「タイプ = 読み取りセグメント」でリストをフィルタリングします。また、ジャーニーは、最も早い「公開日」から最も遅い「公開日」まで、時系列で並べ替えることもできます。

![](assets/inline-migration-steps1.png)

上から下に開きます。

* ジャーニーにメッセージがあることを確認します。
* 繰り返しのジャーニーでないことを確認します。これらはアドホックではありません。おそらく、ライブのまま保持することを希望されるでしょう。例えば、これは繰り返しのジャーニーです（アドホックではありません）。

   ![](assets/inline-migration-steps2.png)

* これらのジャーニーで待機中またはイベントのリスナーを使用した場合、プロファイルは内部に残っている可能性があります。ジャーニーの実行日を確認し、待機中またはイベントのリスナーで定義した時間/日を追加して、プロファイルが残っていない実際の日付を推測します。その日付が過去の日付の場合は、ジャーニーを停止できます。それ以外の場合、このジャーニーは、ジャーニーの実行日から 30 日後に、自動的に「完了」ステータスに移動します。

+++

**重要な注意事項**

* 移行日（7月25日（PT））より前にジャーニーをクローズしないでください。移行スクリプトがライブジャーニーやクローズ済みジャーニーを移行しないことを考慮し、実稼動用サンドボックスでクローズ済みジャーニーの数を制限すると、移行後に必要な手動アクションの数が制限されます。

* 最新バージョンではないライブジャーニーがある場合（つまり、別のジャーニーバージョンをドラフトで作成した場合）、公開または削除します。

* ジャーニーで使用されていないメッセージがある場合、そのメッセージを保持するには、テンプレートとして保存します。この[ページ](../design/email-templates.md#save-as-template)を参照してください。廃止されるまで、引き続きこれらの機能にアクセスできます。

## 移行の最初のイテレーション後（7月25日（PT））{#migration-step-2}

移行は、自動フェーズ（夜間、7月25日～7月26日（PT））と、アクション国木ｋが必要な手動フェーズ（7月26日（PT））の 2 つの段階でおこなわれます。

自動フェーズについては、この[ページ](../rn/inline-messages.md#process)を参照してください。手動フェーズの場合、**実稼動用サンドボックス**&#x200B;で実行するアクションは次のとおりです。

<!--
_On non-production sandboxes:_

**1. Check the migration status report for any error**

Click the **Check status** button in the top banner and check that there has been no error during the automatic migration and that there is nothing left to migrate. 

![](assets/inline-migration-steps3.png)

Look for the "ERROR" status. 

![](assets/inline-migration-steps4.png)

* If there is no error, you are good to go.
* If there are errors, look for the error by searching "errorMessage". The following error is expected as migration of multi-channel messages is not supported: "Migration of multi-channel messages is not supported". You will have to rebuild this journey.

    ![](assets/inline-migration-steps5.png)

_On the production sandbox:_

-->

### 1. 移行したライブジャーニーでエラーが発生していないかを確認する{#migration-step-2-1}

自動移行したライブジャーニーでエラーが発生していないかをステータスレポートで確認します（[詳細情報](../rn/inline-messages.md#status)）。最上部のバナーにある「**ステータスを確認**」ボタンをクリックします。

![](assets/inline-migration-steps3.png)

「ERROR_NEW_VERSION_CREATION」を探します。

![](assets/inline-migration-steps6.png)

* エラーが発生していない場合は、移行が必要なすべてのライブジャーニーバージョンが処理され、移行した新しいドラフトバージョンが自動的に作成されたことを意味します。

* エラーが表示された場合は、「errorMessage」を検索し、ログでエラーメッセージを確認できます。 マルチチャネルメッセージは移行されません。別のジャーニーを作成する必要があります。

   ![](assets/inline-migration-steps5.png)

* その他のエラーについては、CSM またはアドビ担当者にお問い合わせください。

### 2. 移行で作成されたすべての新しいバージョンを一覧表示する{#migration-step-2-2}

これらは、ジャーニーのラベルで[移行済み]としてマークされ、作成日が更新されます。

![](assets/inline-migration-steps7.png)

### 3. 1 つずつテストして公開する{#migration-step-2-3}

まだ実稼動環境でジャーニーを実行する必要があることを確認します。この[移行前の準備](../rn/inline-messages-steps.md#migration-step-1)が正しく実行されなかった場合は、不要になったワンショットジャーニー用に新しいバージョンを作成できる可能性があります。

インラインチャネルアクションを含むジャーニーのドラフトバージョンをテストします。

新しいジャーニーバージョンを公開します。その後、以前のライブバージョンは「クローズ済み」ステータスに移動します。

### 4. すべてのライブバージョンを一覧表示する{#migration-step-2-4}

すべて最新としてマークする必要があります。そうでない場合は、新しいバージョンを探し、テストして公開します。

![](assets/inline-migration-steps8.png)

### 5. 移行したドラフトバージョンでエラーが発生していないかを確認する {#migration-step-2-5}

最上部のバナーにある「**ステータスを確認**」ボタンをクリックし（[詳細情報](../rn/inline-messages.md#status)）、自動移行中にエラーが発生していないことと、移行するものが残っていないことを確認します。エラーが発生した（メッセージを含む）ジャーニーは、9月5日（PT）以降（すべてのサンドボックスで）廃止されることに注意してください。

![](assets/inline-migration-steps11.png)

「エラー」ステータスを探します。

![](assets/inline-migration-steps9.png)

* エラーが発生していない場合は、問題ありません。

* エラーが発生している場合は、「errorMessage」を検索してエラーを探します。 マルチチャネルメッセージの移行はサポートされていないので、「マルチチャネルメッセージの移行はサポートされていません」というエラーが発生することが予想されます。このジャーニーを再構築する必要があります。

![](assets/inline-migration-steps5.png)

## 2 回目のイテレーションの後（8月1日（PT））{#migration-step-3}

2 回目のイテレーションは、8月1日から 8月2日にかけて夜間（PT）におこなわれます。

<!--
_On non-production sandboxes:_

**1. Check at the status report**

Click the **Check status** button in the top banner and check that all journeys have been migrated and there's nothing left to migrate. If there is an error or something left to migrate, please reach out to your CSM or Adobe representative for guidance.

-->

前のすべての手順が時間内に実行された場合、クローズ済みジャーニーとエラーが発生したジャーニーを除き、すべてのジャーニーが移行されています。**実稼動用サンドボックス**&#x200B;で実行する手順は次のとおりです。

### 1. 両方の移行フェーズを確認する{#migration-step-3-1}

エラーが発生していない場合、「toMigrate」と「createNewVersion」の下の「eligibilityStatus」にジャーニーを設定しないでください。次の例では、「ERROR」と「ERROR_NEW_VERSION_CREATION」が 1 つあります。

![](assets/inline-migration-steps10.png)

### 2. 以前のバージョンを停止する{#migration-step-3-2}

2 回目のイテレーション（8月1日（PT））の前に新しいジャーニーバージョン（この[節](../rn/inline-messages-steps.md#migration-step-2-3)を参照）を公開していない場合は、新しいバージョンを公開します。

>[!NOTE]
>
>以前のバージョンを停止しないと、そのバージョンと関連するレポートが失われます。

## 3 回目と最後のイテレーションの前（9月5日）{#migration-step-4}

8月1日～9月5日（PT）の間に、すべてが移行され、メッセージを使用するジャーニーがまだ残っていないことを検証する必要があります。そうしない場合は、9月5日（PT）に廃止されます。
