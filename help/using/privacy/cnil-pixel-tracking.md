---
solution: Journey Optimizer
product: journey optimizer
title: メール追跡ピクセルに関するCNIL ガイダンス
description: メール追跡ピクセルに関するCNILの更新されたガイダンスと、コンプライアンスの取り組みをサポートできるAdobe Journey Optimizerコントロールについて説明します。
feature: Privacy, Consent Management
topic: Content Management
role: User
level: Intermediate
keywords: CNIL、トラッキング、ピクセル、電子メール、同意、オプトアウト、プライバシー
source-git-commit: b55af0fe5510f37049713fe8d0b7a2ac73516323
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 1%

---


# メール追跡ピクセルに関するCNILの最新のガイダンスについて {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**このページでは、** CNILの2026年4月の電子メールトラッキングピクセルに関する推奨事項について説明します。また、コンプライアンスの取り組みをサポートするAdobe Journey Optimizer コントロール（開封済みトラッキングトグル、リンクレベルのトラッキング、同意管理、オプトアウトの仕組み、および抑制）についてご紹介します。

>[!ENDSHADEBOX]

このページは、情報提供のみを目的としています。 法的アドバイスではなく、適用法の遵守を保証するものではありません。 以下に説明するAdobe Journey Optimizer製品の機能は、適切に設定および操作されたビルディングブロックであり、コンプライアンスの実装をサポートする場合があります。 各顧客は、適用法に基づく義務を決定し、遵守する責任があります。

## 概要 {#overview}

2026年4月14日、フランスのデータ保護機関である&#x200B;*Commission Nationale de l&#39;Informatique et des Libertés* （CNIL）は、メール内でのトラッキングピクセルの使用に関する[の推奨事項](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)を公開しました。 このガイダンスでは、同意が必要なタイミングを明確にし、メールのピクセル追跡における適切な同意管理の重要性を強調しています。 このポリシーは、フランスに拠点を置く購読者にメールを配信するエンティティの送信方法に影響を与える可能性があります。

CNILは、企業がトラッキングピクセルの存在、目的、およびユーザーのオプトアウト権をメール受信者（「ユーザー」）に通知するための推奨日から3か月間を提供しました。 この移行期間中、顧客はユーザーにピクセルトラッキングについて通知し、必要に応じてオプトアウトを提供することが期待されます。 **CNILは、2026年7月14日以降に強制実行アクティビティを開始する予定です。**

CNILなどの規制当局がトラッキングのピクセルや関連する問題に関するガイダンスを明確にするため、Adobeは引き続きアップデートを監視し、Adobe Journey Optimizerを含むメールマーケティングをサポートするAdobe製品の技術的能力をお客様に通知します。

Adobe Journey Optimizerには、配信レベルでのオープントラッキングの管理に役立つコントロールが用意されています。 顧客は、適用されるCNIL ガイダンスやその他の法律に基づいて独自のコンプライアンス義務を決定する責任を負いますが、これらの機能は顧客コンプライアンスの取り組みをサポートする可能性があります。

### メールトラッキングピクセルとは {#tracking-pixel}

電子メールトラッキングピクセルは、電子メールのHTMLに埋め込まれた1x1の透明画像です。 受信者のメールクライアントがその画像を読み込むと、ピクセルはタイムスタンプ、デバイスの種類、メールクライアント、場合によってはIP アドレスなどのデータを記録するサーバーにping送信し、おおよその場所を確認します。 その後、そのログは受信者のレコードに関連付けられ、マーケターはメールが開封されたかどうかを確認できます。

### カスタマーサポート {#support}

上記の変更の導入についてサポートを求めるお客様は、既存のAdobe エコシステムを利用できます。 参照されているAdobe機能に関する技術的な質問については、カスタマーサクセスマネージャーまたはテクニカルアカウントマネージャーにお問い合わせください。

## メールトラッキングに関連するAdobe Journey Optimizer機能 {#ajo-functionality}

Adobe Journey Optimizerには、CNIL ガイダンスの要素に対処するのに役立つ、いくつかのネイティブコントロールが用意されています。 以下の節では、関連する製品機能について説明します。

### メールタイプ分類 {#email-type}

Adobe Journey Optimizerでは、あらゆるメールチャネル設定をマーケティングとトランザクションのどちらかに分類します。 この分類は、送信前に購読者の同意が必要かどうかを判断します。

* **マーケティングメール**：オプトインした購読者にプロモーションコミュニケーションを送信しました。 ユーザーの同意が必要です。 これらのメールでは、抑制とオプトアウトの設定が自動的に尊重されます。
* **トランザクションメール**：非商用コミュニケーション（注文確認、パスワードリセットなど）。 これらの電子メールは、適用法に従って、マーケティングコミュニケーションを登録解除したプロファイルに送信できます。

電子メールの種類は、[&#x200B; チャネル設定](../email/email-settings.md#email-type) レベルで設定されます。 ジャーニーまたはキャンペーンでメールを作成する場合、作成者は、メールの種類がコミュニケーションの性質と一致するチャネル設定を選択する必要があります。 この分類は、配信前に適用される同意チェックを通知します。

### トラッキングコントロールを開く {#open-tracking}

Adobe Journey Optimizerを使用すると、マーケターは個々のメッセージレベルでオープントラッキング（1x1 ピクセル）を制御できます。 ジャーニーまたはキャンペーンで電子メールを作成する場合、メッセージプロパティパネルで2つのトラッキングオプションを使用できます。

* **[!UICONTROL 電子メールが開く]**：開封追跡ピクセルを電子メールに含めるかどうかを制御します。 このオプションは、デフォルトでは有効になっています。
* **[!UICONTROL 電子メールのクリック]**: リンクのクリックを追跡するかどうかを制御します。 このオプションはデフォルトでも有効になっています。

特定の電子メールの開封追跡を無効にするには、メッセージの作成時に「**[!UICONTROL 電子メールを開く]**」オプションのチェックを外します。 このオプションを無効にすると、その配信に対して開いているトラッキングデータが収集されなくなります。 フランスのサブスクライバーに送信する組織の場合は、適用日前にすべてのアクティブなジャーニーとキャンペーンのオープン トラッキング設定を確認します。

<!--
EDITORIAL NOTE – ENGINEERING CONFIRMATION NEEDED before publish:
Clarify whether unchecking "Email opens" fully removes the 1x1 tracking pixel from the delivered HTML, or whether the pixel is still present in the HTML but open data is suppressed at the data processing layer only. The current wording ("prevents open tracking data from being collected") is intentionally neutral. If the pixel is removed: update to state this explicitly. If the pixel remains but data is not processed: reword to make that distinction clear, to avoid misleading customers seeking CNIL compliance.
-->

[メッセージを追跡する方法を学ぶ](../email/message-tracking.md)

### リンクレベルのトラッキング管理 {#link-tracking}

Adobe Journey Optimizerの電子メールDesignerでは、メッセージごとの開封トラッキングトグル以外にも、トラッキングするURLを詳細に制御できます。 作成者は、メールDesignerの&#x200B;**[!UICONTROL リンク]** パネルを使用して、すべてのトラッキング済みURLをメッセージで表示し、各リンクのトラッキングモードを個別に設定できます。

各リンクで使用できるトラッキングモードには、次のものがあります。

* **トラッキング対象**：この URL のトラッキングを有効化します。
* **オプトアウト**：このURLをオプトアウト URLまたは購読解除URLとして指定します。
* **ミラーページ**：このURLをミラーページリンクとして指定します。
* **なし**: メッセージレベルの設定に関係なく、このURLに対してトラッキングがアクティブ化されることはありません。

特定のリンクを&#x200B;**Never**&#x200B;に設定すると、メッセージレベルのトラッキングが有効になっている場合でも、特定のURLがトラッキングされないようにすることができます。

[E メール Designerでのトラッキングの管理方法を説明します](../email/message-tracking.md#manage-tracking)

### 同意の取得と管理 {#consent-management}

Adobe Journey Optimizerは、Adobe Experience Platform （AEP） [同意と環境設定スキーマ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja){target="_blank"}を通じて同意を処理します。 同意設定はプロファイルレベルで保存され、ジャーニーおよびキャンペーンの実行中に自動的に適用されます。

メールトラッキングに関連する主な同意属性には、次のようなものがあります。

* **`consents.marketing.email.val`**: プライマリメールマーケティングの同意フィールド。 値`y`はオプトインを示し、`n`はオプトアウトを示します。 空の値は、デフォルトでは同意として扱われます（このデフォルトはオンボーディング時に変更できます）。

### オプトアウトと離脱の仕組み {#opt-out}

Adobe Journey Optimizerでは、購読者がコミュニケーションをオプトアウトし、顧客の嗜好を管理するための複数の仕組みを提供しています。これらの仕組みにより、Adobe Experience Platformでプロファイルの同意属性が更新されます。

**ワンクリックで購読解除（メールヘッダー）**

メールチャネル設定で「**[!UICONTROL リストの購読解除を有効にする]**」オプションがオンになっている場合、ワンクリックの購読解除URLとメールアドレスが自動的にメールヘッダーに追加されます。 受信者は、メール本文をクリックすることなく、メールクライアントから直接オプトアウトできます。 このオプションは、新しいチャネル設定に対してデフォルトで有効になっています。

[List-Unsubscribeの設定方法を学ぶ](../email/list-unsubscribe.md)

**ワンクリックのオプトアウト（メール本文）**

作成者は、メールDesignerを使用して、ワンクリックのオプトアウトリンクをメールコンテンツに直接挿入できます。 受信者がこのリンクをクリックすると、設定がすぐに更新されます。 オプトアウトの範囲は、次のいずれかです。

* **チャネルレベル**: チャネル全体の今後のすべてのメール通信からプロファイルをオプトアウトします。
* **ID レベル**：現在のメッセージでのみ使用されている特定の電子メールアドレスをオプトアウトします。

[ワンクリックのオプトアウトリンクを追加する方法を説明します](../email/email-opt-out.md#one-click-opt-out)

**ランディングページ経由のプリファレンスセンター**

Adobe Journey Optimizerのネイティブなランディングページ機能により、企業は、購読者がコミュニケーションやトラッキングのプリファレンスセンターを管理できる環境を構築できます。 顧客がプリファレンスセンターフォームを送信すると、選択した内容は、同意と環境設定フィールドグループのAEP プロファイル属性に書き戻されます。

CNIL コンプライアンスのシナリオの場合、プリファレンスセンターのランディングページをメールフッターからリンクして（購読解除リンクとは異なります）、受信者が購読状況に関係なくトラッキング設定を管理できるようにします。

[顧客のプリファレンスを管理する方法](../action/preference-center.md)

### 同意の処理と適用 {#consent-enforcement}

受信者が上記のいずれかのメカニズムを通じてオプトアウトすると、以下が発生します。

* プロファイルの同意属性（`consents.marketing.email.val`）がAdobe Experience Platformの`n`に更新されます。
* プロファイルは、ジャーニーやキャンペーンでの今後のマーケティングメール送信からすぐに除外されます。
* オプトアウト情報は、AEP Consent Service データセットに保存されます。
* Journey Optimizerでは、各送信の前にチャネルレベルで同意チェックを実行し、オプトアウトされたプロファイルがマーケティングコミュニケーションを受け取らないようにします。

[オプトアウト管理について詳しく見る](opt-out.md)

### 同意ポリシー {#consent-policies}

企業はAdobe Journey Optimizerで同意ポリシーを作成して適用することで、特定の同意条件を満たすプロファイルのみがコミュニケーションを受け取れるようになります。 同意ポリシーは、マーケティングアクションを通じて、チャネル設定に関連付けることができます。

[同意ポリシーの操作方法について説明します](../action/consent.md)

### 抑制リストと再勧誘 {#suppression}

Adobe Journey Optimizerは、ハードバウンス、ソフトバウンス、迷惑メールの苦情の原因となるメールアドレスを含む抑制リストを自動的に管理します。 抑制リスト上のプロファイルは、今後のマーケティング送信から除外されます。

Journey Optimizer抑制REST APIは、送信メッセージに対する追加のプログラム制御を提供し、APIを介して抑制と許可リストに加えるの動作を管理できるようにします。

[抑制リストの管理方法を説明します](../configuration/manage-suppression-list.md)

<!--
EDITORIAL NOTE – ENGINEERING CONFIRMATION NEEDED before publish:
AJO has no native equivalent of Campaign v8's "lastPixelRefusalDate" field or re-solicitation typology rule. If re-solicitation governance for pixel consent refusal is required, customers would likely need to: (a) create a custom XDM date field to capture the pixel refusal date, and (b) build an AEP audience that filters out profiles where that date falls within the last six months, then use that audience as a suppression filter in campaigns/journeys. Confirm with Engineering: (1) whether this guidance should be included in this article, and (2) whether any native AJO improvements are planned in this area.
-->

### レポート {#reporting}

Adobe Journey Optimizerの電子メールレポートでは、[&#x200B; ライブレポート &#x200B;](../reports/live-report.md)および[Customer Journey Analytics レポート &#x200B;](../reports/report-gs-cja.md)を通じて、開封率とクリック率の指標が提供されます。 メッセージに対して&#x200B;**[!UICONTROL 電子メールが開く]**&#x200B;追跡が無効になっている場合、その配信に対して開いているデータは収集されません。レポートには、クリックやその他のエンゲージメントシグナルのみが反映されます。

