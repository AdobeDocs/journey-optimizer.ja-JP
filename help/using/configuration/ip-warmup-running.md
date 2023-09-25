---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランを実行する
description: IP ウォームアッププランの実行および監視方法の詳細
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP、プール、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
source-git-commit: 1ec2c406e777e08de97c3ad53cee5986afeb3c44
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 1%

---

# IP ウォームアッププランを実行する {#ip-warmup-running}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* [IP ウォームアッププランを作成する](ip-warmup-plan.md)
* **[IP ウォームアッププランを実行する](ip-warmup-running.md)**

>[!ENDSHADEBOX]

一度 [IP ウォームアッププランを作成しました](ip-warmup-plan.md) および配信品質コンサルタントと共に準備されたファイルをアップロードした場合は、プランのフェーズと実行を定義できます。

各フェーズは、1 つのキャンペーンを割り当てる、複数の実行で構成される期間に対応します。

実行ごとに、一定数の受信者が存在し、その実行を実行するタイミングをスケジュールします。

## フェーズを定義する {#define-phases}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_campaigns_excluded"
>title="除外するキャンペーンオーディエンスを選択"
>abstract="現在のフェーズから除外する他のキャンペーンのオーディエンスを選択します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_domains_excluded"
>title="除外するドメイングループを選択"
>abstract="現在のフェーズから除外するドメインを選択します。"

フェーズレベルでキャンペーンとオーディエンスを関連付け、1 つのクリエイティブ/キャンペーンに関連するすべての実行で必要に応じて、一部の設定を有効にする必要があります

フェーズレベルでは、以前にターゲット設定された+新しいプロファイルが取得され、反復レベルでは、各実行に一意のプロファイルが割り当てられ、計画に記載されている値とカウントが一致するようになります

1. 各フェーズで、IP ウォームアッププランのこのフェーズに関連付けるキャンペーンを選択します。

   ![](assets/ip-warmup-plan-select-campaign.png)

   次のことに注意してください。

   * 次を含むキャンペーンのみ： **[!UICONTROL IP ウォームアッププランの有効化]** オプション有効 <!--and live?--> は選択可能です。 [詳細情報](#create-ip-warmup-campaign)

   * 現在の IP ウォームアッププランで選択したものと同じサーフェスを使用するキャンペーンを選択する必要があります。

   * 別の IP ウォームアップキャンペーンで既に使用中のキャンペーンは選択できません。

1. Adobe Analytics の **[!UICONTROL プロファイルの除外]** 「 」セクションでは、そのフェーズの以前の実行からのプロファイルが常に除外されることを確認できます。 例えば、「実行」で#1対象となる最初の 4800 人のユーザーがプロファイルの対象となった場合、「実行」で同じプロファイルが電子メールを受信しないように自動的にシス#2ムが保証しす。

1. 次から： **[!UICONTROL 除外されたキャンペーンオーディエンス]** セクションで、他のオーディエンスを選択します <!--executed/live?-->現在のフェーズから除外するキャンペーン。

   ![](assets/ip-warmup-plan-exclude-campaigns.png)

   たとえば、フェーズ 1 の実行時に、次の手順を実行する必要がありました。 [分割する](#split-phase) 何らかの理由で したがって、フェーズ 1 から以前に連絡したプロファイルがフェーズ 2 に含まれないように、フェーズ 1 で使用するキャンペーンを除外できます。 他の IP ウォームアッププランからキャンペーンを除外することもできます。

1. 次から： **[!UICONTROL 除外されたドメイングループ]** 「 」セクションで、そのフェーズから除外するドメインを選択します。

   ![](assets/ip-warmup-plan-exclude-domains.png)

   例えば、IP ウォームアップを数日間実行した後、ドメイン (Adobe) での ISP の評判が良くないことに気が付き、IP ウォームアップ計画を停止せずに解決したいと考えます。 この場合、ドメインドメイングループを除外するAdobeドメイングループを指定できます。

   >[!NOTE]
   >
   >ドメインの除外には実行されないフェーズが必要なので、除外を追加するには、実行フェーズを分割する必要が生じる場合があります。 同様に、ドメイングループが OOTB ドメイングループでない場合は、このドメイングループを Excel ファイルに追加し、アップロードしてからドメインを除外する必要があります。

   ![](assets/ip-warmup-plan-phase-1.png)

1. 必要に応じて、フェーズを追加できます。 これは、最後の現在のフェーズの後に追加されます。

1. 以下を使用します。 **[!UICONTROL フェーズを削除]** ボタンをクリックして、不要なフェーズを削除します。

   ![](assets/ip-warmup-plan-add-delete-phases.png)

   >[!CAUTION]
   >
   >この操作を元に戻すことはできません。 **[!UICONTROL 削除]** アクション。
   >
   >IP ウォームアッププランからすべてのフェーズを削除する場合は、プランを再度アップロードすることをお勧めします。

## 実行の定義 {#define-runs}

1. 各実行のスケジュールを選択します。 <!--which is actually a window of opportunity. meaning? how many hours? shall we specify that to clarify?-->

   ![](assets/ip-warmup-plan-send-time.png)

1. オーディエンスセグメントジョブの実行に遅延が生じた場合に備えて、IP ウォームアップキャンペーンを実行できる期間を選択します。 終了時間を指定しない場合は、開始時に実行が試行され、セグメント化が完了しなかった場合は失敗します。

1. 各実行をアクティブ化します。 セグメント化ジョブを実行できるように、十分な早い時間をスケジュールしてください。 <!--explain how you can evaluate a proper time-->

   >[!CAUTION]
   >
   >各実行は、実際の送信時間の 12 時間以上前に有効化する必要があります。 そうしないと、セグメント化が完了しない場合があります。 <!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

   <!--Sart to execute on every day basis by simply clicking the play button > for each run? do you have to come back every day to activate each run? or can you schedule them one after the other?)-->

1. キャンペーンの実行が開始されていない場合は、実行を停止できます。<!--why?-->

   >[!NOTE]
   >
   >キャンペーンの実行が開始されると、 **[!UICONTROL 停止]** ボタンが使用できなくなります。 <!--TBC in UI-->

   ![](assets/ip-warmup-plan-stop-run.png)

1. 実行を追加するには、「 **[!UICONTROL 下に実行を追加]** を 3 つのドットアイコンから選択します。

   ![](assets/ip-warmup-plan-run-more-actions.png)

## フェーズの分割 {#split-phase}

特定の実行から開始する別のキャンペーンを使用する場合は、 **[!UICONTROL 新しいフェーズに分割オプション]** を 3 つのドットアイコンから選択します。

現在のフェーズの残りの実行に対して新しいフェーズが作成されます。 手順に従います。 [上](#define-phases) をクリックして、新しいフェーズを定義します。

たとえば、[ 実行 ] にこのオプションを選択す#4、[ 実行 ] から [ 実行 ] に [ 実#4] を選択する#8、新しいフェーズに移動します。

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

## プランを完了済みとしてマーク {#mark-as-completed}

プランのパフォーマンスが不十分な場合や、プランをドロップして別のプランを作成する場合は、完了とマークできます。

これをおこなうには、 **[!UICONTROL その他]** IP ウォームアッププランの右上にあるボタンをクリックし、 **[!UICONTROL 完了済みとしてマーク]**.

![](assets/ip-warmup-plan-mark-completed.png)

このオプションは、プラン内のすべての実行が **[!UICONTROL 成功]** または **[!UICONTROL ドラフト]** ステータス。 実行できません **[!UICONTROL ライブ]**.

様々な実行ステータスについては、 [この節](#monitor-plan).

## プランの監視 {#monitor-plan}

プランの影響を測定するには、レポートを使用して IP ウォームアップキャンペーンのパフォーマンスを確認します。 キャンペーン E メールの詳細を表示 [ライブレポート](../reports/campaign-live-report.md#email-live) および [グローバルレポート](../reports/campaign-global-report.md##email-global).

IP 暖機プラン自体も、1 か所で統合レポートとして機能します。 次の数のような要素を確認できます。 **[!UICONTROL ライブ]** または **[!UICONTROL 成功]** は各フェーズで実行され、IP ウォームアップ計画の進行状況を確認します。

実行には、次のステータスがあります。

* **[!UICONTROL ドラフト]** ：実行が作成されたときは常に、 [新しいプランのアップロード](ip-warmup-plan.md) または [実行の追加](#define-runs) ユーザーインターフェイスから、 **[!UICONTROL ドラフト]** ステータス。
* **[!UICONTROL ライブ]**：実行をアクティブ化するたびに、実行が必要になります **[!UICONTROL ライブ]** ステータス。
* **[!UICONTROL 成功]**<!--TBC-->：この実行のキャンペーンの実行が完了しました。 <!--i.e. campaign execution has started, no error happened and emails have reached users? to check with Sid-->
* **[!UICONTROL キャンセル]**: a **[!UICONTROL ライブ]** を使用して実行がキャンセルされました **[!UICONTROL 停止]** 」ボタンをクリックします。 このボタンは、キャンペーンの実行が開始されていない場合にのみ使用できます。 [詳細情報](#define-runs)
* **[!UICONTROL 失敗]**：システムでエラーが発生したか、現在のフェーズで使用されているキャンペーンが停止しました<!--what should the user do in that case?-->.
