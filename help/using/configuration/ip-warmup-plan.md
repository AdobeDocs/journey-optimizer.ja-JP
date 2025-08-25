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
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 84%

---

# IP ウォームアッププランを作成 {#ip-warmup}

専用の設定と対応するオプションを有効にして、1 つ以上の [IP ウォームアップキャンペーン](ip-warmup-campaign.md)を作成したら、IP ウォームアッププランの作成を開始できます。

IP ウォームアッププランへのアクセス、作成、編集および削除には、**[!UICONTROL 配信品質コンサルタント]**&#x200B;の役割または IP ウォームアッププラン関連の権限が必要です。

+++配信品質コンサルタントの役割または IP ウォームアッププランに関連する権限を割り当てる方法について説明します

オブジェクトレベルのアクセス制御により、データを保護し、プランを表示および管理するための特定のアクセス権を付与できます。IP ウォームアッププランにラベルが割り当てられていない場合は、すべてのユーザーが表示および編集できるようになります。

**[!UICONTROL IP ウォームアッププランを表示]**&#x200B;権限を付与すると、アクセスは表示と公開のみに制限されますが、**[!UICONTROL IP ウォームアッププランの管理]**&#x200B;権限を割り当てると、ユーザーはプランの表示と編集の両方を行うことができます。

該当する権限を特定の&#x200B;**[!UICONTROL 役割]**&#x200B;に割り当てるには、次の手順に従います。

1. [!DNL Permissions] 製品から、**[!UICONTROL 役割]**&#x200B;メニューに移動して、新しい **[!UICONTROL IP ウォームアップ設定]**&#x200B;権限で更新する役割を選択します。

1. **[!UICONTROL 役割]**&#x200B;ダッシュボードで、「**[!UICONTROL 編集]**」をクリックします。

   ![](assets/ip_permissions_1.png)

1. **[!UICONTROL IP ウォームアッププラン]**&#x200B;リソースをドラッグ＆ドロップして、権限を割り当てます。

1. **[!UICONTROL IP ウォームアップ設定]**&#x200B;リソースドロップダウンから、ユーザーが必要とする権限（**[!UICONTROL IP ウォームアッププランを表示]**、**[!UICONTROL IP ウォームアッププランを管理]**、**[!UICONTROL IP ウォームアップレポートを表示]**）を選択します。必要に応じて、すべて一度に選択できます。

   ![](assets/ip_permissions_2.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

該当する役割を&#x200B;**[!UICONTROL ユーザー]**&#x200B;に割り当てるには、次の手順に従います。

1. [!DNL Permissions] 製品から、**[!UICONTROL 役割]**&#x200B;メニューに移動して、**[!UICONTROL 配信品質コンサルタント]**&#x200B;のビルトインの役割を選択します。

1. **[!UICONTROL 役割]**&#x200B;ダッシュボードで、「**[!UICONTROL ユーザー]**」タブにアクセスします。

   ![](assets/ip_permissions_3.png)

1. 「**[!UICONTROL ユーザーを追加]**」をクリックして、**[!UICONTROL 配信品質コンサルタント]**&#x200B;のビルトインの役割を割り当てます。

   ![](assets/ip_permissions_4.png)

1. 「**[!UICONTROL ユーザー]**」を選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/ip_permissions_5.png)

+++

## IP ウォームアッププランファイルを準備 {#prepare-file}

IP ウォームアップは、正当な送信者としての評判を確立するために、IP およびドメインから主要なインターネットサービスプロバイダー（ISP）に送信されるメールの量を徐々に増やすことで構成されるアクティビティです。

このアクティビティは、通常、配信品質の専門家の支援を受けて実施されます。配信品質の専門家の助けを借りて、業界ドメイン、ユースケース、地域、ISP、その他の様々な要因に基づいて綿密に検討されたプランを準備することができます。

<!--When working with the [!DNL Journey Optimizer] IP warmup feature, this plan takes the form of an Excel file that must contain a number of predefined columns.-->

IP ウォームアッププランを [!DNL Journey Optimizer] インターフェイスで作成する前に、プランにフィードするすべてのデータを Excel テンプレートに入力する必要があります。

* ユーザーインターフェイスから、空白の Excel [IP ウォームアッププランテンプレート](assets/IPWarmupPlan-Template.xlsx)をダウンロードして入力できます。

* また、例として使用できるデータが既に入力されている[サンプルの IP ウォームアッププラン](assets/IPWarmupPlan-Sample.xlsx)をダウンロードすることもできます。

<!--
* From the user interface you can download the blank Excel IP warmup plan template to fill in.

* You can also download a sample IP warmup plan already filled in with some data you can use as an example.
-->

>[!CAUTION]
>
>配信品質コンサルタントと協力して、IP ウォームアッププランファイルが正しく設定されていることを確認します。
>
>必ず、テンプレートで指定された形式を使用してください。

以下は、IP ウォームアッププランを含むファイルの例です。

![](assets/ip-warmup-sample-file.png)

### 「ウォームアッププラン」タブ {#ip-warmup-plan-tab}

IP ウォームアッププランを作成するには、プランにフィードする必要があるデータを最初のタブに入力します。

* 上記の例では、100 万を超えるプロファイルのターゲットボリュームを達成するために、17 日間にわたるプラン（「**実行**」と呼ばれる）が準備されています。

* この計画は 6 つの&#x200B;**フェーズ**&#x200B;を通じて実行され、各フェーズには少なくとも 1 回の実行が含まれます。

* 最大 6 列（ドメイングループに 4 列、**その他**&#x200B;の列に 1 列、 **エンゲージメント日数**&#x200B;の列に 1 列）を含めることができます。この例のプランでは、次の 6 列に分割されます。

   * そのうち 3 列は&#x200B;**標準のドメイングループ**&#x200B;に対応し、プランに使用します（Gmail、Yahoo、Microsoft）。標準のドメイングループはすべて「[OOTB ドメイングループ](#ootb-domain-groups-tab)」タブに一覧表示されます。
   * 1 列は、カスタムドメイングループに対応します（このグループは「[カスタムドメイングループ](#custom-domain-group-tab)」タブを使用して追加する必要があります）。
   * 5 列目の&#x200B;**その他**&#x200B;には、プランで明示的に適用されない他のドメインの残りすべてのアドレスが含まれます。この列はオプションです。省略した場合、メールは指定したドメインにのみ送信されます。
   * 最後の列の&#x200B;**エンゲージメント日数**&#x200B;では、エンゲージメントを追跡または評価する日数を指定できます。

このアイデアでは、各フェーズの実行数を減らしながら、各実行でターゲットアドレスの数を徐々に増やしていきます。

### 「カスタムドメイングループ」タブ {#custom-domain-group-tab}

また、カスタムドメイングループを含めることで、プランに列を追加することもできます。

「**[!UICONTROL カスタムドメイングループ]**」タブをクリックして、新しいドメイングループを定義します。各ドメインに対して、対象となるすべてのサブドメインを追加できます。

>[!IMPORTANT]
>
>各ドメインがそのドメイングループに固有であり、他のドメイングループまたは[標準のドメイングループ](#ootb-domain-groups-tab)と重複していないことを確認します。

例えば、カスタムドメイン Roadrunner を追加する場合、サブドメイン（roadrunner.com、nc.rr.com、tampabay.rr.com、rochester.rr.com など）を含めます。

![](assets/ip-warmup-sample-file-custom.png)

>[!NOTE]
>
>カスタムドメインが必要ない場合は、「**[!UICONTROL カスタムドメイングループ]**」タブを空のままにします。

### 「OOTB ドメイングループ」タブ {#ootb-domain-groups-tab}

IP ウォームアッププランテンプレートの「**OOTB ドメイングループ**」タブには、プランに追加できる標準のすべてのメインドメイングループが含まれます。

![](assets/ip-warmup-sample-file-ootb.png)

>[!NOTE]
>
>このタブにドメイングループが表示されない場合は、対応するタブでカスタムドメイングループを作成する必要があります。[詳細情報](#custom-domain-group-tab)

また、標準のメインドメイングループも以下に示します。

+++ Gmail
gmail.com;google.com;googlemail.com;googlemail.co.uk
+++

+++Microsoft
hotmail.com.tr;live.de;live.ru;live.nl;windowslive.com;live.jp;mts.net;xbox.com;hotmail.fr;hotmail.cl;hotmail.jp;live.cl;live.at;live.com.au;hotmail.co.th;live.hk;hotmail.com.au;hotmail.com;live.com.my;hotmail.co.kr;live.ie;outlook.com.br hotmail.co.il;hotmail.dk;live.co.kr;live.co.uk live.com.mx hotmail.co.uk live.com.sg msn.com hotmail.co.jp live.co.za live.com.pt outlook.com live.com live.com.ar hotmail.com.br hotmail.com.ar;outlook.ie;live.cn;;hotmail.sdk;live.no;live.dk;hotmail.it;live.se;live.jp;hotmail.se;hotmail.ch;live.gr it；電話；hotmail.ca；電話；live.ca;hotmail.de
+++

+++Yahoo
aol.fi;games.com;cs.com;yahoo.com.in;y7mail.com;yahoo.co.uk;yahoo.hu;yahoo.co.hu;yahoo.cn;yahoogroups.com.sg;yahoogroups.com.au;aol.es;yahoo.com.au;yahoo.com.vn;yahoo.ca;aol.hk;aol.co.nz;yahoo.com.br;aolpoland.pl;aolnorge.no;yahoo.ne.jp;yahoo.fi;ymail.com netscape.com yahoo.com.pe yahoo.co.id citlink.net wmconnect.com yahoo.com.jp yahoo.com.hk aol.com.br yahoo.co.kr yahoo.com.ar ygm.com yahoo.co.nz aol.com goowy.com rocketmail.com frontiernet.net aim.com yahoogroups.co.in netscape.net luckymail.com yahoo.co.jp yahoo.com.kr yahoo.co.za verizon.net aol.com.ve aol.com.ar aol.com.co wild4music.com yahoogroups.com.cn yahoo.com.co wow.com yahoo.com yahooxtra.co.nz yahoo.com.mx yahoo.com.ph sky.com aol.com.mx aol.com.au aolchina.com yahoo.com.net yahoo.com.tw talk21.com compuserve.com yahoo.com.sg yahoogroups.com.tw frontier.com yahoo.co.in yahoo.co.il verizon.net.in yahoo.com.tr yahoogroups.com.hk yahoogroups.co.uk yahoo.com.biz yahoo.com.hr aol.co.uk ybb.ne.jp yahoogroups.co.kr yahoo.com.my rogers.com gte.net yahoogroups.com yahoo.co.th yahoo.com.cn love.com bellatlantic.net yahoo.com.ve yahoo.com.ua;;yahol.fi;aolcom.tr;yahoo.si;aol.it;yahoo.es;yahoo.dk;yahoo.ca;yahoo.jp;aol.jp AOL;yahoo.lt;AOL.nl;AOL.BG;ASL;AOL.SE;ASL;yahoo.de;AOL.CL;AOL.DK;AOL.CL;ASL;YAHOO.NO;YAHOO.DE;YAHOO.GR;ASL;YAHOO.CR;AOL.IN;AOL.DE;aol;AOL;DE;DE;DE;DE AOL;AOL;AOL.JP;YAHOO.PT;JAR;yahoo.fr;JAR;yahoo.fr;AOL.pl;AOL.CH;YAHOO.IT;AOL.PL;AOL.RUPPI.IT;YAHOL.CL;;AOL.TW;AOL.TW;AOL.TW;AOL;AOL;aolska;aolska;aolska ol.at;yahoo.pl
+++

+++Apple
mac.com;icloud.com;apple.com;me.com
+++

+++Comcast
comcast.net
+++

+++Orange
voila.com;francetelecom.com;orange.com;orange.fr;wanadoo.fr;voila.fr
+++

+++La Poste
laposte.net
+++

+++Italia Online
inwind.it;blu.it;virgilio.it;giallo.it;iol.it;libero.it
+++

+++WP
wp.pl;o2.pl
+++

+++United Internet
gmx.de;1and1.com;gmx.fr;mail.com;1und1.de;gmx.com;gmx.net;gmx.at;web.de;gmx.ch
+++

+++Bigpond
bigpond.com;bigpond.com.au;bigpond.net;telstra.com;bigpond.net.au
+++

+++Docomo
docomo.ne.jp
+++

+++Softbank
c.vodafone.ne.jp;jp-h.ne.jp;k.vodafone.ne.jp;jp-d.ne.jp;jp-c.ne.jp;t.vodafone.ne.jp;h.vodafone.ne.jp;r.vodafone.ne.jp;q.vodafone.ne.jp;jp-t.ne.jp;jp-q.ne.jp;s.vodafone.ne.jp;jp-s.ne.jp;jp-r.ne.jp;jp-k.ne.jp;;n.vodafone.ne.jp;d.vodafone.ne.jp;softbank.ne.jp;jp-n.ne.jp;;
+++

+++KDDI
au.com;ezweb.ne.jp;uqmobile.jp
+++

### 例 {#example}

次の 2 つのカスタムドメイングループがあるとします。

* 1 つは Hotmail ドメイン専用です。
* もう 1 つは、ドメイングループ Microsoft からの他のすべてのドメイン用です（したがって、すべての Hotmail ドメインを除く）。

Hotmail 以外のドメインとドメイングループ Microsoft からのドメインは、**[!UICONTROL その他]**&#x200B;列に集められます。

1. 「**[!UICONTROL カスタムドメイングループ]**」タブで、**Hotmail** ドメイングループを作成します。

1. 同じ行にすべての Hotmail ドメインを追加します。

   [「OOTB ドメイングループ」タブ](#ootb-domain-groups-tab)のセクションにリストされる Hotmail のすべてのドメインを[コピーして貼り付け](#copy-paste)ることができます。

1. 別の行を追加します。

1. **Microsoft_X** ドメイングループを作成します。

1. Hotmail 以外の Microsoft ドメインをすべて同じ行に追加します。同様に、上のリストから[コピーして貼り付け](#copy-paste)ることもできます。

1. 「**[!UICONTROL IP ウォームアッププラン]**」タブに戻ります。

1. 3 列を作成します。1 列は、**Hotmail** 用に、もう 1 列は、**Microsoft_X** 用に、そしてもう 1 列は、**その他**&#x200B;用に作成します。

1. 必要に応じて、列に入力します。

<!--Only the domain groups listed in the **[!UICONTROL IP Warmup Plan]** tab will be taken into account.-->

### デフォルトのドメインをコピー＆ペースト {#copy-paste}

例えば、すべての Hotmail ドメインを含むカスタムドメイングループを作成する場合は、[IP ウォームアッププランテンプレート](assets/IPWarmupPlan-Template.xlsx)の「**OOTB ドメイングループ**」タブ、または[上記](#ip-warmup-plan-tab)のリストからドメインをコピーして貼り付けることができます。

次に、Excel コンバージョンツールを使用して、テキストを列に変換します。

1. **[!UICONTROL データ]**／**[!UICONTROL テキストから列へ…]**&#x200B;を選択し、「**[!UICONTROL 区切り]**」、「**[!UICONTROL 次へ]**」の順に選択します。

1. 「**[!UICONTROL セミコロン]**」を選択し、「**[!UICONTROL 次へ]**」および「**[!UICONTROL 終了]**」をクリックします。

各ドメインが同じ行の異なる列に表示されるようになりました。

## IP ウォームアッププランへのアクセスと管理 {#manage-ip-warmup-plans}

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスします。これまでに作成した IP ウォームアッププランがすべて表示されます。

   ![](assets/ip-warmup-filter-list.png)

1. ステータスに基づいてフィルタリングできます。 様々なステータスを以下に示します。

   * **未開始**：実行はまだアクティブ化されていません。 [詳細情報](ip-warmup-execution.md#define-runs)
   * **ライブ**：最初のフェーズの最初の実行が正常にアクティブ化されると、プランは直ちにこのステータスに変わります。[詳細情報](ip-warmup-execution.md#define-runs)
   * **完了**：プランは完了とマークされています。<!--This option is only available if all the runs in the plan are in **[!UICONTROL Completed]** or **[!UICONTROL Draft]** status (no run can be **[!UICONTROL Live]**).-->  [詳細情報](ip-warmup-execution.md#mark-as-completed)
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
>abstract="IP ウォームアップフェーズやターゲットプロファイル数など、プランに必要なすべてのデータを Excel テンプレートに入力し、ここにアップロードします。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/implement-ip-warmup-plan/ip-warmup-plan.html?lang=ja#prepare-file" text="IP ウォームアッププランファイルを準備"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="マーケティング設定の選択"
>abstract="IP ウォームアッププランに関連付けるキャンペーンで選択した設定と同じ設定を選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="チャネル設定の指定"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="IP ウォームアップキャンペーンを作成"

IP ウォームアッププランを作成するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスし、「**[!UICONTROL IP ウォームアッププランを作成]**」をクリックします。

   ![](assets/ip-warmup-create-plan.png)

1. IP ウォームアッププランの詳細（名前と説明）を入力します。

   ![](assets/ip-warmup-plan-details.png)

1. ウォームアップする[設定](channel-surfaces.md)を選択します。選択できるのはマーケティング設定のみです。[詳しくは、メールタイプを参照してください](../email/email-settings.md#email-type)

   >[!NOTE]
   >
   >IP ウォームアッププランに関連付けるキャンペーンは、同じ設定を使用する必要があります。[IP ウォームアップキャンペーンの作成方法を学ぶ](ip-warmup-campaign.md)

1. IP ウォームアッププランを含む Excel ファイルをアップロードします。[詳細情報](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

   >[!NOTE]
   >
   >アップロードに失敗した場合は、正しい形式とファイル形式（.xls または.xlsx）を使用していることを確認してください。アドビが提供する[テンプレート](assets/IPWarmupPlan-Template.xlsx)を使用します。

1. 「**[!UICONTROL 作成]**」をクリックします。アップロードしたファイルに定義されているすべてのフェーズ、実行、列、およびそれらのコンテンツは、[!DNL Journey Optimizer] インターフェイスに自動的に表示されます。

   ![](assets/ip-warmup-plan-uploaded.png)

   >[!NOTE]
   >
   >**[!UICONTROL ターゲット]**&#x200B;列には、各実行のターゲットとなるすべてのプロファイルの合計が表示されます。つまり、**その他**&#x200B;列（存在する場合）を含む、定義した各ドメイングループのすべてのプロファイルのことです。

これで、IP ウォームアッププランを実行する準備が整いました。[詳細情報](ip-warmup-execution.md)
