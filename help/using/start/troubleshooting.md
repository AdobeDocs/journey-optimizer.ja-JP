---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のトラブルシューティング
description: Journey Optimizer のトラブルシューティングに関する質問
feature: Get Started
role: User
level: Intermediate
exl-id: f8acb987-5c6e-4545-93b9-fdfc0d74db57
source-git-commit: f46cc01dce5ab0a30c1f0907b2a4684802b216be
workflow-type: tm+mt
source-wordcount: '2746'
ht-degree: 97%

---

# トラブルシューティング {#ajo-troubleshooting}

次は、Adobe Journey Optimizer のトラブルシューティング記事のリストです。各トラブルシューティングセクションでは、よくある質問への回答と問題に対する解決策を提供します。

詳しくは、[Adobe Experience Platform の FAQ とトラブルシューティングドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/troubleshooting){target="_blank"}も参照してください。

## メールチャネル {#ajo-troubleshooting-email}

+++ テーマを使用して Adobe Journey Optimizer でメールの書式設定の問題を防ぐにはどうすればよいですか？

Adobe Journey Optimizer（AJO）では、メールヘッダーのデフォルトの CSS ブロックを変更すると、特にコンテンツフラグメントを削除した後に、予期しない書式設定の問題が発生する場合があります。これらの問題はモバイルデバイスでより顕著になり、レイアウトのずれやスタイルの不一致が発生する場合があります。これを防ぐには、テーマ機能を使用して、システムによって生成された CSS スタイルを変更せずにカスタム CSS を安全に適用します。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-27252){target="_blank"}を参照してください。

メールの書式設定について詳しくは、[このページ](../email/get-started-email-design.md)を参照してください。

+++


+++ 編集可能なフィールドを含むフラグメントが機能しないのはなぜですか？

Adobe Journey Optimizer では、編集可能なフィールドを含むフラグメントをテンプレートに追加すると、正しく読み込めなかったり、予期せず重複したりする場合があります。この問題は通常、環境全体の特定のフラグメントに影響します。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26908){target="_blank"}を参照してください。

カスタマイズ可能なフラグメントについて詳しくは、[このページ](../content-management/customizable-fragments.md)を参照してください。

+++

+++ HTML フラグメントがメールで正しく表示されないのはなぜですか？

HTML フラグメントはメールで正しくレンダリングされず、多くの場合、実際のコンテンツではなく&#x200B;**フラグメント ID** として表示される場合があります。ビジュアルフラグメントとは異なり、HTML フラグメントは慎重な設定が必要です。これを解決するには、メールキャンペーンで&#x200B;**ビジュアルと HTML の両方の式フラグメント**&#x200B;を使用するベストプラクティスに従います。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-25441){target="_blank"}を参照してください。

HTML フラグメントについて詳しくは、[このページ](../content-management/fragments.md)を参照してください。

+++

+++ 非公開のジャーニーからメールテンプレートとコンテンツが表示されなくなるのはなぜですか？

非公開のジャーニーでメールテンプレートを編集すると、特定のメールのコンテンツとテンプレートが予期せず表示されなくなる場合があります。これは、リワークや遅延の原因となる場合があります。この問題のリスクを軽減するには、同時編集を避け、開いているタブの数を制限し、変更を頻繁に保存します。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"}を参照してください。

テンプレートについて詳しくは、[このページ](../email/use-email-templates.md)を参照してください。

+++

+++ 「独自にコーディング」モードでメールプリヘッダーフィールドが表示されないのはなぜですか？ 

**メール本文を編集**&#x200B;機能の&#x200B;**「独自にコーディング」**&#x200B;モードでは、「プリヘッダー」入力フィールドが表示されません。プリヘッダーテキストを含めるには、ユーザーはカスタム HTML コンテンツ内に&#x200B;**プリヘッダーを手動でコーディング**&#x200B;する必要があります。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26174){target="_blank"}を参照してください。

メールヘッダーの設定について詳しくは、[このページ](../email/header-parameters.md)を参照してください。

+++

+++ メールテンプレートで HTML コンポーネントを使用する場合、リンクの動作に不一致があるのはなぜですか？  

**HTML コンポーネント**&#x200B;をメールテンプレートに追加すると、**メールクライアント**、**表示モード**、**デバイス／ブラウザー**&#x200B;に応じてリンクの動作が異なる場合があります。例えば、アンカーリンクは、**Outlook の並列表示**&#x200B;と全画面表示では機能が異なる場合があります。メールテンプレートを設計し、複数のクライアントとデバイスでテストする際は、これらのバリエーションに注意してください。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26221){target="_blank"}を参照してください。

メールデザインのベストプラクティスについて詳しくは、[このページ](../email/get-started-email-design.md)も参照してください。

+++


+++ レポートでメールトラッキングリンクが失われないようにするにはどうすればよいですか？

メール URL に動的変数が使用され、http で始まらない場合や、「URL」フィールドにロジックステートメントが配置されている場合に、Adobe Journey Optimizer でリンクトラッキングが失われます。これを解決するには、すべての URL が http で始まることを確認し、「URL」フィールドでのロジックの使用を避け、複雑なパーソナライゼーションロジックを HTML コンテンツまたは事前処理済み属性に移動します。


この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26932){target="_blank"}を参照してください。

メールトラッキングについて詳しくは、[このページ](../email/message-tracking.md)を参照してください。

+++

+++ API トリガーのトランザクションメールキャンペーンを設定する際にメール交換エラーを解決するにはどうすればよいですか？ 

Adobe Journey Optimizer で API トリガーのトランザクションメールキャンペーンのチャネル設定を作成中にメール交換（MX）エラーが発生した場合、**DNS の設定ミス**&#x200B;または **DMARC ポリシーの制限**&#x200B;が原因であることがあります。この問題を解決するには、DNS が正しく設定されていることを確認し、ドメインが **Domain-based Message Authentication, Reporting, and Conformance（DMARC）**&#x200B;の要件に準拠していることを確認します。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26200){target="_blank"}を参照してください。

メールの DMARC ポリシーについて詳しくは、[このページ](../configuration/dmarc-record-update.md)を参照してください。

詳しくは、[API トリガーキャンペーンドキュメント](../campaigns/api-triggered-campaigns.md)も参照してください。
+++

## プッシュチャネル {#ajo-troubleshooting-push}

+++ Adobe Journey Optimizer では、プロファイルに複数のプッシュトークンを設定できますか？

Journey Optimizer でプッシュ通知を実装する場合、1 つのプロファイルに、異なるデバイスに関連付けられた複数のプッシュトークンを含めることができます。プッシュ通知キャンペーン中、Journey Optimizer はこれらのトークンを管理し、関連するすべてのデバイスでターゲットプロファイルに確実に到達できるように設計されています。

プッシュトークンの管理について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"}を参照してください。

プッシュ設定について詳しくは、[このページ](../push/push-configuration.md)を参照してください。

+++

+++ プッシュメッセージをクリックしても、設定済みの web URL にリダイレクトされないのはなぜですか？  

プッシュメッセージが目的の web URL にリダイレクトされない場合は、クリックアクションの設定が正しくないか、プッシュ通知設定が無効になっていることが原因であることがあります。この問題を解決するには、プッシュメッセージの&#x200B;**クリックアクション**&#x200B;が正しく設定され、プッシュ通知の&#x200B;**自動表示とトラッキング**&#x200B;が有効になっていることを確認します。

この問題について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26226){target="_blank"}を参照してください。

プッシュ設定について詳しくは、[このページ](../push/push-configuration.md)を参照してください。

+++


## SMS チャネル {#ajo-troubleshooting-sms}

+++ 同意が `marketing.sms.value=y` に設定されているにもかかわらず、トランザクション SMS が配信されないのはなぜですか？

受信者が SMS に **STOP** と応答すると、その短縮番号からの今後のすべてのメッセージ（トランザクションメッセージを含む）がブロックされます。トランザクション SMS の配信が中断されないようにするには、受信者が以前にオプトアウトしていない&#x200B;**別の短縮番号**&#x200B;を設定して、その番号を通じて送信します。

この問題について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26258){target="_blank"}を参照してください。

SMS オプトアウト設定について詳しくは、[このページ](../sms/sms-opt-out.md)を参照してください。

+++

## アプリ内チャネル

+++ Customer Journey Analytics でアプリ内チャネルをレポートできないのはなぜですか？

Adobe Customer Journey Analytics の&#x200B;**アプリ内チャネル**&#x200B;に関するレポートの問題は、多くの場合、**データビュー**、**データセット**&#x200B;または&#x200B;**スキーマの更新**&#x200B;の設定が間違っているために発生します。問題を解決するには、これらの設定が正しく適用されていることを確認します。

この問題について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26206){target="_blank"}を参照してください。

Customer Journey Analytics で Journey Optimizer Analytics データを統合する方法について詳しくは、[このページ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/integrations/ajo?lang=ja#automatically-configure-journey-optimizer-integration){target="_blank"}を参照してください。

詳しくは、[Journey Optimizer の全期間レポートドキュメント](../reports/report-gs-cja.md)も参照してください。

+++


## データ管理 {#ajo-troubleshooting-data-management}

+++ 新しいサンドボックスを作成する際に、Time-to-Live（TTL）設定はプロファイルとデータレイクのデータセットにどのように適用されますか？

Adobe Journey Optimizer で新しいサンドボックスをプロビジョニングする組織から、Time-to-Live（TTL）設定がプロファイルおよびデータレイクデータセットにどのように適用されるかに関する質問が寄せられています。この記事では、TTL 設定は既存のサンドボックスに影響を与えず、新しくプロビジョニングされたサンドボックスにのみ自動的に適用されることを明確にします。

TTL の処理方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"}を参照してください。

データセットの Time-to-live について詳しくは、[このページ](../data/datasets-ttl.md)を参照してください。

+++


## プロファイルと Audience management {#ajo-troubleshooting-audiences}

+++ オーディエンス数の不一致を解決するにはどうすればよいですか？

Adobe Journey Optimizer の&#x200B;**オーディエンスを読み取り**&#x200B;機能で処理されるエントリの数は、予想されるオーディエンス数よりも少なくなる場合があります。この問題は、多くの場合、名前空間の設定が正しくないことが原因で発生し、プロファイルがジャーニーから除外されます。解決策には、名前空間の設定の確認と修正、関連ドキュメントの確認、優先度の調整が含まれ、Adobe Journey Optimizer での操作がスムーズになります。

この問題の解決方法について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"}を参照してください。

詳しくは、[古いオーディエンス数に関するこの記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26166){target="_blank"}も参照してください。

ジャーニーの&#x200B;**オーディエンスを読み取り**&#x200B;アクティビティについて詳しくは、[このページ](../building-journeys/read-audience.md)を参照してください。

+++

+++ プロファイルの更新が失敗するのはなぜですか？

Adobe Journey Optimizer では、ジャーニーで&#x200B;**プロファイルを更新**&#x200B;アクティビティを実行した後、特定のフィールド値が正しく更新されない場合があります。場合によっては、更新したフィールドが表示されなくなったり、以前の状態に戻ったりすることがあります。この問題に対処するには、競合するルールや条件がないかを確認し、権限設定を確認し、**プロファイルを更新**&#x200B;アクティビティに一意のデータセットを使用し、他の取り込みプロセスが同時に同じプロファイルに書き込んでいないことを確認します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26352){target="_blank"}を参照してください。

ジャーニーの&#x200B;**プロファイルを更新**&#x200B;アクティビティについて詳しくは、[このページ](../building-journeys/update-profiles.md)を参照してください。

詳しくは、[データ取り込みに関する Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/tutorials/ingest-batch-data?lang=ja#dataset-activity){target="_blank"}も参照してください。

+++

+++ ジャーニーにエントリするプロファイル数と関連するオーディエンスのプロファイル数が一致しないのはなぜですか？

ジャーニーの実行時に現在の日付のスナップショットが使用できない場合、ジャーニーで前日のプロファイルスナップショットを使用すると、不一致が発生することがあります。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26253){target="_blank"}を参照してください。

詳しくは、[この Journey Optimizer コミュニティの投稿](https://experienceleaguecommunities.adobe.com/t5/real-time-customer-data-platform/profile-snapshot-and-segment-qualification-troubleshooting/ba-p/698998){target="_blank"}を参照してください。

毎日のジョブがスケジュールされるタイミングを確認するには、[Adobe Experience Platform Schedules API ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/api/schedules?lang=ja){target="_blank"}も参照してください。

+++


+++ オーディエンス母集団の問題を解決するにはどうすればよいですか？

オーディエンス母集団の問題は、多くの場合、使用権限、プロビジョニング、権限の設定ミスにより、コンポーネントやリソースが欠落している際に発生します。これらの問題を修正するには、まず、使用権限を検証し、正しいプロビジョニングを確認し、権限をレビューします。問題が解決しない場合は、ケースをエスカレートし、サポートチームと調整して完全な解決を行います。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26333){target="_blank"}を参照してください。

ジャーニーの&#x200B;**プロファイルを更新**&#x200B;アクティビティについて詳しくは、[このページ](../building-journeys/update-profiles.md)を参照してください。

詳しくは、[Adobe Real-Time CDP プロファイルドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/ui/user-guide?lang=ja#profile-detail){target="_blank"}も参照してください。

+++

+++ エンゲージ可能なプロファイル数が短期間に大幅に増加したのはなぜですか？ 

**エンゲージ可能なプロファイル**&#x200B;指標は、過去 12 か月間にジャーニーまたはキャンペーンによって関与された一意のプロファイルの数を反映します。突然の増加は、大規模なオーディエンスをターゲットにしたり、データセットに変更があったりすることによって発生する場合があります。これを管理するには、**プロファイルカウントロジック**&#x200B;を確認し、大規模なオーディエンスをターゲットにするジャーニーを調査し、ジャーニーレベルで&#x200B;**オーディエンスをフィルタリング**&#x200B;し、**アドレス可能なオーディエンスサイズ**&#x200B;を縮小し、**データセットの変更**&#x200B;を監視します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26161){target="_blank"}を参照してください。

[ライセンス使用状況ダッシュボード](../audience/license-usage.md)を使用して、組織のライセンス使用状況とエンゲージ可能なプロファイルを監視します。

詳しくは、[Adobe Experience Platform クエリサービスの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home?lang=ja){target="_blank"}も参照してください。

+++

+++ 日付関数に基づいて、対象のオーディエンス以外の個人にメールが送信されるのはなぜですか？

**指定されたオーディエンス条件を満たさない**&#x200B;受信者にメールが送信される場合があります。例えば、引き換え日が **2025年7月4日（PT）より前**&#x200B;のメンバーには、その日以降のメンバーのみを対象としたメールが届く場合があります。この動作は、**オーディエンスのセグメント化の設定ミス**&#x200B;や、**プロファイル選定ロジックの予期しない変更**&#x200B;によって発生する場合があります。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26173){target="_blank"}を参照してください。

日付関数について詳しくは、[このページ](../../rp_landing_pages/date-landing-page.md)を参照してください。

+++

+++ ジャーニーを保存する際にオーディエンス選択の問題と Chrome エラーを解決するにはどうすればよいですか？

ジャーニー条件にオーディエンスを追加すると、ジャーニーの保存時にエラーが発生するなど、**アプリケーションがクラッシュ**&#x200B;したり、Chrome で **Aw Snap エラー**&#x200B;が表示されたりする場合があります。これらの問題は、多くの場合、**Chromium サービス**&#x200B;に関連しています。問題を解決するには、**ブラウザーのアップデート**&#x200B;を適用するか、適切な&#x200B;**回避策**&#x200B;を使用します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26145){target="_blank"}を参照してください。

+++

## ジャーニー {#ajo-troubleshooting-journeys}

ジャーニーについて詳しくは、次のトラブルシューティングの節を参照してください。

* [ジャーニーをテストする前のエラーのトラブルシューティング](../building-journeys/troubleshooting.md)
* [ジャーニーでのインバウンドアクションのトラブルシューティング](../building-journeys/troubleshooting-inbound.md)
* [ライブジャーニー実行のトラブルシューティング](../building-journeys/troubleshooting-execution.md)
* [カスタムアクションのトラブルシューティング](../action/troubleshoot-custom-action.md)


+++ 新しいジャーニーバージョンを作成する際に式が失われるのはなぜですか？  

新しいバージョンのジャーニーを作成すると、**特定のステップの式**&#x200B;が失われ、エラーが発生し、手動での再入力が必要になる場合があります。これを解決するには、**ジャーニーを複製**&#x200B;し、再現性をテストし、**ブラウザーの再読み込みを回避**&#x200B;し、古いジャーニーには&#x200B;**更新されたキャンバス**&#x200B;を使用します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26152){target="_blank"}を参照してください。

ジャーニーを複製する方法について詳しくは、[このページ](../building-journeys/journey-ui.md#duplicate-a-journey)を参照してください。

+++

+++ プロファイルが途中でジャーニーを終了するのはなぜですか？ 

送信されたメッセージの&#x200B;**条件チェックのフィードバックステータス**&#x200B;に設定ミスがある場合、プロファイルは指定されたノードを通過せずに予期せずジャーニーを終了することがあります。これを解決するには、**条件ロジック**&#x200B;を確認し、**代替ロジック**&#x200B;を実装するか、**実装チーム**&#x200B;にお問い合わせください。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26127){target="_blank"}を参照してください。

詳しくは、[ジャーニー設計ガイドライン](../building-journeys/using-the-journey-designer.md)も参照してください。

+++


+++ プロファイルが予期せずジャーニーを終了するのはなぜですか？

**イベントキャップ**&#x200B;が発生すると、プロファイルが予期せずジャーニーから終了する場合があり、処理されるイベントの数がシステム容量を超えると、一部のプロファイルが破棄されます。プロファイルの終了を減らすには、**システムの制限**&#x200B;を理解し、**イベントスパイク**&#x200B;を監視し、しきい値を超えないように&#x200B;**データフロー**&#x200B;を最適化します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26018){target="_blank"}を参照してください。

詳しくは、[ジャーニーガードレール](../start/guardrails.md#journey-guardrails)も参照してください。

+++


+++ イベントが対象のジャーニーをトリガーしないのはなぜですか？  

イベントは、**データ収集コアサービス（DCCS）**&#x200B;にストリーミングされるのではなく、**クエリサービスを通じて作成**&#x200B;される場合、すべての条件が満たされていても、ジャーニーをトリガーできないことがあります。これを解決するには、イベント設定を確認し、イベントが **DCCS に直接ストリーミング**&#x200B;されていることを確認し、**テストモード**&#x200B;を使用して機能を検証します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26031){target="_blank"}を参照してください。

イベントについて詳しくは、[このページ](../event/about-events.md)を参照してください。

詳しくは、[ジャーニーイベントガードレール](../start/guardrails.md#events)も参照してください。

+++


+++ Adobe Journey Optimizer でオーディエンス変更後のジャーニートリガーの問題を解決するにはどうすればよいですか？ 

結合ポリシーの変更など、関連するオーディエンスに変更を行った後にジャーニーのトリガーが停止すると、フローが中断される場合があります。これを解決するには、更新されたオーディエンス設定で&#x200B;**ジャーニーを複製して再公開**&#x200B;し、トリガーが正しく機能することを確認します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26224){target="_blank"}を参照してください。

ジャーニーを複製する方法について詳しくは、[このページ](../building-journeys/journey-ui.md#duplicate-a-journey)を参照してください。

+++

+++ 外部のサードパーティエンドポイントを呼び出すカスタムアクションがタイムアウトするのはなぜですか？

**カスタムアクション**&#x200B;が外部のサードパーティエンドポイントを呼び出すと、タイムアウトエラーが発生する場合があります。これを解決するには、**エンドポイントがアクセス可能**&#x200B;であることを検証し、**サーバーログ**&#x200B;を確認し、**アドビからのブロックがない**&#x200B;ことを確認し、必要に応じてエンドポイント設定を更新し、**更新後にテスト**&#x200B;を行います。また、**API 呼び出しのタイムアウト仕様**&#x200B;にも注意してください。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26156){target="_blank"}を参照してください。

Journey Throttling API について詳しくは、[このページ](../configuration/throttling.md)を参照してください。

詳しくは、[外部システムとの統合に関するドキュメント](../configuration/external-systems.md)も参照してください。

+++

+++ 矢印からオーディエンスを公開する際に「**invalid_access**」または「**No access to this dataId=XX granted**」というメッセージが表示された場合、403 エラーが発生した場合は、どのような手順を行う必要がありますか？

このエラーを解決するには、管理者に問い合わせて、ユーザープロファイルがオーディエンスの公開に必要なデータビューにアクセスできることを確認してから、オーディエンスを再度公開してみてください。

この問題を解決する手順については、[ 権限のドキュメント ](../administration/permissions.md){target="_blank"} を参照してください。

+++

## ルール {#ajo-troubleshooting-rules}

+++ キャッピングルールのドロップダウンが機能しないのはなぜですか？

**キャッピングルールのドロップダウン**&#x200B;の問題は、多くの場合、ルールセットが&#x200B;**誤って設定**&#x200B;されているか、**アクセスできない**&#x200B;場合に発生します。問題を解決するには、すべてのルールセットが正しく設定され、使用可能であることを確認します。

詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26204){target="_blank"}を参照してください。

キャッピングルールの適用方法について詳しくは、[この節](../conflict-prioritization/rule-sets.md)を参照してください。

+++

## 決定 {#ajo-troubleshooting-decisioning}

+++ オファーコレクションを作成する際に問題を解決するにはどうすればよいですか？

組織に&#x200B;**カタログがプロビジョニングされていない**&#x200B;と、多くの場合、オファーコレクションの作成が困難になります。これを解決するには、オファーコレクションを作成する前に、必要なすべてのカタログが正しくプロビジョニングされていることを確認します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26265){target="_blank"}を参照してください。

オファーコレクションについて詳しくは、[このページ](../offers/offer-library/creating-collections.md)を参照してください。

+++

+++ Offer Decisioning にアクセスできないのはなぜですか？  

Adobe Journey Optimizer を使用して Adobe Target をアプリケーションに統合する場合、データストリーム設定内で「**Offer Decisioning**」オプションにアクセスできないことがあります。これは通常、**権限設定**&#x200B;または&#x200B;**プロビジョニングの制約**&#x200B;により発生します。問題を解決するには、ユーザー権限を検証し、必要なプロビジョニングが行われていることを確認します。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26175){target="_blank"}を参照してください。

Offer Decisioning に必要な権限について詳しくは、[このページ](../offers/get-started/starting-offer-decisioning.md#granting-acess-to-decision-management)を参照してください。

+++



## 多言語 {#ajo-troubleshooting-multilingual}

+++ この問題 `Message validation error (CJMMAS - 1069-500)` を解決するにはどうすればよいですか？

Adobe Journey Optimizer では、多言語機能にリンクされたメッセージ検証エラー（CJMMAS - 1069-500）により、ジャーニーをテストモードに設定したり公開したりできません。

この問題の解決手順について詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26168){target="_blank"}を参照してください。

多言語コンテンツについて詳しくは、[このページ](../content-management/multilingual-gs.md)を参照してください。

+++


## 設定 {#ajo-troubleshooting-config}

+++ カスタムアクションに対して TLS v1.3 を有効にするにはどうすればよいですか？  

サードパーティシステムに接続する際に&#x200B;**データの整合性とセキュリティ**&#x200B;を維持するには、カスタムアクションで Transport Layer Security（**TLS**）v1.3 が有効になっていることを確認します。これにより、通信が保護され、潜在的なセキュリティの脆弱性を防ぐことができます。


詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26223){target="_blank"}を参照してください。

多言語コンテンツについて詳しくは、[このページ](../action/about-custom-action-configuration.md)を参照してください。

+++

+++ Adobe Journey Optimizer のクエリから直接ダッシュボードを作成できないのはなぜですか？ 

Adobe Journey Optimizer では、クエリから直接ダッシュボードを作成できません。ダッシュボードを作成するには、Adobe Experience Platform 内で使用可能な&#x200B;**ダッシュボード作成機能**&#x200B;を使用します。これにより、クエリデータを効果的に視覚化および分析できます。

詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26201){target="_blank"}を参照してください。

+++

## API {#ajo-troubleshooting-apis}

+++ Query Service API のアクセスの問題を解決するにはどうすればよいですか？  

Postman や同様のツールを通じて **Query Service API** を使用する際にアクセスエラーが発生する場合は通常、**権限が不十分**&#x200B;なことが原因です。これを解決するには、ユーザー権限を検証し、API 資格情報を確認して、必要に応じて詳細情報をサポートに提供します。

詳しくは、[このトラブルシューティング記事](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26196){target="_blank"}を参照してください。

詳しくは、[API 資格情報の管理ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/abac/permissions-ui/permissions?lang=ja#manage-api-credentials-for-role){target="_blank"}も参照してください。

+++
