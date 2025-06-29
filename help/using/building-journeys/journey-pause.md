---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーを一時停止
description: ライブジャーニーを一時停止および再開する方法について説明します
feature: Journeys
role: User
level: Intermediate
badge: label="限定提供" type="Informative"
keywords: 公開, ジャーニー, ライブ, 有効性, 確認
exl-id: a2892f0a-5407-497c-97af-927de81055ac
source-git-commit: fa46397b87ae3a81cd016d95afd3e09bb002cfaa
workflow-type: tm+mt
source-wordcount: '2106'
ht-degree: 34%

---

# ジャーニーを一時停止 {#journey-pause}

>[!CONTEXTUALHELP]
>id="ajo_journey_pause"
>title="ジャーニーの一時停止"
>abstract="新しいプロファイルがエントリしないように、ライブジャーニーを一時停止します。ジャーニー内の現在のプロファイルを破棄するか、そのまま保持するかを選択します。保持した場合は、ジャーニーを再開すると、次のアクションアクティビティで実行が再開されます。進行状況を失うことなく、アップデートや緊急停止を行うのに最適です。"

いつでもライブジャーニーを一時停止し、必要なすべての変更を実行して、再開できます。<!--You can choose whether the journey is resumed at the end of the pause period, or whether it stops completely. -->一時停止中に、[グローバルフィルターを適用](#journey-global-filters)して、属性に基づいてプロファイルを除外できます。ジャーニーは、一時停止期間の終了時に自動的に再開されます。また、[手動で再開](#journey-resume-steps)することもできます。

>[!AVAILABILITY]
>
>この機能は、一連の組織でのみ使用でき（限定提供）、今後のリリースでグローバルにロールアウトされる予定です。


## 主なメリット {#journey-pause-benefits}

ジャーニーの一時停止と再開により、顧客体験を中断することなくライブジャーニーを一時的に中断できるので、ジャーニー実務担当者はより優れた制御と柔軟性を得ることができます。一時停止すると、通信は送信されず、ジャーニーが再開されるまでプロファイルは中断状態のままになります。

この機能により、エラーや更新（例：メッセージコンテンツの変更）中に意図しないメッセージを送信するリスクが軽減され、より安全なジャーニー管理がサポートされ、実務担当者の信頼性が向上します。一時停止したジャーニーとそのステータスを UI で直接確認できるので、透明性と運用の俊敏性がさらに向上します。

>[!CAUTION]
>
>* ジャーニーを一時停止および再開する権限は、**[!DNL Publish journeys]** の高レベル権限を持つユーザーに制限されます。[!DNL Journey Optimizer] ユーザーのアクセス権の管理について詳しくは、[この節](../administration/permissions-overview.md)を参照してください。
>
>* 一時停止/再開機能の使用を開始する前に、[ ガードレールと制限事項を参照 ](#journey-pause-guardrails) してください。


## ジャーニーを一時停止する方法 {#journey-pause-steps}

任意の&#x200B;**ライブ**&#x200B;ジャーニーを一時停止できます。

ジャーニーを一時停止するには、次の手順に従います。

1. 一時停止するジャーニーを開きます。
1. ジャーニーキャンバスの右上のセクションにある「**...その他**」ボタンをクリックし、「**一時停止**」を選択します。

   ![「ジャーニーを一時停止」ボタン](assets/pause-journey-button.png)

1. ジャーニーに現在あるプロファイルの管理方法を選択します。

   ![「ジャーニーを一時停止」オプション](assets/pause-confirm.png){width="50%" align="left"}

   実行できる操作は、次のとおりです。

   * **保留** プロファイル – プロファイルは、ジャーニーが再開されるまで、次の **アクション** ノードで待機します
   * **破棄** プロファイル – プロファイルは、次の **アクション** ノードでジャーニーから除外されます

1. 「**一時停止**」ボタンをクリックして、確定します。

ジャーニーのリストから、1 つまたは複数の&#x200B;**ライブ**&#x200B;ジャーニーを一時停止できます。ジャーニーのグループを一時停止（_一括一時停止_）するには、リストでジャーニーを選択し、画面下部の青いバーにある「**一時停止**」ボタンをクリックします。「**一時停止**」ボタンは、**ライブ**&#x200B;ジャーニーを選択した場合にのみ使用できます。

![下部のバーから 2 つのライブジャーニーを一括で一時停止する](assets/bulk-pause-journeys.png)

### 一時停止したジャーニーの動作

ジャーニーが一時停止すると、保留/破棄モードに関係なく、新しいエントリは常に破棄されます。

ジャーニーの一時停止時、プロファイル管理とアクティビティの実行は、アクティビティによって異なります。 動作について詳しくは、以下を参照してください。 詳しくは、この [ エンドツーエンドのサンプル ](#journey-pause-sample) も参照してください。


| ジャーニーアクティビティ | ジャーニーが一時停止している場合 |
|-------------------------|--------------------------------------------------|
| [ オーディエンスの選定 ](audience-qualification-events.md) | <ul> <li>キャンバスの最初のノードで：オーディエンスに対するプロファイルの選定は破棄されます </li><li>他のノードの場合：ライブジャーニーの場合と同じ動作ですが、オーディエンスの選定が <strong> アクション </strong> アクティビティの後にあり、ユーザーがそのアクションで一時停止した場合、オーディエンスの選定は破棄されます。 </li></ul> |
| [ 単一イベント ](general-events.md) | <ul> <li>キャンバスの最初のノードで：イベントは破棄されます</li><li>他のノードの場合：ライブジャーニーの場合と同じ動作ですが、イベントが <strong> アクション </strong> アクティビティの後にあり、ユーザーがそのアクションで一時停止した場合、イベントは破棄されます。 </li></ul> |
| [ オーディエンスを読み取り ](read-audience.md) | ライブジャーニーと同じ動作ですが、特異性がいくつかあります。 <ol> <li> <strong> オーディエンスを読み取り </strong> アクティビティが開始された後に <strong> 一時停止 </strong> が押された場合、ジャーニーにエントリしたプロファイルは（次の <strong> アクション </strong> アクティビティまで）続行します。 ジャーニーが一定の速度でオーディエンスを読み取る際、オーディエンス全体がまだエントリしていない場合、キュー内の残りのプロファイルは破棄されます。</li><li> 1 回実行の場合：スケジュールされた日付が再開日より前の場合、再開時にエラーは表示されません。 そのスケジュールは無視されます。</li><li>増分ジャーニーの場合： <ul><li>最初の発生前に一時停止が発生した場合は、再開時にオーディエンス全体が再生されます。 </li><li>例えば、一時停止が毎日の繰り返しの 4 日目に発生した場合、ジャーニーは 9 日目まで一時停止されたままになり、再開時には 4 日から 9 日までにエントリしたすべてのプロファイルが含まれます  </li></ul></ol> |
| [ 反応 ](reaction-events.md) | ライブジャーニーの場合と同じ動作ですが、反応が <strong> アクション </strong> アクティビティの後にあり、そのアクションでユーザーを一時停止した場合、反応イベントは破棄されます。 |
| [待機](wait-activity.md) | ライブジャーニーと同じ動作 |
| [条件](condition-activity.md) | ライブジャーニーと同じ動作 |
| [ コンテンツの決定 ](content-decision.md) | ジャーニーが一時停止された際にユーザーが選択した内容に基づいて、プロファイルがパークまたは破棄されます |
| [ チャネルアクション ](journeys-message.md) | ジャーニーが一時停止された際にユーザーが選択した内容に基づいて、プロファイルがパークまたは破棄されます |
| [ カスタムアクション ](../action/action.md) | ジャーニーが一時停止された際にユーザーが選択した内容に基づいて、プロファイルがパークまたは破棄されます |
| [ プロファイルを更新 ](update-profiles.md) &amp; [ ジャンプ ](jump.md) | ライブジャーニーと同じ動作 |
| [ 外部データのSource](../datasource/external-data-sources.md) | ライブジャーニーと同じ動作 |
| [ 終了条件 ](journey-properties.md#exit-criteria) | ライブジャーニーと同じ動作 |

## 一時停止したジャーニーを再開する方法 {#journey-resume-steps}

>[!CONTEXTUALHELP]
>id="ajo_journey_resume"
>title="ジャーニーの再開"
>abstract="新しいプロファイルが再度エントリできるように、一時停止したジャーニーを再開します。プロファイルが一時停止中に待機していた場合、ジャーニーは続行されます。アップデートや一時停止後にジャーニーを安全に再開するのに最適です。"

一時停止したジャーニーは、14 日間の最大一時停止期間の終了時に自動的に再開されます。いつでも手動で再開できます。 一時停止したジャーニーを再開すると、新しいプロファイルを再び入力できます。 プロファイルが一時停止中に待機していた場合、ジャーニーは続行されます。アップデートや一時停止後にジャーニーを安全に再開するのに最適です。

一時停止したジャーニーを再開し、ジャーニーイベントのリッスンを再開するには、次の手順に従います。

1. 再開するジャーニーを開きます。
1. ジャーニーキャンバスの右上のセクションにある「**...その他**」ボタンを選択し、「**再開** を選択します。

   ジャーニーは「**再開中**」ステータスに切り替わります。ジャーニーが再開されると、1 分以内に新しいエントリが開始されます。 保持されたプロファイルの再開には時間がかかる場合があります – プロファイルは 5k tps の速度で再開されます。  ジャーニーを再度 **ライブ** にするには、すべてのプロファイルを再開する必要があるので、**再開中** ステータスから **ライブ** ステータスへの移行に時間がかかることがあります。

1. 「**再開**」ボタンをクリックして、確定します。


ジャーニーのリストから、1 つまたは複数の「**一時停止**」されているジャーニーを再開できます。ジャーニーのグループを再開（_一括再開_）するには、ジャーニーを選択し、画面下部の青いバーにある「**再開**」ボタンをクリックします。「**再開**」ボタンは、**一時停止した**&#x200B;ジャーニーを選択した場合にのみ使用できます。


## 一時停止したジャーニーのプロファイルへのグローバルフィルターの適用 {#journey-global-filters}

ジャーニーを一時停止した場合、プロファイル属性に基づいてグローバルフィルターを適用できます。このフィルターを使用すると、再開時に、定義済みの式に一致するプロファイルを除外できます。グローバルフィルターが設定されると、新しいプロファイルエントリに対しても、アクションノードで適用されます。 条件に一致する既存のプロファイルと、ジャーニーにエントリする新しいプロファイルは、発生した **次のアクションノードで** ジャーニーから除外されます。

例えば、一時停止したジャーニーからすべてのフランス人の顧客を除外するには、次の手順に従います。

1. 変更する一時停止したジャーニーを参照します。

1. **終了条件とグローバルフィルター** アイコンを選択します。

   ![一時停止したジャーニーへのグローバルフィルターの追加](assets/add-global-filter.png)

1. **終了条件とグローバルフィルター** 設定で「**グローバルフィルターを追加**」をクリックし、プロファイル属性に基づいてフィルターを定義します。

1. 式を設定して、国属性が「フランス」のプロファイルを除外します。

   ![一時停止したジャーニーへのグローバルフィルターの追加](assets/add-country-filter.png)

1. フィルターを保存し、「**ジャーニーを更新**」ボタンをクリックして変更を適用します。

1. [ジャーニーを再開します](#journey-resume-steps)。

   再開時に、国属性がフランスに設定されたすべてのプロファイルは、次のアクションノードでジャーニーから自動的に除外されます。 ジャーニーへのエントリを試みる際、国属性がフランスに設定された新しいプロファイルは、次のアクションノードでもブロックされます。

現在ジャーニー内にあるプロファイルと新しいプロファイルのプロファイル除外は、アクションノードに到達した場合にのみ発生します。

>[!CAUTION]
>
>* ジャーニーごとに設定できるグローバルフィルターは **1 つ**&#x200B;のみです。
>
>* **一時停止した**&#x200B;ジャーニーでは、グローバルフィルターの作成、更新、削除のみ行うことができます。

## ガードレールと制限 {#journey-pause-guardrails}

* ジャーニーのバージョンは最大 **14 日間** 一時停止でき、最大 **1,000 万のプロファイルが** 組織全体の一時停止されたジャーニーで許可されます。
この制限は 30 分ごとにチェックされます。 つまり、一時的に 1,000 万のしきい値を超える可能性がありますが、システムが検出すると、追加のプロファイルは自動的に破棄されます。

  ジャーニーを再開して、保持しているプロファイルの数が制限を下回った場合、ジャーニーは直ちに再開されます。ただし、プロファイル数が更新されるまで最大 30 分かかる場合があります。 その間、システムは、引き続きこれらのプロファイルを一時停止と見なします。

* 一時停止したジャーニーは、ライブジャーニーの割り当てにカウントされます
* ジャーニーにエントリしたが、一時停止中に破棄されたプロファイルは、引き続きエンゲージメント可能なプロファイルとしてカウントされます
* 一時停止されたジャーニーは、すべてのビジネスルールで、ライブの場合と同様に考慮されます
* ジャーニーのグローバルタイムアウトは、一時停止したジャーニーに引き続き適用されます。例えば、プロファイルが 90 日間ジャーニーにあり、ジャーニーを一時停止した場合、このプロファイルは 91 日目にジャーニーを終了します
* プロファイルは、アクションアクティビティに到達すると、一時停止されたジャーニーで **破棄** されます。 ジャーニーの一時停止中に待機し、再開後に待機を終了した場合、ジャーニーは続行され、破棄されません。 [ エンドツーエンドのサンプルを参照 ](#journey-pause-sample)
* 一時停止した後もイベントが処理され続けると、これらのイベントは 1 秒あたりのジャーニーイベント数の割り当てにカウントされ、その後にスロットルが単一イベントとして認識されます
* プロファイルを一時停止したジャーニーで保持すると、再開時にプロファイル属性が更新されます
* 条件は一時停止したジャーニーでも実行されるので、データ品質の問題でジャーニーが一時停止されている場合、アクションノード前の条件を誤ったデータで評価できます
* 増分オーディエンスベースの **オーディエンスを読み取り** ジャーニーの場合、一時停止された時間が考慮されます。 これは、オーディエンスの選定またはイベントベースのジャーニーには当てはまりません（オーディエンスの選定またはイベントを一時停止中に受け取り、ジャーニーの最初のアクティビティの場合、それらのイベントは破棄されます）
* プロファイルをジャーニーで保持し、このジャーニーを数日後に自動的に再開する場合、プロファイルはジャーニーを続行し、ドロップされません。ドロップする場合は、ジャーニーを停止する必要があります
* 一時停止したジャーニーで、次のアラートが発生しません [ バッチセグメントアラート ](../reports/alerts.md#alert-read-audiences)
* ジャーニーの 14 日間一時停止状態が終了すると、システムに監査ログが残りません
* 破棄されたプロファイルの中には、ジャーニーステップイベントには表示できても、レポートには表示されないものもあります。 例：
   * **オーディエンスを読み取り** のビジネスイベントを破棄
   * **オーディエンスを読み取り** ジャーニーの一時停止が原因でジョブが削除される
   * **イベント** アクティビティが、プロファイルが待機しているアクションの後にあった場合に破棄されたイベント
     <!--* There is a guardrail (at an org level) on the max number of profiles that can be held in paused journeys. This guardrail is per org, and is visible in the journey inventory on a new bar (only visible when there are paused journeys).-->

## エンドツーエンドのサンプル {#journey-pause-sample}

次のジャーニーの例を見てみましょう。

![ ジャーニーの例 ](assets/pause-journey-sample.png){zoomable="yes"}

このジャーニーを一時停止する場合、プロファイルを **破棄** するか **保持** するかを選択すると、プロファイル管理は次のようになります。

1. **AddToCart** アクティビティ：すべての新しいプロファイルのエントリがブロックされます。 プロファイルが一時停止の前に既にジャーニーにエントリしている場合、プロファイルは次のアクションノードに進みます。
1. **待機** アクティビティ：ジャーニーが一時停止している場合でも、プロファイルは引き続きノードで通常どおりに待機し、ノードから終了します。
1. **条件**：プロファイルは、引き続き条件を通過し、条件に定義された式に基づいて右側の分岐に移動します。
1. **プッシュ**/**メール** アクティビティ：一時停止したジャーニー中、プロファイルは待機を開始するか、次のアクションノードで（一時停止時のユーザーの選択に基づいて）破棄されます。 そのため、プロファイルはそこで待機を開始するか、破棄されます。
1. **アクション** ノードの後の **イベント**：プロファイルが **アクション** ノードを待機していて、その後に **イベント** アクティビティがある場合、そのイベントが発生すると、プロファイルは破棄されます。

この動作に従って、ジャーニーの一時停止に伴い、ほとんどの場合、**アクション** アクティビティの前のアクティビティでプロファイル番号が増加していることがわかります。 例えば、この例では、「**待機**」アクティビティは引き続き有効のままなので、「**条件**」アクティビティを終了するプロファイルの数が増えます。

このジャーニーを再開した場合：

1. 1 分以内に新しいジャーニーのエントリが開始されます。
1. **アクション** アクティビティのジャーニーで現在待機しているプロファイルは、5,000 件の TPS 率で再開されます。 その後、待機していた **アクション** に入り、ジャーニーを続行できます。
