---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerのトラブルシューティング
description: Journey Optimizerのトラブルシューティングの質問
feature: Get Started
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 0cc119d3e4c1ffa676f00fcedb93d8818f176689
workflow-type: tm+mt
source-wordcount: '2665'
ht-degree: 1%

---

# トラブルシューティング {#ajo-troubleshooting}


以下は、Adobe Journey Optimizerのトラブルシューティング記事のリストです。 各トラブルシューティングセクションでは、よくある質問への回答と問題の解決策を示します。

[Adobe Experience Platformの FAQ とトラブルシューティングドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/troubleshooting#service-troubleshooting-directory){target="_blank"} も参照してください。

## メールチャネル {#ajo-troubleshooting-email}

### メールデザイン {#ajo-troubleshooting-design}

+++ テーマを使用してAdobe Journey Optimizerでメールの形式の問題を防ぐ方法を教えてください。

Adobe Journey Optimizer（AJO）では、メールヘッダーのデフォルトの CSS ブロックを変更すると、特にコンテンツフラグメントを削除した後で、予期しない形式の問題が発生する可能性があります。 これらの問題はモバイルデバイスでより顕著で、レイアウトが変更されたりスタイルに不整合が生じたりする場合があります。 これを防ぐには、テーマ機能を使用して、システム生成の CSS スタイルを変更せずに、カスタム CSS を安全に適用します。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-27252){target="_blank"} を参照してください。

メールの形式について詳しくは [ このページ ](../email/get-started-email-design.md) を参照してください。

+++


+++ 編集可能なフィールドを含むフラグメントが機能しないのはなぜですか？

Adobe Journey Optimizerでは、編集可能なフィールドを含むフラグメントをテンプレートに追加すると、正しく読み込めなかったり、予期せず重複したりすることがあります。 この問題は、通常、環境全体の特定のフラグメントに影響します。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26908){target="_blank"} を参照してください。

カスタマイズ可能なフラグメントについて詳しくは [ このページ ](../content-management/customizable-fragments.md) を参照してください。

+++

+++ HTML フラグメントがメールで正しく表示されないのはなぜですか？

HTML フラグメントはメールで正しくレンダリングされず、多くの場合、実際のコンテンツではなく **フラグメント ID** として表示される場合があります。 ビジュアルフラグメントとは異なり、HTML フラグメントは慎重な設定が必要です。 これを解決するには、メールキャンペーンで **ビジュアルとHTMLの両方の式フラグメント** を使用するためのベストプラクティスに従います。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-25441){target="_blank"} を参照してください。

HTML フラグメントについて詳しくは [ このページを参照 ](../content-management/fragments.md)。

+++

+++ 未公開のジャーニーからメールテンプレートとコンテンツが表示されなくなるのはなぜですか？

非公開のジャーニーでメールテンプレートを編集すると、特定のメールのコンテンツとテンプレートが予期せず表示されなくなる場合があります。 これは、リワークや遅延の原因となる可能性があります。 この問題のリスクを軽減するには、同時編集を避け、開いているタブの数を制限し、変更を頻繁に保存します。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} を参照してください。

テンプレートについて詳しくは [ このページを参照 ](../email/use-email-templates.md)。

+++

+++ 「独自にコーディング」モードでメールプリヘッダーフィールドが表示されないのはなぜですか？ 

**メール本文** 編集 **機能の** 独自にコーディング モードでは、「プリヘッダー」入力フィールドが表示されません。 プリヘッダーテキストを含めるには、カスタム HTML コンテンツ内に **プリヘッダーを手動でコーディング** する必要があります。

この問題を解決する方法については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26174){target="_blank"} を参照してください。

メールプリヘッダー設定について詳しくは [ このページ ](../email/header-parameters.md) を参照してください。

+++

+++ メールテンプレートでHTML コンポーネントを使用する場合、リンクの動作に不一致があるのはなぜですか？  

**HTML コンポーネント** をメールテンプレートに追加する場合、リンクの動作は、**メールクライアント**、**表示モード**、**デバイス/ブラウザー** によって異なる場合があります。 例えば、アンカーリンクは、**Outlook の左右に並べて表示するビュー** と全画面表示ビューで異なる機能を果たす場合があります。 メールテンプレートを設計し、複数のクライアントやデバイスでテストする場合は、これらのバリエーションに注意してください。

この問題を解決する方法については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26221){target="_blank"} を参照してください。

メールデザインのベストプラクティス [ このページ ](../email/get-started-email-design.md) も参照してください。

+++


### 電子メールのトラッキングとレポート {#ajo-troubleshooting-tracking}

+++ レポートでメールトラッキングリンクが見つからないようにする方法

Adobe Journey Optimizerでのリンクトラッキングの欠落は、メール URL が動的変数を使用し、http で始まらない場合や、URL フィールドに論理ステートメントが配置された場合に発生します。 これを解決するには、すべての URL が http で始まることを確認し、「URL」フィールドでロジックを使用しないようにして、複雑なパーソナライゼーションロジックをHTML コンテンツまたは事前処理済み属性に移動します。


この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26932){target="_blank"} を参照してください。

メールトラッキングについて詳しくは [ このページを参照 ](../email/message-tracking.md)。

+++

### メール送信 {#ajo-troubleshooting-sending}

+++ API トリガーのトランザクションメールキャンペーンを設定する際に Mail Exchanger エラーを解決する方法を教えてください。 

Adobe Journey Optimizerで API トリガーのトランザクションメールキャンペーンのチャネル設定を作成中にメール交換（MX）エラーが発生した場合は、**DNS の設定ミス** または **DMARC ポリシーの制限** が原因である可能性があります。 これを解決するには、DNS が正しく設定されていること、およびドメインが **Domain-based Message Authentication, Reporting, and Conformance （DMARC））の要件に準拠していることを確認し** す。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26200){target="_blank"} を参照してください。

メールDMARCポリシーについて詳しくは [ このページ ](../configuration/dmarc-record-update.md) を参照してください。

[API トリガーキャンペーンのドキュメント ](../campaigns/api-triggered-campaigns.md) も参照してください。
+++

## プッシュチャネル {#ajo-troubleshooting-push}

+++ Adobe Journey Optimizerでは、1 つのプロファイルに複数のプッシュトークンを含めることはできますか？

Journey Optimizerにプッシュ通知を実装する場合、1 つのプロファイルが異なるデバイスに関連付けられた複数のプッシュトークンを持っている可能性があります。 プッシュ通知キャンペーン中、Journey Optimizerはこれらのトークンを管理し、関連するすべてのデバイスからターゲットプロファイルに確実にアクセスできるように設計されています。

プッシュトークン管理について詳しくは、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} を参照してください。

プッシュ設定について詳しくは [ このページ ](../push/push-configuration.md)。

+++

+++ プッシュメッセージをクリックしても、設定済みの web URL にリダイレクトされないのはなぜですか？  

プッシュメッセージが目的の web URL にリダイレクトされない場合は、クリックアクションの設定が正しくないか、プッシュ通知設定が無効になっている可能性があります。 プッシュメッセージの **クリックアクション** が正しく設定されていること、およびプッシュ通知の **自動表示とトラッキング** が有効になっていることを確認して、この問題を解決します。

この問題について詳しくは、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26226){target="_blank"} を参照してください。

プッシュ設定について詳しくは [ このページ ](../push/push-configuration.md)。

+++


## SMS チャネル {#ajo-troubleshooting-sms}

+++ 同意が `marketing.sms.value=y` に設定されているにもかかわらず、トランザクション SMS が配信されないのはなぜですか？

受信者が SMS に対して **STOP** 応答すると、その短い数からの今後のすべてのメッセージ（トランザクションメッセージを含む）がブロックされます。 トランザクション SMS の配信が中断されないようにするには、受信者が以前にオプトアウトしたことがない **別の短い数字** を使用して SMS を設定および送信します。

この問題について詳しくは、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26258){target="_blank"} を参照してください。

SMS オプトアウト設定について詳しくは [ このページ ](../sms/sms-opt-out.md) を参照してください。

+++



## アプリ内チャネル

+++ Customer Journey Analyticsのアプリ内チャネルでレポートできないのはなぜですか？

Adobe Customer Journey Analyticsの **アプリ内チャネル** に関するレポートの問題は、多くの場合、設定の誤り **データビュー**、**データセット**、または **スキーマの更新** から発生します。 問題を解決するために、これらの設定が正しく適用されていることを確認します。

この問題について詳しくは、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26206){target="_blank"} を参照してください。

Customer Journey AnalyticsでJourney Optimizer Analytics データを統合する方法について詳しくは [ このページ ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/ajo?lang=en#automatically-configure-journey-optimizer-integration){target="_blank"} を参照してください。

[Journey Optimizerの全期間レポートのドキュメントも参照してください ](../reports/report-gs-cja.md)

+++




## データ管理 {#ajo-troubleshooting-data-management}

+++ 新しいサンドボックスを作成する際、Time-to-Live （TTL）設定はプロファイルおよびデータレイクのデータセットにどのように適用されますか。

Adobe Journey Optimizerで新しいサンドボックスをプロビジョニングする組織からは、Time-to-Live （TTL）設定がプロファイルおよびデータレイクデータセットにどのように適用されるかについて疑問が生じています。 この記事では、TTL 設定は既存のサンドボックスに影響を与えず、新しくプロビジョニングされたサンドボックスにのみ自動的に適用されることを明確にします。

TTL の処理方法については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"} を参照してください。

データセットの有効期間について詳しくは [ このページを参照してください ](../data/datasets-ttl.md)。

+++


## プロファイルと Audience Management {#ajo-troubleshooting-audiences}

+++ オーディエンス数の不一致を解決する方法は？

Adobe Journey Optimizerの **オーディエンスを読み取り** 機能の処理済みエントリ数は、期待されるオーディエンス数よりも少ない場合があります。 この問題は、多くの場合、名前空間の設定が正しくないことが原因で発生し、プロファイルがジャーニーから除外されます。 この解決策には、名前空間の設定の確認と修正、関連するドキュメントのレビュー、Adobe Journey Optimizerでの操作をよりスムーズにするための優先度の調整が含まれます。

この問題の解決方法については、[ このトラブルシューティングの記事 ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"} を参照してください。

[ 古いオーディエンス数に関するこの記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26166){target="_blank"} も参照してください。

ジャーニーの **オーディエンスを読み取り** アクティビティについて詳しくは [ このページ ](../building-journeys/read-audience.md) を参照してください。

+++

+++ プロファイルの更新が失敗する理由

Adobe Journey Optimizerでは、ジャーニーの **プロファイルを更新** アクティビティを実行した後、特定のフィールド値が正しく更新されない場合があります。 場合によっては、更新されたフィールドが消えたり、以前の状態に戻ったりすることがあります。 この問題に対処するには、競合するルールや条件がないかを確認し、権限の設定を確認し、「**プロファイルを更新**」アクティビティに一意のデータセットを使用し、他の取り込みプロセスが同じプロファイルに同時に書き込んでいないことを確認します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26352){target="_blank"} を参照してください。

ジャーニーの **プロファイルを更新** アクティビティについて詳しくは [ このページ ](../building-journeys/update-profiles.md) を参照してください。

データ取得に関する [Adobe Experience Platform ドキュメントも参照してください ](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/ingest-batch-data?lang=en#dataset-activity){target="_blank"}。

+++

+++ プロファイル数がジャーニーにエントリする場合と、関連するオーディエンスにエントリする場合に不一致があるのはなぜですか？

相違は、ジャーニーの実行時に現在の日付のスナップショットを使用できない場合に、ジャーニーが前日のプロファイルスナップショットを使用する場合に発生する可能性があります。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26253){target="_blank"} を参照してください。

詳しくは、[ このJourney Optimizer コミュニティの投稿 ](https://experienceleaguecommunities.adobe.com/t5/real-time-customer-data-platform/profile-snapshot-and-segment-qualification-troubleshooting/ba-p/698998){target="_blank"} を参照してください。

毎日のジョブがスケジュールされるタイミングを確認するには [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/schedules?lang=en){target="_blank"}Adobe Experience Platform スケジュール API ドキュメントも参照してください。

+++


+++ オーディエンス母集団の問題を解決するにはどうすればよいですか？

オーディエンス母集団の問題は、多くの場合、使用権限、プロビジョニング、権限の設定の誤りが原因で、コンポーネントやリソースが欠落しているときに発生します。 これらの問題を修正するには、まず、使用権限を検証し、正しいプロビジョニングを確認し、権限を確認します。 問題が解決しない場合は、ケースをエスカレーションし、サポートチームと調整して完全な解決を得ます。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26333){target="_blank"} を参照してください。

ジャーニーの **プロファイルを更新** アクティビティについて詳しくは [ このページ ](../building-journeys/update-profiles.md) を参照してください。

[Adobe Real-Time CDP プロファイルのドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide?lang=en#profile-detail){target="_blank"} も参照してください。

+++

+++ エンゲージメント可能なプロファイル数が短期間に大幅に増加したのはなぜですか？ 

**エンゲージメント可能なプロファイル** 指標は、過去 12 か月間にジャーニーまたはキャンペーンによってエンゲージメントされた一意のプロファイルの数を反映します。 大きなオーディエンスがターゲットになったり、データセットが変更されたりすると、急増する場合があります。 これを管理するには、**プロファイルカウントロジック** を確認し、大きなオーディエンスをターゲティングするジャーニーを調査し、ジャーニーレベルで **オーディエンスをフィルタリング**、**アドレス可能なオーディエンスサイズ** を小さくし、**データセットの変更** を監視します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26161){target="_blank"} を参照してください。

[ ライセンス使用状況ダッシュボード ](../audience/license-usage.md) を使用して、組織のライセンス使用状況と契約プロファイルを監視します

[Adobe Experience Platform クエリサービスの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/home?lang=en){target="_blank"} も参照してください。

+++

+++ 日付関数に基づいて対象オーディエンス以外の個人にメールが送信されるのはなぜですか？

**指定されたオーディエンス条件を満たさない** 受信者にメールが送信される場合があります。 例えば、償還日が **2025 年 7 月 4 日より前** のメンバーは、その日以降のメンバーのみを対象としたメールを受信できます。 この動作は、**オーディエンスセグメント化の設定が誤っている** または **プロファイル選定ロジックの予期しない変更** が原因で発生する可能性があります。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26173){target="_blank"} を参照してください。

日付関数について詳しくは [ このページ ](../../rp_landing_pages/date-landing-page.md) を参照してください。

+++

+++ ジャーニーを保存する際にオーディエンスの選択の問題とChrome エラーを解決する方法を教えてください。

ジャーニー条件にオーディエンスを追加すると、Chromeで **アプリケーションのクラッシュ** または **Aw Snap エラー** が発生する場合があります（ジャーニーの保存時のエラーを含む）。 これらの問題は、多くの場合、**Chromium サービス** に関連しています。 問題を解決するには、**ブラウザーのアップデート** を適用するか、適切な **回避策** を使用します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26145){target="_blank"} を参照してください。

+++

## ジャーニー {#ajo-troubleshooting-journeys}

### ジャーニーのバージョン {#ajo-troubleshooting-journey-versions}

+++ 新しいジャーニーバージョンを作成すると式が失われるのはなぜですか？  

新しいバージョンのジャーニーを作成すると、**特定のステップの式** が失われ、エラーが発生したり、手動で再入力する必要が生じたりする場合があります。 これを解決するには、**ジャーニーを複製**、再現性をテストし、**ブラウザーのリロードを回避**、古いジャーニーには **更新されたキャンバス** を使用します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26152){target="_blank"} を参照してください。

ジャーニーを複製する方法については [ このページ ](../building-journeys/journey-ui.md#duplicate-a-journey) を参照してください。

+++

### 入口と出口 {#ajo-troubleshooting-journeys-exit}

+++ プロファイルがジャーニーを途中で終了するのはなぜですか？ 

送信されたメッセージの **条件チェックフィードバックステータス** が正しく設定されていない場合、プロファイルは、指定されたノードを通過せずにジャーニーを予期せず終了する場合があります。 これを解決するには、**条件ロジック** を確認し、**代替ロジック** を実装するか、**実装チーム** に問い合わせます。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26127){target="_blank"} を参照してください。

[ジャーニー設計ガイドライン ](../building-journeys/using-the-journey-designer.md) も参照してください。

+++


+++ プロファイルがジャーニーから予期せず離脱するのはなぜですか？

**イベントキャッピング** が発生すると、プロファイルが予期せずジャーニーを終了する可能性があり、処理されたイベントの数がシステムの処理能力を超えると、一部のプロファイルが破棄されます。 プロファイルの離脱を減らすには、**システム制限** を理解し、**イベントスパイク** を監視し、**データフロー** を最適化してしきい値の超過を防ぎます。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26018){target="_blank"} を参照してください。

[ジャーニーガードレール ](../start/guardrails.md#journey-guardrails) も参照してください。

+++

### イベント {#ajo-troubleshooting-journey-events}

+++ イベントが目的のジャーニーをトリガーしないのはなぜですか？  

イベントは、すべての条件が満たされた場合でも、**データ収集コアサービス（DCCS）にストリーミングされるのではなく** クエリサービスを通じて作成された **ジャーニーをトリガーに** きません。 これを解決するには、イベントの設定を確認し、イベントが **DCCS に直接ストリーミング** されていることを確認し、**テストモード** を使用して機能を検証します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26031){target="_blank"} を参照してください。

イベントについて詳しくは [ このページを参照 ](../event/about-events.md)。

[ジャーニーイベントガードレール ](../start/guardrails.md#events) も参照してください。

+++


+++ Adobe Journey Optimizerでオーディエンスが変更された後のジャーニートリガーの問題を解決するにはどうすればよいですか？ 

結合ポリシーの変更など、関連するオーディエンスに対する変更の後にジャーニーがトリガーを停止した場合、フローが中断される可能性があります。 これを解決するには、トリガーが正しく機能するように、更新したオーディエンス設定を使用して **ジャーニーを複製および再公開** します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26224){target="_blank"} を参照してください。

ジャーニーを複製する方法については [ このページ ](../building-journeys/journey-ui.md#duplicate-a-journey) を参照してください。

+++

### カスタムアクション {#ajo-troubleshooting-journeys-actions}

+++ 外部のサードパーティエンドポイントを呼び出すカスタムアクションがタイムアウトするのはなぜですか？

**カスタムアクション** が外部のサードパーティエンドポイントを呼び出すと、タイムアウトエラーが発生する場合があります。 これを解決するには、**エンドポイントがアクセス可能** であることを確認し、**サーバーログ** をチェックし、**Adobeからのブロックがない** ことを確認し、必要に応じてエンドポイント設定を更新し、**更新後のテスト** を行います。 また、**API 呼び出しのタイムアウトの仕様** にも注意してください。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26156){target="_blank"} を参照してください。

ジャーニースロットル API について詳しくは [ このページ ](../configuration/throttling.md) を参照してください。

[ 外部システムとの統合に関するドキュメント ](../configuration/external-systems.md) も参照してください。

+++

## ルール {#ajo-troubleshooting-rules}

+++ キャッピングルール ドロップダウンが機能しないのはなぜですか？

**キャッピングルール** ドロップダウンの問題は、ルールセットが **設定が正しくない** または **アクセスできない** 場合に発生することがよくあります。 すべてのルールセットが正しく設定され、問題を解決できる状態になっていることを確認します。

詳しくは、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26204){target="_blank"} を参照してください。

キャッピングルールを適用する方法については、この節 [ を参照し ](../conflict-prioritization/rule-sets.md) ください。

+++

## 決定 {#ajo-troubleshooting-decisioning}

+++ オファーコレクションを作成する際の問題を解決する方法

オファーコレクションの作成で問題が発生するのは、組織に **カタログがプロビジョニングされていない** 場合です。 これを解決するには、オファーコレクションを作成する前に、必要なすべてのカタログが正しくプロビジョニングされていることを確認します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26265){target="_blank"} を参照してください。

オファーコレクションについて詳しくは [ このページを参照 ](../offers/offer-library/creating-collections.md)。

+++

+++ Offer Decisioningにアクセスできないのはなぜですか？  

Adobe TargetをAdobe Journey Optimizerを使用してアプリケーションに統合する場合、**Offer Decisioning** オプションにデータストリーム設定内でアクセスできない可能性があります。 これは通常、**権限設定** または **プロビジョニングの制約** が原因で発生します。 この問題を解決するには、ユーザー権限を検証し、必要なプロビジョニングが行われていることを確認します。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26175){target="_blank"} を参照してください。

Offer Decisioningに必要な権限について詳しくは [ このページを参照 ](../offers/get-started/starting-offer-decisioning.md#granting-acess-to-decision-management)。

+++



## 多言語 {#ajo-troubleshooting-multilingual}

+++ `Message validation error (CJMMAS - 1069-500)` でこの問題を解決する方法

Adobe Journey Optimizerでは、多言語機能にリンクされたメッセージ検証エラー（CJMMAS - 1069-500）により、ジャーニーがテストモードに設定されたり、公開されたりすることができません。

この問題を解決する手順については、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26168){target="_blank"} を参照してください。

多言語コンテンツについて詳しくは [ このページ ](../content-management/multilingual-gs.md) を参照してください。

+++


## 設定 {#ajo-troubleshooting-config}

### セキュリティ {#ajo-troubleshooting-security}

+++ カスタムアクションに対して TLS v1.3 を有効にするにはどうすればよいですか？  

サードパーティシステムに接続する際に **データの整合性とセキュリティ** を維持するには、Transport Layer Security （**TLS**） v1.3 がカスタムアクションに対して有効になっていることを確認します。 これにより、通信を保護し、潜在的なセキュリティの脆弱性を防ぐことができます。


詳しくは、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26223){target="_blank"} を参照してください。

多言語コンテンツについて詳しくは [ このページ ](../action/about-custom-action-configuration.md) を参照してください。

+++

### ダッシュボード {#ajo-troubleshooting-dashboards}

+++ Adobe Journey Optimizerのクエリから直接ダッシュボードを作成できないのはなぜですか？ 

Adobe Journey Optimizerでは、クエリから直接ダッシュボードを作成することはできません。 ダッシュボードを作成するには、Adobe Experience Platform内で使用可能な **ダッシュボード作成機能** を使用します。これにより、クエリデータを効果的に視覚化して分析できます。

詳しくは、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26201){target="_blank"} を参照してください。

+++

## API {#ajo-troubleshooting-apis}

+++ Query Service API でのアクセスの問題を解決する方法を教えてください。  

Postmanや同様のツールを使用して **Query Service API** を使用する際にアクセスエラーが発生する場合、通常は **権限が不十分** ことが原因です。 これを解決するには、ユーザーの権限を確認し、API 資格情報を確認し、必要に応じてサポートに詳細情報を提供します。

詳しくは、[ このトラブルシューティング記事 ](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-26196){target="_blank"} を参照してください。

[API 資格情報の管理ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions?lang=en#manage-api-credentials-for-role){target="_blank"} も参照してください。

+++

