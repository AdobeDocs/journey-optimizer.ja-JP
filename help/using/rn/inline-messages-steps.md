---
title: ジャーニーインラインオーサリングに移行する手順
description: ジャーニーインラインオーサリングに移行する手順
source-git-commit: 3f9844dec9caf520ab59c5f2b433a5c2e86ef44f
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 1%

---


# インラインオーサリングの移行手順{#migration-steps}

Adobe Journey Optimizerでのメッセージのオーサリングの新しいプロセスについては、この節で説明します [ページ](../rn/inline-messages.md). ジャーニーの自動コンバージョンが実行されます。 しかし、いくつかの手順について、皆様のご協力が必要となります。

>[!VIDEO](https://video.tv.adobe.com/v/344699)

主なフェーズと手順を次に示します。

**[移行前](../rn/inline-messages-steps.md#migration-step-1)**

1. 非実稼動用サンドボックスで、ライブジャーニーおよびクローズ済みジャーニーをすべて停止します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-1-1)
1. 実稼動用サンドボックスで、にプロファイルを残さずに、すべてのライブアドホックジャーニーを停止します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-1-2)

**[最初の反復の後](../rn/inline-messages-steps.md#migration-step-2)**

1. 移行したライブジャーニーでエラーが発生していないかを確認します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-1)
1. 移行で作成されたすべての新しいバージョンを一覧表示します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-2)
1. それらを 1 つずつテストして公開します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-3)
1. すべてのライブバージョンをリストします。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-4)
1. ドラフトバージョンの移行時にエラーが表示されます。 [詳細情報](../rn/inline-messages-steps.md#migration-step-2-5)

**[2 番目の反復の後](../rn/inline-messages-steps.md#migration-step-3)**

1. 両方の移行フェーズを確認します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-3-1)
1. 以前のバージョンを停止します。 [詳細情報](../rn/inline-messages-steps.md#migration-step-3-2)

**[3 番目と最後の反復の前](../rn/inline-messages-steps.md#migration-step-4)**

廃止前に、すべてが移行されたことを検証します。

<br> 

## 移行前（7 月 25 日）{#migration-step-1}

### 1.ライブジャーニーおよびクローズ済みジャーニーをすべて停止します。{#migration-step-1-1}

オン **非実稼働用サンドボックス**、ライブジャーニーおよびクローズ済みジャーニーをすべて停止します。 これにより、自動移行プロセスで、ユーザーが何も操作しなくても、これらのサンドボックスからすべてのジャーニーを移行できます。 移行後、停止したジャーニーのバージョンを複製して使用できるようになります。

### 2.内にプロファイルを残さずに、すべてのライブアドホックジャーニーを停止します。{#migration-step-1-2}

の **実稼動サンドボックス**、プロファイルを含まなくなったライブアドホックジャーニーをすべて停止します。

+++これらのジャーニーを見つける方法は？

これらのジャーニーを見つけるには、 **ジャーニー** メニューを開き、「Status = Live」および「Type = Read segment」でリストをフィルタリングします。 また、「公開日」が早い日から遅い日まで、時系列で並べ替えることもできます。

![](assets/inline-migration-steps1.png)

上から下に開きます。

* ジャーニーにメッセージがあることを確認します。
* 繰り返しのジャーニーでないことを確認します。 これらはアドホックではありません。 最も多くの場合は、それらをライブに保ちたいと思います。 例えば、これは繰り返しのジャーニーです（アドホックではありません）。

   ![](assets/inline-migration-steps2.png)

* これらのジャーニーで wait または event リスナーを使用した場合、プロファイルは内部に残っている可能性があります。 ジャーニーの実行日を確認し、待機中またはイベントのリスナーで定義した時間/日を追加して、プロファイルが残っていない実際の日付を推測します。 その日付が過去の日付の場合は、ジャーニーを停止できます。 それ以外の場合、このジャーニーは、ジャーニーの実行日から 30 日後に、自動的に「完了」ステータスに移動します。

+++

**重要な注意事項**

* 移行日（7 月 25 日）より前にジャーニーを閉じないようにします。 移行スクリプトがライブジャーニーやクローズ済みジャーニーを移行しないことを考慮し、実稼働用サンドボックスでクローズ済みジャーニーの数を制限すると、移行後に必要な手動アクションの数が制限されます。

* 最新バージョンではないライブジャーニーがある場合（つまり、別のジャーニーバージョンをドラフトで作成した場合）、公開または削除します。

* ジャーニーで使用されていないメッセージがあり、保持したいメッセージがある場合は、テンプレートとして保存します。 廃止されるまで、引き続きこれらの機能にアクセスできます。

## 最初の移行の後（7 月 25 日）{#migration-step-2}

移行は、次の 2 つの段階でおこなわれます。自動フェーズ（夜間、7 月 25 日～7 月 26 日）と手動フェーズ（7 月 26 日開始）。アクション項目が必要です。

自動化フェーズについては、次を参照してください。 [ページ](../rn/inline-messages.md#process).

手動フェーズでは、次の操作を実行します。 **実稼動サンドボックス**:

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

### 1.移行したライブジャーニーでエラーが発生していないかを確認します{#migration-step-2-1}

自動的に移行されたライブジャーニーに関するエラーがステータスレポートにないかを確認します。

「ERROR_NEW_VERSION_CREATION」を探します。

![](assets/inline-migration-steps6.png)

* エラーがない場合は、移行が必要なすべてのライブジャーニーバージョンが処理され、移行された新しいドラフトバージョンが自動的に作成されたことを意味します。

* エラーが表示された場合は、「errorMessage」を検索し、ログでエラーメッセージを確認できます。 マルチチャネルメッセージは移行されません。 別のジャーニーを作成する必要があります。

* その他のエラーについては、CSM またはAdobe担当者にお問い合わせください。

### 2.移行で作成されたすべての新しいバージョンを一覧表示します{#migration-step-2-2}

これらは、 [移行済み] ジャーニーのラベルと作成日が更新されます。

![](assets/inline-migration-steps7.png)

### 3.テストして 1 つずつ公開する{#migration-step-2-3}

ジャーニーを実稼動で実行する必要があることを確認します。 この [移行前の準備](../rn/inline-messages-steps.md#migration-step-1) が正しく実行されなかった場合は、不要になったワンショットジャーニー用に新しいバージョンを作成できる可能性があります。

インラインチャネルアクションを含むジャーニーの下書きバージョンをテストします。

新しいジャーニーバージョンを公開します。 以前のライブバージョンは、「クローズ済み」ステータスに移行します。

### 4.すべてのライブバージョンをリストする{#migration-step-2-4}

すべて最新としてマークされる必要があります。 そうでない場合は、新しいバージョンを探し、テストして公開します。

![](assets/inline-migration-steps8.png)

### 5.ドラフトバージョンの移行に関するエラーを確認する{#migration-step-2-5}

次をクリック： **ステータスを確認** 」ボタンをクリックし、自動移行中にエラーが発生していないこと、および移行する必要がないことを確認します。 エラーが発生したジャーニー（メッセージを含む）は、9 月 5 日以降（すべてのサンドボックス）に廃止されることに注意してください。

![](assets/inline-migration-steps11.png)

「エラー」ステータスを探します。

![](assets/inline-migration-steps9.png)

* エラーがない場合は、行って良いです。

* エラーがある場合は、「errorMessage」を検索してエラーを探します。 マルチチャネルメッセージの移行はサポートされていないので、次のエラーが発生することが予想されます。「マルチチャネルメッセージの移行はサポートされていません」。 このジャーニーを再構築する必要があります。

![](assets/inline-migration-steps6.png)

## 2 番目の反復（8 月 1 日）以降{#migration-step-3}

2 番目の反復は、8 月 1 日から 8 月 2 日の夜間に行われます。

<!--
_On non-production sandboxes:_

**1. Check at the status report**

Click the **Check status** button in the top banner and check that all journeys have been migrated and there's nothing left to migrate. If there is an error or something left to migrate, please reach out to your CSM or Adobe representative for guidance.

-->

前のすべての手順が時間内に実行された場合、終了したジャーニーとエラーが発生したジャーニーを除き、すべてのジャーニーが移行されています。 以下に、 **実稼動サンドボックス**:

### 1.両方の移行フェーズを確認します。{#migration-step-3-1}

エラーがない場合、「toMigrate」と「createNewVersion」の下の「eligibilityStatus」にジャーニーを設定しないでください。 次の例では、「ERROR」と「ERROR_NEW_VERSION_CREATION」が 1 つあります。

![](assets/inline-migration-steps10.png)

### 2.以前のバージョンを停止する{#migration-step-3-2}

新しいジャーニーバージョンをまだ公開していない場合 ( [セクション](../rn/inline-messages-steps.md#migration-step-2-3)) は、繰り返し 2（8 月 1 日）より前の時間意味で、次に新しいバージョンを公開し、 **以前のバージョンを停止するか、失われます** および関連するレポート。

## 3 番目と最後の反復（9 月 5 日）より前{#migration-step-4}

8 月 1 日～9 月 5 日の間に、すべてが移行され、メッセージを使用するジャーニーがまだ残っていないことを検証する必要があります。そうしない場合は、9 月 5 日に廃止されます。

