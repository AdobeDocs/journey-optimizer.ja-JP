---
title: ジャーニーインラインオーサリングに移行
description: メッセージの移行方法を説明します。
exl-id: accdebba-5322-401e-8a40-3e1539e65a7e
source-git-commit: 3f9844dec9caf520ab59c5f2b433a5c2e86ef44f
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 5%

---


# インラインオーサリングの移行の概要{#inline-authoring}

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_before"
>title="新しいインラインオーサリングメッセージの詳細を学ぶ"
>abstract="2022 年 7 月 25 日以降、メッセージはジャーニーから直接作成されます。 既存のメッセージは、新しいモデルに自動的に移行されます。移行後には、追加のアクションが必要になります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-messages-steps.html" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_during"
>title="状況を把握する"
>abstract="2022 年 7 月 25 日以降、メッセージはジャーニーから直接作成されます。 お使いの環境を移行中です。移行後には、追加のアクションが必要になります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-messages-steps.html" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_after"
>title="メッセージの移行方法を説明します。"
>abstract="2022 年 7 月 25 日以降、メッセージはジャーニーから直接作成されます。 既存のメッセージは、新しいモデルに移行されました。ジャーニーの実践者は、追加のアクションが必要になりました。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-messages-steps.html" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_depecrated_inventory"
>title="メッセージの移行方法を説明します。"
>abstract="2022 年 7 月 25 日以降、メッセージメニューが表示されなくなり、ジャーニーから直接メッセージが作成されます。 従来のメッセージをジャーニーで再利用する場合は、テンプレートとして保存する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/design/email-templates.html#save-as-template" text="メッセージをテンプレートとして保存"

Adobe Journey Optimizerでは、Journey Optimizerチャネル（E メール、プッシュ、SMS）のコンテンツのオーサリング方法を改善する新機能がリリースされます。 Journey Optimizerの実践者は、ジャーニーから直接メッセージを作成し、作成できるようになりました。

この機能を使用するには、メッセージを使用している既存のジャーニーを移行する必要があります。

このページでは、この変更に関して必要な情報と、ユーザーから必要な手順を確認します。

Journey Optimizerの実践者としての役割と責務の詳細については、 [ページ](../start/path/marketer.md).

<!--
Here are the main changes in the interface:

* Messages are created direcly from journeys.
* The **Messages** entry in the left navigation menu has been removed. 
* There is no separate library of messages, the journey now centralizes all components.


-->

>[!VIDEO](https://video.tv.adobe.com/v/344698)


## 主な留意点{#keys}

* **私は影響を受けていますか？**:メッセージを **メッセージ** メニューを使用して、ジャーニーで使用します。 サードパーティ製システム (Adobe Campaignなど ) を使用している場合、この移行の影響は受けません。

* **製品の変更点**:GA（7 月 25 日）になると、チャネルコンテンツは各ジャーニー内で作成および管理されます。 この **メッセージ** メニューの左側のナビゲーションでは、現在は使用できません ([詳細情報](../rn/inline-messages.md#change)) をクリックします。 既存のジャーニーの移行を続行します。

* **タイムライン**:夜間には、複数の経由で各地域に移行が発生します [繰り返し](../rn/inline-messages.md#iterations).

   ![](assets/inline-migration-timeline.png)

* **必要なアクション**:ジャーニーの自動コンバージョンが実行されます。 しかし、いくつかの手順について、皆様のご協力が必要となります。 このドキュメントで必要な手順の詳細を説明します [ページ](../rn/inline-messages-steps.md).

* **廃止**:9 月 6 日以降、従来のメッセージを使用しているすべてのジャーニーは、後で停止および削除されます。

## メリットと製品の変更点{#change}

Adobeのビジョンは、製品を継続的にシンプル化し、ユーザーフローを効率的かつ最適化することです。 この新しいメッセージ作成方法により、より効率的なユーザープロセスが実現します。

コンテンツを 1 か所に配置し、その場所で直接使用する新しいワークフローを設計しました。

コンテンツの作成は、ジャーニー内で直接実行されるようになりました。 即時 **メリット** 次の情報が得られます。

* 1 つのフローでJourney Optimizerチャネルを使用して、より迅速なジャーニー構築。
* ジャーニー内のすべての E メール、プッシュ、SMS コンテンツをシームレスに切り替えることで、コンテンツをすばやく視覚化します。
* キャンバスからのコンテキストパーソナライゼーションを使用した E メールおよびプッシュのフローを改善しました。
* ジャーニーレポートは、詳細なチャネルレポート情報を一元化します。

こちらが **製品の変更** この新機能によってもたらされる：

<table>
<tr>
<th>移行前</th>
<th>移行後</th>
</tr>
<tr>
<td><img src="assets/inline-migration-before.png"><p>以前、 <strong>メッセージ</strong> メニュー </p></td>
<td><img src="assets/inline-migration-after.png"><p>さて、 <strong>メッセージ</strong> メニューの左側のナビゲーションは使用できなくなりました。 </p></td>
</tr>
<tr>
<td><img src="assets/inline-migration-before2.png"><p>次に、ジャーニーを作成し、 <strong>メッセージ</strong> アクティビティを選択し、前に作成したメッセージを選択します。</p></td>
<td><img src="assets/inline-migration-after2.png"><p>これで、目的のチャネルアクションアクティビティ（E メール、SMS、プッシュ）をジャーニーに追加するだけで済みます。 アクティビティで、メッセージパラメーターを直接設定し、コンテンツエディターにアクセスします。</p></td>
</tr>
<tr>
<td><img src="assets/inline-migration-before3.png"><p>以前は、レポートには、メッセージレベルとジャーニーレベルの両方でアクセスできました。 メッセージ実行タブとジャーニーレポート間を移動する必要がありました。</p></td>
<td><img src="assets/inline-migration-after3.png"><p>すべてのレポートをジャーニーレベルで一元化。 これにより、ナビゲーションとユーザーエクスペリエンスが向上します。 1 つのジャーニーに複数の E メールがある場合、 <strong>アクション</strong> 関連するレポートを表示するドロップダウンメニュー。
</p></td>
</tr>
</table>

GA（7 月 25 日）では、この新しいユーザーフローは、すべての新しいジャーニーに適用されます。 この **メッセージ** メニューの左側のナビゲーションは使用できなくなりました。

## 移行のタイムライン{#iterations}

を使用して既存のジャーニーを切り替えるには、移行が必要です。 **メッセージ** をインラインで作成されたアクションを含むジャーニーに追加します。 ジャーニーの自動コンバージョンが実行されます。 しかし、いくつかの手順について、皆様のご協力が必要となります。

移行は、夜間に各地域に対して数回繰り返し実行されます。 移行タイムラインを次に示します。

* 2002 年 7 月 25 日：GA — 第 1 イテレーション
* 2002 年 8 月 1 日：第 2 反復
* 2022 年 9 月 6 日：3 番目の反復
* 2022 年 9 月 7 日：廃止

繰り返しが必要な理由

繰り返し実行する際には、各ジャーニーを順に実行し、可能な場合はそれらを移行します。 自動的に移行しない場合もあります。ジャーニーがライブまたはクローズされた場合（つまり、ジャーニーにプロファイルが存在する可能性があります）。 この場合は、アクションを実行するように求め、次の反復では、以前の反復で移行できなかったこれらのジャーニーが移行されます。

## FAQ {#faq}

### 変更についてどのように知らされますか？{#inform}

Adobeは、最初の反復の前にユーザーと通信します。

変更は、数回繰り返し実施され、一晩で導入されます。 詳細情報： [繰り返し](../rn/inline-messages.md#inline-authoring).

また、製品内通知によって通知され、ジャーニー画面に表示されます。

* デプロイメントを変更する前に

   ![](assets/inline-migration-banner1.png)

* 反復中

   ![](assets/inline-migration-banner2.png)

* 反復後

   ![](assets/inline-migration-banner3.png)

   反復後、 **ステータスを確認** ボタンが表示されます。 これにより、すべてのジャーニーを JSON 形式で表示し、それぞれの移行ステータスで表示できます。 この[節](../rn/inline-messages.md#status)を参照してください。

* バナーが消えたら、あなたは行って良いです。 これ以上のアクションは必要ありません。

### 移行プロセスとは{#process}

移行は、有効でないジャーニーや終了していないジャーニーに対しては、完全に自動的におこなわれます。 本番環境への影響を避けるために、ライブジャーニーやクローズ済みジャーニーに影響を与えたくはありません。 作成した新しいバージョンを公開するようにお願いします。

顧客組織のすべてのサンドボックスが同時に処理されます。 変更のデプロイメント中に、次の操作が実行されます。

**メッセージを使用しない任意のジャーニー**

これらは変更の影響を受けません。 移行のターゲットになるのは、メッセージを使用するジャーニーのみです。 ただし、次の URL を使用して、ジャーニーで使用されていないメッセージに引き続きアクセスできます。https://experience.adobe.com/#/@[組織]/sname:[サンドボックス]/journey-optimizer/messages/

**1 つ以上のメッセージを使用する下書きジャーニー**

移行中に、下書きバージョンのメッセージが変更されます。 これ以降、メッセージは参照されません。 この **メッセージ** アクティビティは、適切なチャネルアクションアクティビティに置き換えられます。 それぞれに、チャネルパラメーターとコンテンツが含まれます。

通常どおり、公開する前にドラフトジャーニーをテストします。

**少なくとも 1 つのジャーニーを使用するライブメッセージ**

本番環境への影響を回避するため、ジャーニーのライブバージョンは継続して実行されます。

このジャーニーの新しい下書きバージョンは、移行中に作成されます。 この新しい下書きバージョンはライブバージョンのコピーになりますが、メッセージはインラインで作成されたチャネルアクションに置き換えられます。 各チャネルアクションアクティビティには、チャネルパラメーターとコンテンツが含まれます。 コンテンツが失われません。 レポートが失われません

この下書きバージョンを確認し、テストして公開し、ライブバージョンにすることをお勧めします。

**少なくとも 1 つのメッセージを使用してジャーニーを完了または停止しました**

これらのジャーニーも移行されます。

ジャーニーレポートを見ると、以前メッセージレポートで使用できた情報のレベルがレポートに含まれるようになります。

**少なくとも 1 つのメッセージを使用するクローズ済みジャーニー**

本番環境への影響を回避するため、ジャーニーのクローズバージョンは、内部の任意のプロファイルに対して継続的に実行されます。

クローズ済みジャーニーは、30 日後に自動的に「完了」ステータスに切り替わります。 完了後の次の反復で考慮されます。

**マルチチャネルジャーニー**

これらは移行されません。 作成を再作成する必要があります。

### 顧客としてのアクション項目は何ですか？{#actions}

ジャーニーの自動変換は実行されますが、いくつかの手順が必要です。 このドキュメントで必要な手順の詳細を説明します [ページ](../rn/inline-messages-steps.md).

<!--

The process timeline is indicated in a blue banner on the Journeys screen. See this [section](../rn/inline-messages.md#inform). 

**Before migration**

* Check the date indicated in the banner. 
* Stop non-critical journeys, on development, stage and production environments.
* If you have draft messages that you want to keep using, add them to a journey so they are migrated.

**During migration**

* Migration occurs at night-time
* Do not to create, edit or delete journeys.

**After migration**

* After each iteration, click the **Check status** button in the top banner. This page lists all journeys and their migration status. See this [section](../rn/inline-messages.md#status). 

* For each live journey, a new version is created. Review the new version, test it and publish it. 

* The **Messages** menu, in the left navigation is no longer available. You need to use the new in-line message feature. See this [section](../rn/inline-messages.md#change). 

* If you need to access a specific message which was not used in a journey, you can use this URL and save the content as a template: https://experience.adobe.com/#/@[ORG]/sname:[SANDBOX]/journey-optimizer/messages/

## How can I check the migration status?{#status}

Click the **Check status** button in the top banner. The following page is displayed.

![](assets/inline-migration-log.png)

The status report is at sandbox level. This report includes several useful sections:

**migrationStatus**

This section displays the migration information since the first iteration. Numbers are incremented after each iteration.

* MIGRATED: number of draft journeys migrated successfully.
* NEW_VERSION_CREATED: number of live journeys migrated. For each live journey, a new draft version is created: you must test and publish this version.
* ERROR: number of draft journeys not migrated because of a failure. You need to re-create them.
* ERROR_ON_NEW_VERSION_CREATION: number of live journeys not migrated because of a failure. new draft journey versions not migrated because of a failure. You need to re-create them.

**eligibilityStatus**

This section lists the remaining items after the last iteration:

* toMigrate: number of draft journeys that need to be migrated.
* createNewVersion: number of live journeys to migrate.
* noMigration_live: number of live journeys that do not need to be migrated
* noMigration: number of draft journeys that do not need to be migrated.

The **details** section gives, for each of the above indicators, the list of related journeys.

-->

### 移行ステータスを確認するにはどうすればよいですか？{#status}

次をクリック： **ステータスを確認** 」ボタンをクリックします。 次のページが表示されます。

![](assets/inline-migration-log.png)

ステータスレポートは、サンドボックスレベルです。 このレポートには、次の便利な節が含まれます。

**migrationStatus**

このセクションには、最初の反復以降の移行情報が表示されます。 数値は、繰り返しごとに増分されます。

* 移行済み：ドラフト、完了および停止されたジャーニーの数が正常に移行されました。
* NEW_VERSION_CREATED:移行されたライブジャーニーの数。 ライブジャーニーごとに、新しいドラフトバージョンが作成されます。このバージョンをテストして公開する必要があります。
* エラー：ドラフト、完了および停止したジャーニーの数が、失敗したため移行されなかった。 これらを再作成する必要があります。
* ERROR_ON_NEW_VERSION_CREATION:失敗のために移行されなかったライブジャーニーの数。 新しいドラフトジャーニーバージョンは、失敗のため移行されませんでした。 新しい下書きバージョンは作成されていません。 手動で再作成する必要があります。

**eligibilityStatus**

このセクションには、最後の反復以降の残りの項目が一覧表示されます。

* 移行するには：移行する必要があるドラフト、完了および停止されたジャーニーの数。
* createNewVersion:移行するライブジャーニーの数。
* noMigration_live:移行する必要がないライブジャーニーの数。 クローズ済みジャーニーもここに表示されます。
* noMigration:移行する必要のないジャーニーの数。

この **詳細** セクションには、上記の各セクションに関連するジャーニーのリストが表示されます。

### この変更によってサービスが中断されることはありますか？{#interruption}

サービスが中断されることはありません。

* ライブジャーニーの場合：影響なし、継続して実行します。
* 作成済みのジャーニーの場合：移行中（夜間）は、ジャーニーの作成、編集または削除はしないことを強くお勧めします。

### データが失われる可能性はありますか？ {#data}

データの損失やライブジャーニーへの影響はありません。 更新されたジャーニーバージョンの公開を制御できます。

### 機能が失われる可能性はありますか？{#functionality}

メッセージの作成方法に変更が生じます。 機能が失われることはありません。

### 移行プロセス中に環境にアクセスできますか？

移行は夜間に行われます。 製品を使用できるようになります。 ただし、ジャーニーを作成、編集、削除しないでください。

### メッセージは引き続き送信されますか？

はい、ライブジャーニーは継続して実行されます。

### 移行が完了したことを確認する方法を教えてください。

バナーが消えると、移行は完了です。 この[節](../rn/inline-messages.md#inform)を参照してください。

<!--
* Improved authoring flow and navigation
* Personalization: improved contextual personalization flow
* Reporting: the message execution screen will no longer exist. Reporting is centralized in journeys.
* You will still be able to update content in a live journey.
->>
