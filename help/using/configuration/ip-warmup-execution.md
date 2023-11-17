---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランの実行
description: IP ウォームアッププランの実行および監視方法について説明します
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
exl-id: 752ffd7f-09c2-4aa3-a067-2dbe0634709c
source-git-commit: 2483f53982acc920676190c1bc7fef5abf3c2331
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 66%

---

# IP ウォームアッププランを実行 {#ip-warmup-running}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* [IP ウォームアッププランを作成](ip-warmup-plan.md)
* **[IP ウォームアッププランの実行](ip-warmup-execution.md)**

>[!ENDSHADEBOX]

[IP ウォームアッププランを作成](ip-warmup-plan.md)し、配信品質コンサルタントと共に準備したファイルをアップロードしたら、プランのフェーズと実行を定義できます。

各フェーズは複数の実行で構成され、それらの実行に 1 つのキャンペーンを割り当てます。

## フェーズの定義 {#define-phases}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_campaigns_excluded"
>title="キャンペーンオーディエンスの除外"
>abstract="現在のフェーズからオーディエンスを除外するキャンペーンを選択します。 これは、他のフェーズや他の IP ウォームアッププランから以前にコンタクトされたプロファイルが、再びターゲットにされるのを防ぐためです。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_domains_excluded"
>title="ドメイングループの除外"
>abstract="現在のフェーズから除外するドメインを選択します。ドメインの除外には実行されないフェーズが必要なので、場合によっては、実行フェーズを分割して除外を追加する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/implement-ip-warmup-plan/ip-warmup-execution.html?lang=ja#split-phase" text="フェーズの分割"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_phases"
>title="プランのフェーズの定義"
>abstract="各フェーズは複数の実行で構成され、それらの実行に 1 つのキャンペーンを割り当てます。"

<!--You need to associate the campaign and audience at phase level and turns on some settings as needed for all runs associated with a single creative/campaign

At phase level, system ensures that previously targeted + new profiles are picked up AND at iteration level, system ensures that each run is having unique profiles and the count matches what is stated in plan-->

<!--![](assets/ip-warmup-plan-phase-1.png)-->

1. フェーズごとに、IP ウォームアッププランのこのフェーズに関連付けるキャンペーンを選択します。

   >[!NOTE]
   >
   >別の IP ウォームアッププランで既に使用中のキャンペーンは選択できません。ただし、同じ IP ウォームアッププランの 1 つ以上のフェーズで同じキャンペーンを使用できます。

   ![](assets/ip-warmup-plan-select-campaign.png)

   >[!IMPORTANT]
   >
   >* 「**[!UICONTROL IP ウォームアッププランのアクティベーション]**」オプションが有効になっているキャンペーンのみを選択できます。[詳細情報](#create-ip-warmup-campaign)
   >
   >* 現在の IP ウォームアッププランで選択したものと同じサーフェスを使用するキャンペーンを選択する必要があります。

1. 現在のフェーズでキャンペーンを選択すると、プロファイル、キャンペーンオーディエンス、ドメイングループを除外するセクションが表示されます。

   >[!NOTE]
   >
   >実行がアクティブ化されると、次の操作を行わない限り、除外を変更できなくなります [ランを分割する](#split-phase) を新しいフェーズに追加します。

   1. 「**[!UICONTROL プロファイルの除外]**」セクションでは、そのフェーズの前の実行からのプロファイルが常に除外されることを確認できます。例えば、実行 #1 で、ターゲットとなる最初の 4,800 人のユーザーがプロファイルに含まれていた場合、システムは自動的に、同じプロファイルが実行 #2 でメールを受信しないようにします。

      >[!NOTE]
      >
      >このセクションは編集できません。

   1. 次から： **[!UICONTROL 除外されたキャンペーンオーディエンス]** 「 」セクションで、現在のフェーズからオーディエンスを除外するキャンペーンを選択します。

      ![](assets/ip-warmup-plan-exclude-campaigns.png)

      例えば、フェーズ 1 の実行中に、何らかの理由で[フェーズを分割](#split-phase)する必要があったとします。そのため、フェーズ 1 で使用したキャンペーンを除外して、フェーズ 1 で以前にコンタクトしたプロファイルがフェーズ 2 に含まれないようにすることができます。他の IP ウォームアッププランからキャンペーンを除外することもできます。

   1. 「**[!UICONTROL 除外されたドメイングループ]**」セクションで、そのフェーズから除外するドメインを選択します。

      >[!NOTE]
      >
      >ドメインの除外には実行されないフェーズが必要なので、場合によっては、[実行フェーズを分割](#split-phase)して除外を追加する必要があります。

      ![](assets/ip-warmup-plan-exclude-domains.png)

      例えば、IP ウォームアップを数日間実行した後、ドメイン（Adobe など）での ISP の評判が良くないことに気付き、IP ウォームアッププランを停止せずに解決したいとします。このような場合は、Adobe ドメイングループを除外できます。

      >[!NOTE]
      >
      >除外できるのは、 [IP ウォームアッププランテンプレート](ip-warmup-plan.md#prepare-file). そうでない場合は、除外するドメイングループでテンプレートを更新し、 [プランを再度アップロード](#re-upload-plan).

1. 必要に応じて、 **[!UICONTROL キャンペーンの置換]** 」ボタンをクリックします。

   ![](assets/ip-warmup-plan-replace-campaign.png)

   >[!NOTE]
   >
   >このアクションは、フェーズの最初の実行をアクティブ化する前にのみ実行できます。 実行が有効化されると、次の条件を満たさない限り、キャンペーンは置き換えられません。 [ランを分割する](#split-phase) を新しいフェーズに追加します。

1. 必要に応じて、フェーズを追加できます。現在の最終フェーズの後に追加されます。

   ![](assets/ip-warmup-plan-add-phase.png)

1. 「**[!UICONTROL フェーズを削除]**」ボタンを使用して、不要なフェーズを削除します。このアクションは、フェーズで実行が実行されない場合にのみ使用できます。 <!--Once a run is executed, deletion is not allowed.-->

   >[!CAUTION]
   >
   >**[!UICONTROL 削除]**&#x200B;アクションを取り消すことはできません。

   ![](assets/ip-warmup-plan-delete-phase.png)

   >[!NOTE]
   >
   >IP ウォームアッププランからすべてのフェーズを削除する場合は、プランを再アップロードすることをお勧めします。[詳細情報](#re-upload-plan)

## 実行の定義 {#define-runs}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_run"
>title="各実行の定義"
>abstract="すべてのフェーズの各実行を定義しアクティブ化します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_last_engagement"
>title="エンゲージメントに関するフィルタリング"
>abstract="この列は、例えば、過去 20 日間にブランドとエンゲージしたユーザーのみをターゲットにするフィルターです。この設定は、「**実行を編集**」オプションから変更することもできます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_retry"
>title="時間枠を設定"
>abstract="セグメント化ジョブに遅延が生じた場合に、IP ウォームアップキャンペーンを実行できる時間枠を定義できます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_pause"
>title="オーディエンスエラーによる実行をキャンセル"
>abstract="オーディエンスが実行に対して評価された後で、適格なプロファイルより小さい場合に、このオプションを選択して実行をキャンセルします。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_qualified"
>title="認定プロファイルを表示"
>abstract="この列には、認定プロファイルの数が表示されます。オーディエンスが実行に対して評価された後、適格なプロファイルが認定プロファイルよりも多い場合、「**エラーが発生した場合に一時停止**」オプションが有効になっていない限り、実行は引き続き行われます。この場合、実行はキャンセルされます。"

1. 各実行のスケジュールを選択して、指定した時間に実行されるようにします。

   ![](assets/ip-warmup-plan-send-time.png)

1. 必要に応じて、IP ウォームアップキャンペーンを実行する時間枠を定義できます。この期間に、 [オーディエンス評価](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#how-segmentation-works){target="_blank"}. これを行うには、左上のプラン名の横にある「プロパティ」アイコンをクリックし、**[!UICONTROL 再試行の実行時間]**&#x200B;ドロップダウンリストを使用して、最大 240 分（4 時間）の期間を選択します。

   ![](assets/ip-warmup-plan-retry-run-time.png)

   例えば、指定した日の午前 9 時に送信時間を設定し、再試行実行時間として 120 分を選択した場合、オーディエンス評価で予期しない遅延が発生した場合に、実行時間を 2 時間（午前 9 時～午前 11 時）に設定できます。

   >[!NOTE]
   >
   >時間枠を指定しない場合、送信時に実行が試行され、オーディエンスの評価が完了していない場合は失敗します。

1. 必要に応じて、その他のアクションアイコンから「**[!UICONTROL 実行を編集]**」を選択します。各列のアドレス数を更新できます。また、過去 20 日間にブランドに関与したユーザーのみをターゲットにするように、「**[!UICONTROL 最後のエンゲージメント]**」フィールドを更新することもできます。

   >[!NOTE]
   >
   >配信品質のエキスパートに相談して、これらの数値を変更することをお勧めします。

   ![](assets/ip-warmup-plan-edit-run.png)

   >[!NOTE]
   >
   >実行にエンゲージメント期間を適用しない場合は、「**[!UICONTROL 前回のエンゲージメント]**」フィールドに 0 を入力します。

1. オーディエンスが実行の評価後に、適格なプロファイルがターゲットのプロファイルよりも小さい場合に実行をキャンセルするには、「**[!UICONTROL エラーが発生した場合に一時停止]**」オプションを選択します。その場合、実行には **[!UICONTROL 失敗]** ステータス。

   ![](assets/ip-warmup-plan-pause.png)

1. 実行を&#x200B;**[!UICONTROL アクティブ化]**&#x200B;します。[詳細情報](#activate-run)

1. この実行のステータスは、 **[!UICONTROL ライブ]**：実行をスケジュールするリクエストをシステムが受け入れたことを意味します。

   >[!NOTE]
   >
   >様々な実行ステータスは、[この節](#monitor-plan)に記載されています。

1. キャンペーンの実行が開始されていない場合は、ライブ実行を停止できます。このアクションは、実行スケジュールをキャンセルします。送信は停止しません。

   ![](assets/ip-warmup-plan-stop-run.png)

   >[!NOTE]
   >
   >キャンペーンの実行が開始されると、「**[!UICONTROL 停止]**」ボタンが使用できなくなります。

1. 実行を追加するには、「その他のアクション」アイコンから「**[!UICONTROL 以下に実行を追加]**」を選択します。

   ![](assets/ip-warmup-plan-run-more-actions.png)

## 実行を有効化 {#activate-run}

実行をアクティブ化するには、「**[!UICONTROL アクティブ化]**」ボタンを選択します。その後、毎日次の実行を有効化できます。

次の期間を考慮するために十分な時間をスケジュールしていることを確認します。 [オーディエンス評価](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#how-segmentation-works){target="_blank"} を実行します。

![](assets/ip-warmup-plan-activate.png)

>[!CAUTION]
>
>各実行は、実際の送信時間の 12 時間以上前にアクティブ化する必要があります。そうしないと、オーディエンス評価が完了しない場合があります。

実行をアクティブ化すると、複数のオーディエンスが自動的に作成されます。

* フェーズの最初の実行をアクティブ化する場合：

   * An [audience](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja){target="_blank"} 次の命名規則を使用して、除外された（存在する場合）キャンペーンオーディエンス用にが作成されます。 `<warmupName>_Phase<phaseNo>-Audience Exclusion`.

   * 次の命名規則を使用して、除外されたドメイングループに対して別のオーディエンスが作成されます（存在する場合）。 `<warmupName>_Phase<phaseNo>-Domain Exclusion`.

  >[!NOTE]
  >
  >ウォームアッププランが完了とマークされた後、オーディエンスはクリーンアップされます。
  >
  >後のフェーズで除外されたキャンペーンオーディエンスまたはドメイングループに変更がない場合、システムは新しいオーディエンスを作成しません。

* 任意の実行をアクティブ化する場合：

   * 次の命名規則を使用して、最後のエンゲージメントフィルターに対して別のオーディエンスが作成されます。 `<warmupName>_Phase<phaseNo>_Run<runNo>-Engagement Filter`.

     >[!NOTE]
     >
     >ウォームアッププランが完了とマークされた後、オーディエンスはクリーンアップされます。
     >
     >後続のフェーズで最後のエンゲージメントフィルターに変更がない場合、システムは新しいオーディエンスを作成しません。

   * An [オーディエンスの構成](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/audience-composition.html?lang=ja){target="_blank"} は、次の命名規則を使用して、キャンペーンの送信先となるオーディエンスに対応して作成されます。 `<warmupName>-Phase<phaseNo>-Run<runNo>`.

     >[!NOTE]
     >
     >実行のたびに新しいオーディエンス構成が作成されます。
     >
     >次の反復が有効化されると、オーディエンスの構成（つまり出力オーディエンス）がクリーンアップされます。

<!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

<!--Sart to execute on every day basis by simply clicking the play button > for each run? do you have to come back every day to activate each run? or can you schedule them one after the other?)-->

<!--Upon activation, when the segment evaluation happens, more segments will be created by the IP warmup service and will be leveraged in an audience composition and a new audience will be created for each run splitted into the different selected domains.-->

## プランを監視 {#monitor-plan}

IP ウォームアッププランを正しく実行するには、レポートを監視し、実行をアクティブ化して、毎日そのステータスを確認する必要があります。

### ハイライトセクションの使用 {#highlights}

最初の実行がフェーズに対して有効化されると、 **[!UICONTROL ハイライト]** セクションが表示されます。

現在の実行と今後の実行の概要をすばやく表示します。 このセクションから、次の実行を編集およびアクティブ化することもできます。

![](assets/ip-warmup-plan-highlights.png)

### 実行ステータスの確認 {#run-statuses}

IP 暖機プラン自体は、1 か所で統合レポートとして機能します。 各フェーズの「**[!UICONTROL ライブ]**」または「**[!UICONTROL 完了]**」の実行数などの要素をチェックして、IP ウォームアッププランの進捗状況を確認できます。

>[!NOTE]
>
>ベストプラクティスとして、IP ウォームアップ計画を毎日監視することをお勧めします。

実行には以下のステータスがあります。

* **[!UICONTROL ドラフト]**：「[新しいプランを作成](ip-warmup-plan.md)」する際、またはユーザーインターフェイスから「[実行を追加](#define-runs)」する際、実行が作成されるたびに、その実行は&#x200B;**[!UICONTROL ドラフト]**&#x200B;ステータスになります。
* **[!UICONTROL ライブ]**：実行をアクティベートするたびに、**[!UICONTROL ライブ]**&#x200B;ステータスが取得されます。これは、送信が開始されたのではなく、実行スケジュールのリクエストをシステムが受け入れたことを意味します。
* **[!UICONTROL 完了]**：この実行のキャンペーンの実行が完了しました。<!--i.e. campaign execution has started, no error happened and emails have reached users? to check with Sid-->
* **[!UICONTROL キャンセル]**：**[!UICONTROL ライブ]**&#x200B;実行が「**[!UICONTROL 停止]**」ボタンを使用してキャンセルされたか、「**[!UICONTROL エラーが発生した場合に一時停止]**」オプションを有効にしてエラーが発生しました。[詳細情報](#define-runs)
* **[!UICONTROL 失敗]**：システムでエラーが発生したか、現在のフェーズで使用されているキャンペーンが停止されました。実行が失敗した場合は、別の実行を次の日にスケジュールできます。

### レポートの使用 {#reports}

より一般的に、プランの影響を測定するには、 [!DNL Journey Optimizer] キャンペーンレポート。 これを行うには、完了した実行ごとに、「**[!UICONTROL レポートを表示]**」ボタンをクリックします。キャンペーンメールについて詳しくは、[ライブレポート](../reports/campaign-live-report.md#email-live)と[グローバルレポート](../reports/campaign-global-report.md#email-global)を参照してください。

![](assets/ip-warmup-plan-reports.png)

また、 [キャンペーンメニュー](../campaigns/modify-stop-campaign.md#access) 別のキャンペーンを使用するプランがあるので、

## プランを管理 {#manage-plan}

IP ウォームアッププランが期待どおりに実行されない場合は、いつでも以下のアクションを実行できます。

### フェーズの分割 {#split-phase}

特定の実行から開始する新規フェーズを追加する場合は、「その他のアクション」アイコンから「**[!UICONTROL 新規フェーズに分割オプション]**」を選択します。

![](assets/ip-warmup-plan-run-split-run.png)

現在のフェーズの残りの実行に対して新しいフェーズが作成されます。

例えば、実行 #4 に対してこのオプションを選択すると、実行 #4～#8 は現在のフェーズ直後の新規フェーズに移動します。

[上記](#define-phases)の手順に従って、新しいフェーズを定義します。

* その新しいフェーズでは、「**[!UICONTROL キャンペーンを置換]**」オプションを使用できます。

* 前のキャンペーンやパパフォーマンスの低いドメインを除外することもできます。[この節](#define-phases)でその方法を説明します。

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

### IP ウォームアッププランを再アップロード {#re-upload-plan}

IP ウォームアッププランが期待どおりに実行されない場合（一部の ISP がメッセージをスパムとしてマークしている場合など）は、配信品質のエキスパートに別の IP ウォームアッププランファイルを設定するよう依頼し、対応するボタンを使用して再アップロードできます。

![](assets/ip-warmup-re-upload-plan.png)

以前に実行されたすべての実行は読み取り専用になります。最初のプランの下に新しいプランが表示されます。

[上記](#define-phases)の手順に従って、新しいプランのフェーズを定義します。

>[!NOTE]
>
>IP ウォームアッププランの詳細は、新しくアップロードされたファイルに従って変更されます。以前に実行した実行（[ステータス](#monitor-plan)に関係なく）は影響を受けません。

例を見てみましょう。

* 初期の IP のウォームアッププランでは、フェーズ 2 は 9 回実行されました。

* 4 回の実行が実行されました（失敗したか、完了したか、キャンセルされたかは関係ありません<!--as long as a run has been attempted, it is an executed run-->）。

* 新しいプランを再アップロードすると、最初の 4 回の実行を含むフェーズ 2 は読み取り専用モードになります。

* 残りの 5 回の実行（ドラフト状態）は、新たにアップロードされたプランに従って表示される新規フェーズ（フェーズ 3）に移動します。

### プランを完了済みとしてマーク {#mark-as-completed}

プランのパフォーマンスが不十分な場合や、プランを削除して別のプランを作成する場合は、プランを完了とマークできます。

これを行うには、IP ウォームアッププランの右上にある「**[!UICONTROL その他]**」ボタンをクリックして、「**[!UICONTROL 完了済みとしてマーク]**」を選択します。

![](assets/ip-warmup-plan-mark-completed.png)

このオプションは、プラン内のすべての実行が「**[!UICONTROL 完了]**」または「**[!UICONTROL ドラフト]**」ステータスである場合にのみ使用できます。実行が「**[!UICONTROL ライブ]**」の場合、オプションはグレー表示になります。

様々な実行ステータスは、[この節](#monitor-plan)に記載されています。

