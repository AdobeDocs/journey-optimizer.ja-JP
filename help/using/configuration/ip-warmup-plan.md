---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランを作成
description: Journey Optimizer で IP ウォームアッププランを作成する方法を学ぶ
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: eb4a4929de17f0b57216f69e00da6314f7b59b07
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 100%

---

# IP ウォームアッププランを作成 {#ip-warmup}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* **[IP ウォームアッププランを作成](ip-warmup-plan.md)**
* [IP ウォームアッププランを実行](ip-warmup-execution.md)

>[!ENDSHADEBOX]

専用のサーフェスと対応するオプションを有効にして、1 つ以上の [IP ウォームアップキャンペーン](ip-warmup-campaign.md)を作成したら、IP ウォームアッププランの作成を開始できます。

>[!CAUTION]
>
>IP ウォームアッププランへのアクセス、作成、編集および削除には、**[!UICONTROL 配信品質コンサルタント]**&#x200B;権限が必要です。<!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

## IP ウォームアッププランファイルを準備 {#prepare-file}

IP ウォームアップは、正当な送信者としての評判を確立するために、IP およびドメインから主要なインターネットサービスプロバイダー（ISP）に送信されるメールの量を徐々に増やすことで構成されるアクティビティです。

このアクティビティは、通常、配信品質の専門家の支援を受けて、業界ドメイン、ユースケース、地域、ISP、その他の様々な要因に基づいて綿密に検討されたプランを準備するのに役立ちます。

<!--When working with the [!DNL Journey Optimizer] IP warmup feature, this plan takes the form of an Excel file that must contain a number of predefined columns.-->

IP ウォームアッププランを [!DNL Journey Optimizer] インターフェイスで作成する前に、プランにフィードするすべてのデータを Excel テンプレートに入力する必要があります。

>[!CAUTION]
>
>配信品質コンサルタントと協力して、IP ウォームアッププランファイルが正しく設定されていることを確認します。
>
>必ず、テンプレートで指定された形式を使用してください。

以下は、IP ウォームアッププランを含むファイルの例です。

![](assets/ip-warmup-sample-file.png)

>[!NOTE]
>
>現時点では、**プロパティ**&#x200B;および&#x200B;**値**&#x200B;セルを変更しないでください。

### 「IP ウォームアッププラン」タブ {#ip-warmup-plan-tab}

* この例では、100 万を超えるプロファイルのターゲットボリュームを達成するために、17 日間にわたるプラン（「**実行**」と呼ばれる）が準備されています。

* この計画は 6 つの&#x200B;**フェーズ**&#x200B;を通じて実行され、各フェーズには少なくとも 1 回の実行が含まれます。

* 配信先のドメインに必要な数の列を含めることができます。この例では、計画は次の 6 つの列に分割されます。

   * そのうち 4 列は&#x200B;**標準のドメイングループ**&#x200B;を対応し、プランに使用します（Gmail、Microsoft、Yahoo、Orange）。
   * 1 列は、カスタムドメイングループに対応します（このグループを「[カスタムドメイングループ](#custom-domain-group-tab)」タブを使用して追加する必要があります）。
   * 6 列目の&#x200B;**その他**&#x200B;には、プランで明示的に適用されない他のドメインの残りのすべてのアドレスが含まれます。この列はオプションです。省略した場合、メールは指定したドメインにのみ送信されます。
* 「**エンゲージメント日数**」列は、過去の期間にブランドと関与したプロファイルのみがターゲットになっていることを示します。

このアイデアでは、各フェーズの実行数を減らしながら、各実行でターゲットアドレスの数を徐々に増やしていきます。

プランに追加できる標準のメインドメイングループを以下に示します。

* Gmail
* Adobe
* WP
* Comcast
* Yahoo
* Bigpond
* Orange
* Softbank
* Docomo
* United Internet
* Microsoft
* KDDI
* Italia Online
* La Poste
* Apple

<!--
+++ Gmail
gmail.com;gmail.fr;gmail.de;gmail.co.uk;gmail.it
+++

+++ Adobe
adobe.com;adobe.fr;adobe.es
+++

+++WP
+++

+++Comcast
+++

+++Yahoo
+++

+++Bigpond
+++

+++Orange
+++

+++Softbank
+++

+++Docomo
+++

+++United Internet
+++

+++Microsoft
+++

+++KDDI
+++

+++Italia Online
+++

+++La Poste
+++
-->

### 「カスタムドメイングループ」タブ {#custom-domain-group-tab}

また、カスタムドメイングループを含めることで、プランに列を追加することもできます。

「**[!UICONTROL カスタムドメイングループ]**」タブをクリックして、新しいドメイングループを定義します。各ドメインに対して、対象となるすべてのサブドメインを追加できます。<!--TBC-->

例えば、カスタムドメイン Luma を追加する場合、サブドメイン（luma.com、luma.co.uk、luma.it、luma.fr、luma.de など）を含めます。

![](assets/ip-warmup-sample-file-custom.png)

### 例 {#example}

次の 2 つのカスタムドメイングループがあるとします。

* 1 つは Hotmail ドメイン専用です。
* もう 1 つは、ドメイングループ Microsoft からの他のすべてのドメイン用です（したがって、すべての Hotmail ドメインを除く）。

その他のすべてのドメインは、**[!UICONTROL その他]**&#x200B;列に集められます。

1. 「**[!UICONTROL カスタムドメイングループ]**」タブで、**Hotmail** ドメイングループを作成します。

1. 同じ行にすべての Hotmail ドメインを追加します。

   [「IP ウォームアッププラン」タブ](#ip-warmup-plan-tab)のセクションにリストされる Hotmail のすべてのドメインを[コピーして貼り付け](#copy-paste)ます。

1. 別の行を追加します。

1. **Microsoft_X** ドメイングループを作成します。

1. Hotmail 以外の Microsoft ドメインをすべて同じ行に追加します。同様に、上のリストからコピーして貼り付けることができます。[詳細情報](#copy-paste)

1. 「**[!UICONTROL IP ウォームアッププラン]**」タブに戻ります。

1. 3 列を作成します。1 列は、**Hotmail** 用に、もう 1 列は、**Microsoft_X** 用に、そしてもう 1 列は、**その他**&#x200B;用に作成します。

1. 必要に応じて、列に入力します。

>[!NOTE]
>
>IP ウォームアッププランが [!DNL Journey Optimizer] にアップロードされると、Microsoft ドメイングループを除外する必要はありません。

<!--Only the domain groups listed in the **[!UICONTROL IP Warmup Plan]** tab will be taken into account.-->

### デフォルトのドメインをコピー＆ペースト {#copy-paste}

例えば、すべての Hotmail ドメインを含むカスタムドメイングループを作成する場合は、[上記の](#ip-warmup-plan-tab)デフォルトのリストからドメインをコピーして貼り付けることができます。

次に、Excel コンバージョンツールを使用して、テキストを列に変換します。

1. **[!UICONTROL データ]**／**[!UICONTROL テキストから列へ…]**&#x200B;を選択し、「**[!UICONTROL 区切り]**」、「**[!UICONTROL 次へ]**」の順に選択します。

1. 「**[!UICONTROL セミコロン]**」を選択し、「**[!UICONTROL 次へ]**」および「**[!UICONTROL 終了]**」をクリックします。

各ドメインが同じ行の異なる列に表示されるようになりました。

## IP ウォームアッププランへのアクセスと管理 {#manage-ip-warmup-plans}

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスします。これまでに作成した IP ウォームアッププランがすべて表示されます。

   ![](assets/ip-warmup-filter-list.png)

1. ステータスに基づいてフィルタリングできます。 様々なステータスを以下に示します。

   * **未開始**：実行はまだアクティブ化されていません。 [詳細情報](ip-warmup-execution.md#define-runs)
   * **ライブ**：最初のフェーズの最初の実行が正常にアクティブ化されると、プランは直ちにこのステータスに変わります。[詳細情報](ip-warmup-execution.md#define-runs)
   * **完了**：プランは完了とマークされています。 <!--This option is only available if all the runs in the plan are in **[!UICONTROL Completed]** or **[!UICONTROL Draft]** status (no run can be **[!UICONTROL Live]**).--> [詳細情報](ip-warmup-execution.md#mark-as-completed)
     <!--* **Paused**: to check (user action)-->

1. IP ウォームアッププランを削除するには、プラン名の横にある「**[!UICONTROL 削除]**」アイコンを選択し、削除を確定します。

   >[!NOTE]
   >
   >**未開始**&#x200B;のステータスのプランのみを削除できます。

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >選択した IP ウォームアッププランは完全に削除されます。

## IP ウォームアッププランを作成 {#create-ip-warmup-plan}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_upload"
>title="IP ウォームアッププランを指定"
>abstract="CSV テンプレートをダウンロードして、IP ウォームアップフェーズとプロファイルのターゲット数のデータを入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="マーケティングサーフェスを選択"
>abstract="IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="チャネルサーフェスの設定"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="IP ウォームアップキャンペーンを作成"

IP ウォームアッププランを作成するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスし、「**[!UICONTROL IP ウォームアッププランを作成]**」をクリックします。

   ![](assets/ip-warmup-create-plan.png)

1. IP ウォームアッププランの詳細（名前と説明）を入力します。

   ![](assets/ip-warmup-plan-details.png)

1. ウォームアップする[サーフェス](channel-surfaces.md)を選択します。選択できるのはマーケティングサーフェスのみです。[メールのタイプの詳細情報](../email/email-settings.md#email-type)

   >[!NOTE]
   >
   >IP ウォームアッププランに関連付けるキャンペーンは、同じサーフェスを使用する必要があります。[IP ウォームアップキャンペーンの作成方法を学ぶ](ip-warmup-campaign.md)

1. IP ウォームアッププランを含む Excel ファイルをアップロードします。[詳細情報](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

   >[!NOTE]
   >
   >アップロードに失敗した場合は、正しい形式とファイル形式（.xls または.xlsx）を使用していることを確認してください。アドビが提供するサンプルを使用します。

1. 「**[!UICONTROL 作成]**」をクリックします。アップロードしたファイルに定義されているすべてのフェーズ、実行、列、およびそれらのコンテンツは、[!DNL Journey Optimizer] インターフェイスに自動的に表示されます。

   ![](assets/ip-warmup-plan-uploaded.png)

これで、IP ウォームアッププランを実行する準備が整いました。[詳細情報](ip-warmup-execution.md)
