---
title: ジャーニーインラインオーサリングへの移行
description: メッセージの移行方法を説明します。
exl-id: accdebba-5322-401e-8a40-3e1539e65a7e
source-git-commit: b31eb2bcf52bb57aec8e145ad8e94790a1fb44bf
workflow-type: tm+mt
source-wordcount: '1732'
ht-degree: 100%

---


# インラインオーサリングへの移行の概要{#inline-authoring}

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_before"
>title="新しいインラインオーサリング機能の詳細情報"
>abstract="2022年7月25日（PT）より、メッセージはジャーニーから直接作成されます。既存のメッセージは、新しいモデルに自動的に移行されます。現在ジャーニー内でメッセージを使用している場合は、移行後に追加のアクションが必要になります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-authoring/inline-messages-steps.html?lang=ja" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_during"
>title="状況を把握する"
>abstract="2022年7月25日（PT）より、メッセージはジャーニーから直接作成されます。お使いの環境を移行中です。現在ジャーニー内でメッセージを使用している場合は、移行後に追加のアクションが必要になります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-authoring/inline-messages-steps.html" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_migration_after"
>title="メッセージの移行方法を説明します。"
>abstract="2022年7月25日（PT）より、メッセージはジャーニーから直接作成されます。既存のメッセージは、新しいモデルに移行されました。ジャーニー実務担当者には、メッセージを使用するジャーニーに追加のアクションが必要になりました。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/whats-new/inline-authoring/inline-messages-steps.html" text="移行手順"

>[!CONTEXTUALHELP]
>id="ajo_messages_depecrated_inventory"
>title="メッセージの移行方法を説明します。"
>abstract="2022年7月25日（PT）より、メッセージメニューが表示されなくなり、ジャーニーから直接メッセージが作成されます。 従来のメッセージをジャーニーで再利用する場合は、それらをテンプレートとして保存する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/design/email-templates.html#save-as-template" text="メッセージをテンプレートとして保存"

Adobe Journey Optimizer では、Journey Optimizer チャネル（メール、プッシュ、SMS）用のコンテンツのオーサリング方法を改善する新機能をリリースします。Journey Optimizer の実務担当者は、ジャーニーから直接メッセージを作成およびオーサリングできるようになりました。

この機能を利用するには、メッセージを使用している既存のジャーニーを移行する必要があります。このページでは、この変更に関する必要な情報と、ユーザーにとって必要な手順を説明します。

Journey Optimizer の実務担当者の役割と責任について詳しくは、この[ページ](../start/path/marketer.md)を参照してください。

<!--
Here are the main changes in the interface:

* Messages are created direcly from journeys.
* The **Messages** entry in the left navigation menu has been removed. 
* There is no separate library of messages, the journey now centralizes all components.


-->

>[!VIDEO](https://video.tv.adobe.com/v/344698)


## 主な留意点{#keys}

* **私は影響を受けますか**：左ナビゲーションの&#x200B;**メッセージ**&#x200B;メニューからメッセージを作成して、ジャーニーで使用している場合は、影響を受けることになります。サードパーティシステム（Adobe Campaign など）を使用している場合は、この移行の影響を受けません。

* **製品の変更点**：GA 時点（7月25日（PT））では、チャネルコンテンツは各ジャーニー内で作成および管理されます。左側のナビゲーションの&#x200B;**メッセージ**&#x200B;メニューは使用できなくなりました（[詳細情報](../rn/inline-messages.md#change)）。アドビが既存のジャーニーの移行を進めます。

* **タイムライン**：夜間に地域ごとに、複数の[イテレーション](../rn/inline-messages.md#iterations)を通じて移行が行われます。

   ![](assets/inline-migration-timeline.png)

* **必要なアクション**：ジャーニーの自動コンバージョンが実行されます。とは言え、いくつかの手順に関してはユーザーの協力が必要です。必要な手順について詳しくは、この[ページ](../rn/inline-messages-steps.md)を参照してください。

* **廃止**：9月6日（PT）以降、従来のメッセージをまだ使用しているすべてのジャーニーは停止し、後で削除されます。

## メリットと製品の変更点{#change}

製品を絶えず簡素化して、効率的で最適化されたユーザーフローを提供することが、アドビのビジョンです。 この新しいメッセージ作成方法により、より効率的なユーザープロセスが実現します。

コンテンツを一元化して直接そこから使用するために、この新しいワークフローを設計しました。

コンテンツの作成は、ジャーニー内で直接実行されるようになりました。すぐに得られる&#x200B;**メリット**&#x200B;は、次のとおりです。

* Journey Optimizer チャネルを単一のフローで使用して、より迅速にジャーニーを構築できます。
* ジャーニー内のすべてのメールコンテンツ、プッシュコンテンツ、SMS コンテンツをシームレスに切り替えることで、コンテンツをすばやく視覚化できます。
* キャンバスからコンテキストに基づくパーソナライゼーションを使用して、メールおよびプッシュのフローを改善しました。
* ジャーニーレポートは、詳細なチャネルレポート情報を一元化します。

この新機能によってもたらされた&#x200B;**製品の変更点**&#x200B;は次のとおりです。

<table>
<tr>
<th>移行前</th>
<th>移行後</th>
</tr>
<tr>
<td><img src="assets/inline-migration-before.png"><p>以前は、<strong>メッセージ</strong>メニューからメッセージを作成していました。 </p></td>
<td><img src="assets/inline-migration-after.png"><p>左側のナビゲーションの<strong>メッセージ</strong>メニューは使用できなくなりました。 </p></td>
</tr>
<tr>
<td><img src="assets/inline-migration-before2.png"><p>次に、ジャーニーを作成し、<strong>メッセージ</strong>アクティビティを追加して、前に作成したメッセージを選択します。</p></td>
<td><img src="assets/inline-migration-after2.png"><p>目的のチャネルアクションアクティビティ（メール、SMS、プッシュ）をジャーニーに追加するだけです。 アクティビティで、メッセージパラメーターを直接設定し、コンテンツエディターにアクセスします。</p></td>
</tr>
<tr>
<td><img src="assets/inline-migration-before3.png"><p>以前は、メッセージレベルとジャーニーレベルの両方でレポートにアクセスでき、メッセージ実行タブとジャーニーレポートの間を移動する必要がありました。</p></td>
<td><img src="assets/inline-migration-after3.png"><p>すべてのレポートが、ジャーニーレベルで一元化されるようになりました。これにより、ナビゲーションとユーザーエクスペリエンスが向上します。 1 つのジャーニーに複数のメールがある場合、<strong>アクション</strong>ドロップダウンメニューを使用して、関連するレポートを表示できます。
</p></td>
</tr>
</table>

一般公開（GA）（7月25日（PT））では、この新しいユーザーフローは、すべての新しいジャーニーに適用されます。 左側のナビゲーションの&#x200B;**メッセージ**&#x200B;メニューは使用できなくなりました。

## 移行のタイムライン{#iterations}

**メッセージ**&#x200B;を使用した既存のジャーニーを、インラインで作成したアクションを含むジャーニーに変えるには、移行が必要です。ジャーニーの自動コンバージョンがおこなわれます。 とは言え、いくつかの手順に関してはユーザーの協力が必要です。

移行は、夜間に、各地域で数回のイテレーションを通じて実行されます。 移行タイムラインを次に示します。

* 2022年7月25日（PT）：一般公開（GA） - 最初のイテレーション
* 2022年8月1日（PT）：2 回目のイテレーション
* 2022年9月5日（PT）：3 回目のイテレーション
* 2022年9月6日（PT）：廃止

複数回のイテレーションが必要な理由

イテレーションでは各ジャーニーを実行し、可能な場合は移行します。ジャーニーがライブである（つまり、ジャーニーにプロファイルがまだ残っている可能性がある）場合は、自動での移行が望ましくないケースがあります。この場合は、ユーザーにアクションを実行するように依頼し、次のイテレーションでは、前回移行できなかったこれらのジャーニーを移行します。

## FAQ {#faq}

### 変更についてどのように知らされますか？{#inform}

アドビは、最初のイテレーションの前にユーザーと通信します。

変更は、数回のイテレーションを通じて夜間にデプロイされます。 詳しくは、[イテレーション](../rn/inline-messages.md#inline-authoring)を参照してください。

また、製品内通知がジャーニー画面に表示されます。

* デプロイメントを変更する前に

   ![](assets/inline-migration-banner1.png)

* イテレーション中

   ![](assets/inline-migration-banner2.png)

* イテレーション後

   ![](assets/inline-migration-banner3.png)

   イテレーション後、「**ステータスを確認**」ボタンが表示されます。 これにより、すべてのジャーニーを JSON 形式で表示し、それぞれの移行ステータスで表示できます。この[節](../rn/inline-messages.md#status)を参照してください。

* バナーが消えたら、準備完了です。これ以上のアクションは必要ありません。

### 移行プロセスはどのようなものですか。{#process}

ライブではないジャーニーやクローズ済みではないジャーニーの移行は完全に自動化されています。実稼動環境への影響を避けるために、ライブジャーニーやクローズ済みジャーニーに影響を与えないようにします。ユーザー用に作成した新しいバージョンを公開するように求められます。

顧客組織のすべてのサンドボックスが同時に処理されます。変更をデプロイメントする際、次のアクションが実行されます。

**メッセージを使用しないすべてのジャーニー**

これらは変更の影響を受けません。移行のターゲットになるのは、メッセージを使用するジャーニーのみです。ただし、次の URL を使用して、ジャーニーで使用されていないメッセージに引き続きアクセスできます： https://experience.adobe.com/#/@[ORG]/sname:[SANDBOX]/journey-optimizer/messages/

**1 つ以上のメッセージを使用するドラフトジャーニー**

下書きバージョンのメッセージは、移行中に変更されます。メッセージは参照されなくなりました。 この&#x200B;**メッセージ**&#x200B;アクティビティは、適切なチャネルアクションアクティビティに置き換えられます。それぞれにチャネルパラメーターとコンテンツが含まれます。

通常どおり、公開する前にドラフトジャーニーをテストします。

**1 つ以上のメッセージを使用するライブジャーニー**

本番環境への影響を回避するため、ジャーニーのライブバージョンは継続して実行されます。

移行中に、このジャーニーの新しいドラフトバージョンが作成されます。この新しいドラフトバージョンはライブバージョンのコピーですが、メッセージはインラインで作成されたチャネルアクションに置き換えられます。各チャネルアクションアクティビティには、チャネルパラメーターとコンテンツが含まれます。 コンテンツは失われません。 レポートは失われません。

このドラフトバージョンを確認し、テストして公開してライブバージョンにすることをお勧めします。

**1 つ以上のメッセージを使用してジャーニーを完了または停止しました**

これらのジャーニーも移行されます。

ジャーニーレポートを見ると、レポートがより豊かになり、以前メッセージレポートで使用できたレベルの情報が含まれるようになりました。

**1 つ以上のメッセージを使用するクローズ済みジャーニー**

本番環境への影響を回避するため、ジャーニーのクローズ済みバージョンは、内部の任意のプロファイルに対して継続的に実行されます。

クローズ済みジャーニーは、30 日後、自動的に「完了」ステータスへと切り替わります。完了後の次のイテレーションで考慮されます。

**マルチチャネルジャーニー**

これらは移行されません。 再作成する必要があります。

### 顧客としてのアクション項目には何がありますか？{#actions}

ジャーニーの自動変換は実行されますが、いくつかの手順が必要です。この[ページ](../rn/inline-messages-steps.md)で必要な手順の詳細を説明します。

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

上部のバナーの「**ステータスを確認**」ボタンをクリックします。次のページが表示されます。

![](assets/inline-migration-log.png)

ステータスレポートは、サンドボックスレベルです。このレポートには、次の便利なセクションが含まれます。

**migrationStatus**

このセクションには、最初のイテレーション以降の移行情報が表示されます。数値は、イテレーションごとに増分されます。

* MIGRATED：正常に移行されたドラフト、完了および停止されたジャーニーの数。
* NEW_VERSION_CREATED：移行されたライブジャーニーの数。ライブジャーニーごとに新しいドラフトバージョンが作成されます。このバージョンをテストして公開する必要があります。
* ERROR：失敗したため移行されなかった、ドラフト、完了および停止したジャーニーの数。これらは再作成する必要があります。
* ERROR_ON_NEW_VERSION_CREATION：失敗したために移行されなかったライブジャーニーの数。失敗したために移行されなかった新しいドラフトジャーニーバージョン。新しいドラフトバージョンは作成されていません。 手動で再作成する必要があります。

**eligibilityStatus**

このセクションには、最後のイテレーション後に残っている項目が一覧表示されます。

* toMigrate：移行する必要があるドラフト、完了および停止されたジャーニーの数。
* createNewVersion：移行するライブジャーニーの数。
* noMigration_live：移行する必要がないライブジャーニーの数。クローズ済みジャーニーもここに表示されます。
* noMigration：移行する必要のないジャーニーの数。

この「**詳細**」セクションには、上記の各セクションに関連するジャーニーのリストが表示されます。

### この変更によってサービスが中断されることはありますか？{#interruption}

サービスが中断されることはありません。

* ライブジャーニーの場合：影響なし、継続して実行します。
* 作成済みのジャーニーの場合：移行中（夜間）は、ジャーニーの作成、編集または削除はしないことを強くお勧めします。

### データが失われる可能性はありますか？ {#data}

データの損失やライブジャーニーへの影響はありません。更新されたジャーニーバージョンの公開を制御できます。

### 機能が失われる可能性はありますか？{#functionality}

メッセージの作成方法に変更が生じます。機能が失われることはありません。

### 移行プロセスの間、環境にアクセスできますか？

移行は夜間におこなわれます。製品を使用できるようになります。 ただし、ジャーニーを作成、編集、削除しないでください。

### メッセージは引き続き送信されますか？

はい、ライブジャーニーは継続して実行されます。

### 移行が完了したことを確認する方法を教えてください。

バナーが消えると、移行は完了です。この[節](../rn/inline-messages.md#inform)を参照してください。

### メッセージ関連の権限はどのような影響を受けますか？

インラインオーサリング機能は、権限に影響を与えます。[!DNL View Messages] や [!DNL Manage Messages] などのメッセージ関連の権限はすべて、ジャーニー機能にリンクされた権限に自動的に含まれます。

詳しくは、この[ページ](../administration/ootb-product-profiles.md)を参照してください。

<!--
* Improved authoring flow and navigation
* Personalization: improved contextual personalization flow
* Reporting: the message execution screen will no longer exist. Reporting is centralized in journeys.
* You will still be able to update content in a live journey.
->>
