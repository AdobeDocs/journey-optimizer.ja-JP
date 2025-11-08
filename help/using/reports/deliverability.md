---
solution: Journey Optimizer
product: journey optimizer
title: 配信品質の基本を学ぶ
description: 配信品質のガイドラインを説明します
feature: Deliverability
topic: Content Management
role: Admin
level: Intermediate, Experienced
exl-id: 8f33dda7-9bd5-4293-8d0d-222205cbc7d5
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 100%

---

# 配信品質の基本を学ぶ {#manage-deliverability}

配信品質は、受信者のインボックスに配信が正常に届いたかどうかを測定する手法です。

>[!NOTE]
>
>Healthcare Shield のライセンスを取得しているお客様の場合、アドビは Transport Layer Security（TLS）1.2 を使用して、ユーザーのシステム（受信者）と Journey Optimizer（送信者）間のデータ交換を保護します。受信メールサーバーが TLS 1.2 をサポートしていない場合、メールが元の送信者にバウンスするなど、配信品質の問題が発生します。

**メール配信品質**&#x200B;とは、期待される品質のコンテンツと形式を備えたメッセージが、個人のメールアドレスを通じて短時間で宛先に到達する能力を判断する、一連の特性のことを指します。これらの特性は、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、評価の 4 つの主なカテゴリに分類されます。これらのカテゴリを合わせて、成功するメール配信品質プログラムの基礎が形成されます。

**配信率**&#x200B;は、受信者のインボックスに届いたメッセージの数と配信されたメッセージの数との比率です。配信率は、多くの要因に左右されます。特に次のような要因があげられます。

* 限定的なスパム通報
* 低いハードバウンス率
* ターゲットアドレスの品質
* メッセージコンテンツ
* 送信者の評価

[!DNL Journey Optimizer] エクスペリエンスの配信品質を最適化するには、この節に示すベストプラクティスを使用することをお勧めします。配信品質の問題は通常、インターネットサービスプロバイダー（ISP）およびメールサーバー管理者が実行するスパム対策に関係しています。

配信品質とは何か、配信品質の主要な用語、概念およびアプローチの詳細については、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja){target="_blank"}を参照してください。

## 苦情率の低減 {#reduce-complaint-rate}

ISP には通常、受信したメッセージをスパムとしてレポートする優れた手段があります。これにより、信頼できないソースを特定することが可能になります。オプトアウト要求に迅速に対応し、自身が信頼できる送信者であることを示すことで、苦情の発生率を低減できます。[詳しくは、オプトアウト管理を参照してください](../privacy/opt-out.md#opt-out-decision-management)

原則として、オプトアウトを希望する受信者がスムーズに手続きできるよう、メールアドレスや名前などのフィールドへの入力を要求しないようにしてください。購読解除ランディングページには、確認ボタンを 1 つだけ配置してください。

追加の確認を要求するときは特に注意が必要です。ユーザーが 2 つのメールアドレス（例：firstname.lastname@club.com および firstname.lastname@internet-club.com）を同じボックスにリダイレクトする場合があります。プロファイルが最初のアドレスしか覚えておらず、もう 1 つのアドレスに送信されたメッセージ経由で購読解除しようとすると、暗号化された識別情報と入力されたメールアドレスが一致しないことから、フォームは購読解除を拒否します。

## 抑制リストの活用 {#suppression-lists}

[!DNL Journey Optimizer] は、絶えず発生するスパム通報、ハードバウンス、ソフトバウンスを収集した抑制リストを管理します。

配信品質を保護するため、受信者のアドレスが抑制リストに含まれている場合、デフォルトでは、今後のすべての配信からそのアドレスが除外されます。これらの連絡先に送信すると、評価が下がる可能性があるからです。

[詳しくは、抑制リストを参照してください](suppression-list.md)

## 監視ツールの使用 {#monitoring-tools}

[!DNL Journey Optimizer] が提供するレポート機能を使用して、配信品質を監視します。

キャンペーンとジャーニーのレポートを使用すると、一連のリアルタイムインジケーターを使用して、配信のパフォーマンスを確認できます。次の項目も表示されます。

* 正常に実行、送信および配信されたメッセージの数。
* 開封されたメッセージの数と、クリックされたメッセージやリンクの数。

詳しくは、[ライブレポート](../reports/live-report.md)と[全期間のレポート](../reports/report-gs-cja.md)を参照してください。

## メッセージコンテンツの調整 {#adapt-message-content}

それほど影響はありませんが、特定のメッセージコンテンツをスパムとして検出することができます。

配信率を向上させ、メールが受信者に届くようにするには、メッセージコンテンツを設計する際に、次の原則に従ってください。

* **送信者の名前とアドレス**：アドレスは送信者を明示的に識別する必要があります。ドメインは送信者によって所有され、送信者に登録されている必要があります。ドメインレジストリを私有化してはいけません。

* **購読解除リンクとランディングページ**：購読解除リンクは必須です。わかりやすく、有効である必要があります。また、フォームが機能する必要があります。

[詳しくは、メールコンテンツのデザインを参照してください](../email/get-started-email-design.md)

## 送信者としての評判を確立する {#reputation}

最近、別のメールサービスプロバイダー、IP アドレス、メールドメインまたはサブドメインに移動した場合は、送信者としての評判を確立する必要があります。そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに送られる可能性があります。

新しい IP アドレスでメールを送信する際に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。

Adobe Journey Optimizer は、標準化された効率的な方法で、最適な配信品質を実現するためのベストプラクティスに従って IP アドレスのウォームアップを行います。

[詳しくは、IP ウォームアッププランを参照してください](../configuration/ip-warmup-gs.md)

<!--To warm up your IP, you can gradually ramp up the number of your deliveries. Learn more in this [use case](../building-journeys/ramp-up-deliveries-uc.md).-->

## DMARC の実装 {#dmarc}

正規のメールがスパムとしてマークされるか却下されるリスクを軽減し、配信品質の問題を防ぐために、[!DNL Journey Optimizer] では、アドビにデリゲートするすべてのサブドメインに対して DMARC レコードを設定できます。

DMARC（Domain-based Message Authentication, Reporting, and Conformance）は、ドメイン所有者が自身のドメインを悪意のある関係者による不正使用から保護できるようにするメール認証方式です。

[詳しくは、DMARC レコードを参照してください](../configuration/dmarc-record.md)

## フィードバックループについて {#feedback-loops}

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="一部のサブドメインは使用できない場合があります"
>abstract="フィードバックループ登録が保留になっているので、特定のサブドメインは現在選択できません。この処理には、最大 10 営業日かかる場合があります。完了したら、使用可能なすべてのサブドメインから選択できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/configuration/delegate-subdomains/about-subdomain-delegation" text="サブドメインデリゲーションの基本を学ぶ"

フィードバックループ（FBL）は、一部の ISP が提供するサービスで、メールを受信したユーザーがメールをスパム（「スパム報告」とも呼ばれます）としてマークすることを選択した場合に、メール送信者に自動的に通知できます。

エンドユーザーがスパム報告を生成し、ISP によってアドビに返信されると、そのメールアドレスは自動的に[抑制リスト](../reports/suppression-list.md)に追加され、今後の配信から除外されます。実際、スパムとしてマークしたユーザーにメールを送信すると、送信者の評判に悪影響を与え、配信品質の問題が発生する場合があります。[詳しくは、スパム報告を参照してください](../reports/suppression-list.md#spam-complaints)

>[!IMPORTANT]
>
>すべての ISP が Gmail などの従来の FBL を提供しているわけではありません。Gmail は個人レベルのフィードバックを提供しておらず、個々の受信者へのスパム報告を追跡するために使用することはできず、代わりに Google Postmaster Tools 内の集計レベルのレポートに焦点を当てています。[詳細情報](https://support.google.com/a/answer/6254652?hl=ja){target="_blank"}

すべてのアドビのお客様は、次の ISP の従来の FBL に自動的に登録されます。

* 1&amp;1

* AOL

* BlueTie

* Comcast

* Fastmail

* Gandi

* Italia Online

* La Poste

* Liberty Global（Chello、UPC、Unity Media）

* Locaweb

* Mail.RU

* Microsoft

* OpenSRS

* Rackspace

* SEZNM

* SFR

* SilverSky

* Swisscom

* Synacor

* Telecom Italia

* Telenet

* Telenor

* Telstra

* Terra

* UOL

* Virgin Media

* Yahoo

* Ziggo

アドビでは、これらの FBL を定期的に監査して、利用可能な最新の FBL が追加されていることを確認します。

## SMTP リレーの使用 {#smtp-relay}

[!DNL Journey Optimizer] は、アドビが所有するメール転送エージェント（MTA）と IP を使用して、メールをインターネットサービスプロバイダー（ISP）に配信します。ただし、場合によっては、最終的なメール配信を独自の MTA と IP を通じてルーティングしたり、受信者に送信する前にメールの最終的な検証を実行したりする必要があることもあります。

この場合、メールを Journey Optimizer から ISP に直接送信する代わりに、組織がホストする SMTP サーバーにリレーすることを選択できます。

>[!AVAILABILITY]
>
>SMTP リレー容量はオンデマンドで使用できます。アドビ担当者にお問い合わせください。
