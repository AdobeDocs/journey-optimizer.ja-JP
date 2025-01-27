---
solution: Journey Optimizer
product: journey optimizer
title: メール設定の指定
description: チャネル設定レベルでメールを設定する方法を学ぶ
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: 設定, メール, 設定
exl-id: 13536962-7541-4eb6-9ccb-4f97e167734a
source-git-commit: 8559fce278974dcf18ba038996fd65b9f72400f4
workflow-type: tm+mt
source-wordcount: '2801'
ht-degree: 96%

---

# メール設定の指定 {#email-settings}

メールの作成を開始するには、メッセージに必要なすべての技術的パラメーターを定義するメールチャネル設定を指定する必要があります。[設定の作成方法を学ぶ](../configuration/channel-surfaces.md)

>[!NOTE]
>
>評判を保持し、配信品質を向上させるには、メール設定を作成する前にメールの送信に使用するサブドメインを設定します。[詳細情報](../configuration/about-subdomain-delegation.md)

以下で詳しく説明するように、チャネル設定の専用セクションでメール設定を定義します。

![](assets/surface-email-settings.png){width="50%" align="left"}

メール設定は、次のロジックに従って、通信を送信するためにピックアップされます。

* バッチジャーニーの場合、メールサーフェスの設定が行われる前に既に開始されていたバッチ実行には適用されません。変更は、次回の繰り返し時または新しい実行時にピックアップされます。

* トランザクションメッセージの場合、変更は次の通信で直ちにピックアップされます（遅延は 5 分以内です）。

>[!NOTE]
>
>更新されたメール設定は、設定が使用されているジャーニーまたはキャンペーンで自動的にピックアップされます。

## メールタイプ {#email-type}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_emailtype"
>title="メールタイプの定義"
>abstract="この設定を使用する際に送信されるメールのタイプを選択します。ユーザーの同意が必要なプロモーションメール用の「マーケティング」または、特定のコンテキストで購読解除済みのプロファイルにも送信できる非商用メール用の「トランザクション」です。"

「**メールタイプ**」セクションで、設定のメッセージのタイプ（「**[!UICONTROL マーケティング]**」または「**[!UICONTROL トランザクション]**」）を選択します。

* 小売店の毎週のプロモーションなど、プロモーションメールの場合は、「**マーケティング**」を選択します。これらのメッセージには、ユーザーの同意が必要です。

* 注文確認、パスワードリセット通知、配信情報など、非商用メールの場合は、「**トランザクション**」を選択します。これらのメールは、アドビからのお知らせの&#x200B;**登録解除**&#x200B;したプロファイルに送信できます。これらのメッセージは、特定のコンテキストでのみ送信できます。

メッセージの作成時に、メールに対して選択したカテゴリに一致する有効なチャネル設定を選択する必要があります。

## サブドメイン {#subdomains}

メールの送信に使用するサブドメインを選択します。

>[!NOTE]
>
>メール設定の制御を高めるために、動的サブドメインを定義できます。[詳細情報](../email/surface-personalization.md#dynamic-subdomains)

ドメインのレピュテーションを保持し、IP ウォーミングプロセスを高速化し、配信品質を向上させるには、送信サブドメインをアドビにデリゲートします。[詳細情報](../configuration/about-subdomain-delegation.md)

## IP プールの詳細 {#ip-pools}

設定に関連付ける IP プールを選択します。[詳細情報](../configuration/ip-pools.md)

![](assets/surface-subdomain-ip-pool.png){width="50%" align="left"}

選択した IP プールが[編集中](../configuration/ip-pools.md#edit-ip-pool)（**[!UICONTROL 処理中]**&#x200B;ステータス）で、選択したサブドメインに関連付けられていない場合は、設定の作成を続行できません。それ以外の場合は、IP プール／サブドメインの関連付けのうち、最も古いバージョンが引き続き使用されます。その場合は、設定をドラフトとして保存し、IP プールが&#x200B;**[!UICONTROL 成功]**&#x200B;ステータスになったら再試行します。

>[!NOTE]
>
>非実稼動環境の場合、アドビは、標準のテストサブドメインの作成や、共有送信 IP プールへのアクセスを許可しません。[独自のサブドメインをデリゲート](../configuration/delegate-subdomain.md)して、組織に割り当てられたプールの IP を使用する必要があります。

IP プールが選択された後、IP プールのドロップダウンリストの下に表示される IP アドレスにカーソルを合わせると、PTR 情報が表示されます。[PTR レコードの詳細情報](../configuration/ptr-records.md)

>[!NOTE]
>
>PTR レコードが設定されていない場合は、アドビ担当者に問い合わせてください。

## リスト登録解除{#list-unsubscribe}

>[!CONTEXTUALHELP]
>id="ajo_email_config_unsubscribe_custom"
>title="カスタムのリスト – 登録解除エンドポイントを入力"
>abstract="Adobe外で同意を管理している場合は、「**顧客管理**」オプションを選択して、カスタム購読解除メールアドレスと独自のワンクリック購読解除 URL を入力します。 この場合、Adobeには登録解除情報が保存されないことに注意してください。 顧客の同意情報の所有者は、同意データを管理し、Journey Optimizerにプッシュする責任を負います。"

<!--Do not modify - Legal Review Done -->

リストから[サブドメインを選択](#subdomains-and-ip-pools)すると、「**[!UICONTROL リスト登録解除を有効にする]**」オプションが表示されます。

このオプションはデフォルトで有効になっており、次のようなワンクリック登録解除 URL がメールヘッダーに含まれます。

![](assets/preset-list-unsubscribe-header.png)

>[!NOTE]
>
>このオプションを無効にした場合、メールヘッダーにワンクリック購読解除 URL は表示されません。

**[!UICONTROL 同意レベル]**&#x200B;ドロップダウンリストから同意レベルを選択できます。チャネルまたはプロファイル ID に固有のものにすることができます。この設定に基づいて、ユーザーがメールのヘッダーにあるリスト登録解除 URL を使用して登録解除すると、Adobe Journey Optimizer においてチャネルレベルまたは ID レベルで同意が更新されます。

リスト登録解除ヘッダーには 、2 つの機能があり、いずれかまたは両方の機能をオフにしない限り、デフォルトで有効になります。

![](assets/surface-list-unsubscribe-mailto.png){width="80%"}

<!--![](assets/surface-list-unsubscribe.png){width="80%"}-->

* **宛先（登録解除）**&#x200B;アドレスは、登録解除リクエストが自動処理にルーティングされる宛先アドレスです。

  Journey Optimizer の場合、登録解除のメールアドレスは、[選択したサブドメイン](#subdomains-and-ip-pools)に基づいてチャネル設定に表示されるデフォルトの&#x200B;**宛先（登録解除）**&#x200B;アドレスです。

* **ワンクリック登録解除 URL**&#x200B;は、デフォルトでは、チャネル設定を行ったサブドメインに基づいて、ワンクリックオプトアウト URL で生成されたリスト登録解除ヘッダーです。

<!--
    >[!AVAILABILITY]
    >
    >One-click Unsubscribe URL Header will be available in Adobe Journey Optimizer starting June 3, 2024.
    >
-->

**[!UICONTROL 宛先（登録解除）]**&#x200B;機能と&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** 機能はオプションです。

デフォルトで生成されたワンクリック登録解除 URL を使用しない場合は、この機能をオフにできます。「**[!UICONTROL リスト登録解除を有効にする]**」オプションがオンに切り替わり、**[!UICONTROL ワンクリック登録解除 URL]** 機能がオフになっているシナリオで、この設定を使用して作成されたメッセージに[ワンクリックオプトアウトリンク](../email/email-opt-out.md#one-click-opt-out)を追加する場合、リスト登録解除ヘッダーは、メールの本文に挿入したワンクリックオプトアウトリンクをピックアップし、それをワンクリック登録解除 URL 値として使用します。

![](assets/preset-list-unsubscribe-opt-out-url.png)

>[!NOTE]
>
>メッセージコンテンツにワンクリックオプトアウトリンクを追加せず、チャネル設定でデフォルトの **[!UICONTROL ワンクリック購読解除 URL]** がオフになっている場合、リストの購読解除ヘッダーの一部としてメールヘッダーに渡される URL はありません。

メッセージにおける登録解除機能の管理について詳しくは、[この節](../email/email-opt-out.md#unsubscribe-header)を参照してください。

<!--![](assets/surface-list-unsubscribe-custom.png){width="80%"}-->

## ヘッダーパラメーター {#email-header}

「**[!UICONTROL ヘッダーパラメーター]**」セクションでは、その設定を使用して送信されるメールのタイプに関連付けられた送信者の名前とメールアドレスを入力します。

>[!NOTE]
>
>メール設定の制御を高めるには、ヘッダーパラメーターをパーソナライズできます。[詳細情報](../email/surface-personalization.md#personalize-header)

* **[!UICONTROL 送信者名]**：送信者の名前（会社のブランド名など）。
* **[!UICONTROL 送信者のメール]**：コミュニケーションに使用するメールアドレス。
* **[!UICONTROL 返信先（名前）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用する名前。
* **[!UICONTROL 返信先（メール）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用するメールアドレス。[詳細情報](#reply-to-email)
* **[!UICONTROL エラーメール]**：メールを配信してから数日後に ISP で発生したすべてのエラー（非同期バウンス）は、このアドレスで受信されます。また、このアドレスでは、不在通知とチャレンジ応答も受信されます。

  アドビにデリゲートされていない特定のメールアドレスで不在通知とチャレンジ応答を受信したい場合は、[転送プロセス](#forward-email)を設定する必要があります。その場合は、このインボックスにランディングするメールを処理するために、手動または自動のソリューションを用意してください。

>[!CAUTION]
>
>**[!UICONTROL 送信者メール]**&#x200B;および&#x200B;**[!UICONTROL エラーメール]**&#x200B;アドレスでは、現在選択されている[デリゲートされたサブドメイン](../configuration/about-subdomain-delegation.md)を使用する必要があります。例えば、デリゲートされたサブドメインが *marketing.luma.com* の場合は、*contact@marketing.luma.com* と *error@marketing.luma.com* を使用できます。

![](assets/preset-header.png){width="80%"}

>[!NOTE]
>
>アドレスは、文字（A ～ Z）で始まる必要があり、英数字のみを使用できます。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

### メールへの返信 {#reply-to-email}

**[!UICONTROL （メール）への返信]**&#x200B;アドレスを定義する場合、有効なアドレスで、正しい形式でタイプミスがない限り、任意のメールアドレスを指定できます。

返信に使用するインボックスは、**[!UICONTROL エラーメール]**&#x200B;アドレスで受信される不在通知とチャレンジ応答を除く、すべての返信メールを受信します。

返信を適切に管理するには、次のレコメンデーションに従ってください。

* メール設定を使用して、送信されるすべての返信メールを受信するのに十分な受信容量が専用のインボックスにあることを確認します。インボックスがバウンスを返す場合、顧客からの返信が受信されない場合があります。

* 返信には個人を特定できる情報（PII）が含まれている可能性があるので、プライバシーとコンプライアンスの義務に留意して返信を処理する必要があります。

* 返信インボックスでメッセージをスパムとしてマークしないでください。このアドレスに送信される他のすべての返信に影響を与えます。

さらに、**[!UICONTROL 返信先（メール）]**&#x200B;アドレスを定義する場合は、有効な MX レコード設定を持つサブドメインを使用します。使用しない場合、メール設定の処理が失敗します。

メール設定の送信時にエラーが発生した場合は、入力したアドレスのサブドメインに対して MX レコードが設定されません。対応する MX レコードの設定について管理者に問い合わせるか、有効な MX レコード設定を持つ別のアドレスを使用します。

>[!NOTE]
>
>入力したアドレスのサブドメインがアドビに[完全にデリゲート](../configuration/delegate-subdomain.md#full-subdomain-delegation)されたドメインである場合は、アドビアカウント担当者にお問い合わせください。

### メールの転送 {#forward-email}

デリゲートされたサブドメインの [!DNL Journey Optimizer] で受信したすべてのメールを特定のメールアドレスに転送するには、アドビカスタマーケアにお問い合わせください。

>[!NOTE]
>
>**[!UICONTROL 返信先（メール）]**&#x200B;アドレスに使用するサブドメインがアドビにデリゲートされていない場合、このアドレスでは転送は機能しません。

以下を指定する必要があります。

* 選択した転送メールアドレス。転送メールアドレスドメインは、アドビにデリゲートされたサブドメインと同じにはできないことに注意してください。
* サンドボックス名。
* 転送メールアドレスを使用する設定名またはサブドメイン。
  <!--* The current **[!UICONTROL Reply to (email)]** address or **[!UICONTROL Error email]** address set at the channel configuration level.-->

>[!NOTE]
>
>サブドメインごとに転送メールアドレスを 1 つだけ指定できます。したがって、複数の設定で同じサブドメインを使用する場合は、それらすべてに同じ転送メールアドレスを使用する必要があります。

転送メールアドレスはアドビが設定します。これには 3～4 日かかる場合があります。

完了すると、**[!UICONTROL 返信先（メール）]**&#x200B;および&#x200B;**[!UICONTROL エラーメール]**&#x200B;アドレスで受信したすべてのメッセージが、指定した特定のメールアドレスに転送されます。

## BCC メール {#bcc-email}

[!DNL Journey Optimizer] から送信された電子メールの同一のコピー（またはブラインドカーボンコピー）を BCC インボックスに送信できます。BCC インボックスは、コンプライアンスやアーカイブの目的で保存されます。

これを行うには、チャネル設定レベルの「**[!UICONTROL BCC メール]**」オプション機能を有効にします。[詳細情報](../configuration/archiving-support.md#bcc-email)

![](assets/preset-bcc.png)

さらに、**[!UICONTROL BCC メール]**&#x200B;アドレスを定義する場合は、有効な MX レコード設定を持つサブドメインを使用します。使用しない場合、メール設定の処理が失敗します。

メール設定の送信時にエラーが発生した場合は、入力したアドレスのサブドメインに対して MX レコードが設定されません。対応する MX レコードの設定について管理者に問い合わせるか、有効な MX レコード設定を持つ別のアドレスを使用します。

## 抑制されたメールアドレスへの送信 {#send-to-suppressed-email-addresses}

>[!CONTEXTUALHELP]
>id="ajo_surface_suppressed_addresses"
>title="抑制リストの優先順位の上書き"
>abstract="スパムの苦情が原因でメールアドレスが Adobe Journey Optimizer の抑制リストに登録されている場合でも、プロファイルへのトランザクションメッセージの送信を決定することができますこのオプションはデフォルトでは無効です。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/monitor-reputation/manage-suppression-list.html?lang=ja" text="抑制リストの管理"

>[!IMPORTANT]
>
>このオプションは、**[!UICONTROL トランザクション]**&#x200B;のメールタイプを選択している場合にのみ使用できます。[詳細情報](#email-type)

[!DNL Journey Optimizer] では、ハードバウンス、ソフトバウンスおよびスパムの苦情としてマークされたすべてのメールアドレスは、自動的に[抑制リスト](../configuration/manage-suppression-list.md)に収集され、ジャーニーやキャンペーンでの送信から除外されます。

ただし、ユーザーからのスパムの苦情によりメールアドレスが抑制リストに登録されている場合でも、**トランザクション**&#x200B;タイプのメッセージをプロファイルに送信する決定をすることができます。

実際、トランザクションメッセージには、通常、注文の確認やパスワードのリセット通知など、有用で期待される情報が含まれます。したがって、顧客がマーケティングメッセージのうち 1 件をスパムとして報告した場合でも、ほとんどの場合、このタイプの非商用メールを顧客に受信してもらうことが望まれます。

スパムの苦情によって抑制されたメールアドレスをトランザクションメッセージオーディエンスに含めるには、「**[!UICONTROL 抑制されたメールアドレスに送信]**」セクションで該当するオプションを選択します。

![](assets/preset-suppressed-email-addresses.png)

>[!NOTE]
>
>このオプションはデフォルトでは無効です。

配信品質のベストプラクティスとして、このオプションは、オプトアウトした顧客が連絡を受けないように、デフォルトで無効になっています。ただし、このデフォルトオプションを変更すると、顧客にトランザクションメッセージを送信できるようになります。

このオプションを有効にすると、顧客がマーケティングメールをスパムとしてマークしても、その顧客は現在の設定を使用してトランザクションメッセージを受信することができます。配信品質のベストプラクティスに従って、必ずオプトアウト設定を管理してください。

## シードリスト {#seed-list}

>[!CONTEXTUALHELP]
>id="ajo_surface_seed_list"
>title="シードリストを追加"
>abstract="希望するシードリストを選択して、特定の内部アドレスをオーディエンスに自動的に追加します。これらのシードアドレスは配信の実行時に含まれ、保証の目的でこのアドレスにメッセージのコピーが送られます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/seed-lists.html?lang=ja#use-seed-list" text="シードリストとは"

[!DNL Journey Optimizer] のシードリストを使用すると、配信に特定のメールシードアドレスを自動的に含めることができます。[詳細情報](../configuration/seed-lists.md)

>[!CAUTION]
>
>現在、この機能はメールチャネルにのみ適用されます。

「**[!UICONTROL シードリスト]**」セクションで、自分に関連するリストを選択します。シードリストの作成方法については、[この節](../configuration/seed-lists.md#create-seed-list)を参照してください。

![](../configuration/assets/seed-list-surface.png){width="80%"}

>[!NOTE]
>
>一度に選択できるシードリストは 1 つのみです。

現在の設定をキャンペーンまたはジャーニーで使用する場合、選択したシードリストのメールアドレスは配信の実行時に含まれ、保証の目的でこのアドレスに配信のコピーが送られます。

キャンペーンまたはジャーニーでのシードリストの使用方法について詳しくは、[この節](../configuration/seed-lists.md#use-seed-list)を参照してください。

## メールの再試行パラメーター {#email-retry}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_retryperiod"
>title="再試行期間の調整"
>abstract="一時的なソフトバウンスエラーが原因でメール配信が失敗した場合は、3.5 日間（84 時間）再試行が実行されます。このデフォルトの再試行期間は、ニーズに合わせて調整できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/monitor-reputation/retries.html?lang=ja" text="再試行について"

**メールの再試行パラメーター**&#x200B;を設定できます。

![](assets/preset-retry-parameters.png)

デフォルトでは、[再試行期間](../configuration/retries.md#retry-duration)は 84 時間に設定されていますが、必要に応じてこの設定を調整できます。

次の範囲内の整数値（時間または分）を入力する必要があります。

* マーケティングメールの場合、再試行期間の下限は 6 時間です。
* トランザクションメールの場合、再試行期間の下限は 10 分です。
* どちらのメールタイプでも、再試行期間の上限は 84 時間（5040 分）です。

再試行の詳細については、[この節](../configuration/retries.md)を参照してください。

## URL トラッキング {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="URL トラッキングパラメーターの定義"
>abstract="このセクションを使用すると、メールコンテンツに存在する URL にトラッキングパラメーターを自動的に追加できます。この機能はオプションです。"

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_url_preview"
>title="URL トラッキングパラメーターのプレビュー"
>abstract="メールコンテンツに存在する URL にトラッキングパラメーターを追加する方法を確認します。"

**[!UICONTROL URL トラッキングパラメーター]**&#x200B;を使用し、チャネルをまたいでマーケティング活動の有効性を測定することができます。この機能はオプションです。

このセクションで定義されたパラメーターは、メールメッセージコンテンツに含まれる URL の末尾に追加されます。その後、これらのパラメーターを Adobe Analytics や Google Analytics などの web 分析ツールで取得し、様々なパフォーマンスレポートを作成できます。

「**[!UICONTROL 新しいパラメーターを追加]**」ボタンを使用して最大 10 個のトラッキングパラメーターを追加できます。

![](assets/preset-url-tracking.png){width="80%"}

URL トラッキングパラメーターを設定するには、目的の値を&#x200B;**[!UICONTROL 名前]**&#x200B;および&#x200B;**[!UICONTROL 値]**&#x200B;フィールドに直接入力することができます。

また、[パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)を使用して各&#x200B;**[!UICONTROL 値]**&#x200B;フィールドを編集することもできます。「編集」アイコンをクリックして、エディターを開きます。ここから、利用可能なコンテキスト属性を選択したり、テキストを直接編集したりできます。

![](assets/preset-url-tracking-editor.png)

パーソナライゼーションエディターでは、次の事前定義済みの値を使用できます。

* **ソースアクション ID**：ジャーニーまたはキャンペーンに追加されたメールアクションの ID。

* **ソースアクション名**：ジャーニーまたはキャンペーンに追加されたメールアクションの名前。

* **ソース ID**：メールの送信に使用されたジャーニーまたはキャンペーンの ID。

* **ソース名**：メールの送信に使用されたジャーニーまたはキャンペーンの名前。

* **ソースバージョン ID**：メールの送信に使用されたジャーニーまたはキャンペーンのバージョンの ID。

* **オファー ID**：メールで使用されるオファーの ID。

>[!NOTE]
>
>テキスト値の入力と、パーソナライゼーションエディターからのコンテキスト属性の使用を組み合わせることができます。各「**[!UICONTROL 値]**」フィールドには、5 KB の制限までの文字数を含めることができます。

<!--You can drag and drop the parameters to reorder them.-->

以下に、Adobe Analytics および Google Analytics 互換 URL の例を示します。

* Adobe Analytics 互換 URL：`www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics 互換 URL：`www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

結果のトラッキング URL を動的にプレビューできます。パラメーターを追加、編集、または削除するたびに、プレビューが自動的に更新されます。

![](assets/preset-url-tracking-preview.png)

>[!NOTE]
>
>また、メールコンテンツ内に存在するリンクに動的にパーソナライズされたトラッキングパラメーターを追加することもできますが、設定レベルでは追加できません。これは、E メールデザイナーを使用してメッセージを作成する際に行う必要があります。[詳細情報](message-tracking.md#url-tracking)

## 実行アドレス {#execution-address}

>[!CONTEXTUALHELP]
>id="ajo_email_config_execution_address"
>title="使用するデフォルトの実行アドレスの上書き"
>abstract="使用できるメールアドレスがデータベース内に複数ある（個人用、仕事用など）場合、優先して送信するアドレスを選択できます。プライマリアドレスはサンドボックスレベルで定義されますが、ここでは、この特定のメール設定のデフォルト設定を上書きできます。"

プロファイルをターゲットにする際に、使用できるメールアドレスがデータベース内に複数ある（仕事用のメールアドレス、個人用のメールアドレスなど）場合があります。

その場合、[!DNL Journey Optimizer] は、サンドボックスレベルで&#x200B;**[!UICONTROL 実行フィールド]**&#x200B;に指定されたアドレスを使用して、優先してプロファイルサービスから使用するメールアドレスを決定します。[詳細情報](../configuration/primary-email-addresses.md)

>[!NOTE]
>
>現在デフォルトで使用されているフィールドを確認するには、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL 一般設定]**／**[!UICONTROL 実行フィールド]**&#x200B;メニューにアクセスします。

ただし、このデフォルトの実行フィールドは、メールチャネル設定レベルで変更できます。その後、この設定を特定のキャンペーンやジャーニーに適用できます。

これを行うには、「**[!UICONTROL 配信アドレス]**」フィールドを編集し、使用できるメールタイプの XDM フィールドのリストから項目を選択します。

![](assets/email-config-delivery-address.png)

実行フィールドは更新され、その後プライマリアドレスとして使用されます。サンドボックスレベルの一般設定が上書きされます。
