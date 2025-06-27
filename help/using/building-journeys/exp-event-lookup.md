---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーでのエクスペリエンスイベントの参照
description: ジャーニーでエクスペリエンスイベント参照を使用する方法を説明します
source-git-commit: 190d7d5fd5cb93a6ddf3757e00f42a9714a1f722
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 6%

---


# ジャーニーでのエクスペリエンスイベント参照 {#ee-journeys}

>[!CAUTION]
>
>7 月 8 日（PT）以降、新しい顧客組織では、エクスペリエンスイベントを使用した式の作成が、ジャーニー条件で使用される式エディターでサポートされなくなります。 その結果、[Experience Platform データソース ](../datasource/adobe-experience-platform-data-source.md) のエクスペリエンスイベントは式の作成に使用できません。 エクスペリエンスイベントを使用して式やロジックを作成するための代替アプローチやベストプラクティスについては、以下を参照してください。
>
>詳細が必要な場合 [FAQ を読む ](#faq-ee)。

このページでは、Adobe Journey Optimizerのエクスペリエンスイベントを最大限に活用するための一般的なパターンとスケーラブルなアプローチについて説明します。 これらのユースケースは、オプトアウトの管理、メッセージ頻度の制御、ユーザー行動に基づくコンテンツのパーソナライズ、リアルタイムシグナルへの反応など、頻繁に発生する課題を解決するのに役立つように設計されています。

これらの戦略を活用することで、行動データを意味のあるアクションに変換し、トリガーするイベントや持つ属性に基づいてプロファイルを抑制、選定、除外できます。 購入しきい値、放棄トリガー、バウンス処理などのロジックを構築している場合でも、これらの例では、ニーズに合わせた実践的なガイダンスを提供します。

どのアプローチが最適かを評価する際には、ジャーニーのレスポンシブで効果的な状態を維持できるように、ユースケースの待ち時間の要件を考慮してください。

## オプトアウト抑制

マーケティングコミュニケーションをオプトアウトしたプロファイルを抑制するには、ビルトインの同意管理を使用します。 オプトアウト環境設定は、プロファイルの同意フィールドに自動的に取り込まれます。これらは、ジャーニー条件で直接参照でき、メッセージ配信中にJourney Optimizerによって自動的に適用されます。

詳細情報：

* [同意を管理](../privacy/opt-out.md)
* [メールオプトアウトの管理](../email/email-opt-out.md)
* [テキストメッセージのオプトアウト管理](../sms/sms-opt-out.md)


## バウンスベースの抑制

メールバウンスが発生したプロファイルを除外するには、バウンスアドレス用のAdobe Journey Optimizerの自動抑制リストを活用します。 この組み込みメカニズムにより、カスタムロジックを必要とせずに、無効なメールや到達できないメールが今後の送信から除外されます。

詳細情報：

* [抑制リストの管理](../configuration/manage-suppression-list.md)


## 汎用抑制

特定の動作を示したプロファイルを抑制するには、イベントベースのロジックを持つバッチオーディエンスを使用して、抑制条件を満たすプロファイルを取得します。 ジャーニー条件でこのオーディエンスを参照します。

詳細情報：

* Adobe Experience Platform[ セグメントビルダー – イベント ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform[ セグメントビルダー – 時間制約 ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience （）関数](../building-journeys/functions/functioninaudience.md)


## 通信が受信した除外

最近の時間枠内に通信を受信したプロファイルにメッセージを送信しないようにするには、次の手順を実行します。

* 時間ベースの条件でバッチオーディエンスを使用し、ジャーニー条件で参照します。
* フリークエンシーキャップのビジネスルールを適用して、毎日または毎週のメッセージ制限を適用します。


オーディエンスの使用について詳しくは、以下を参照してください。

* Adobe Experience Platform[ セグメントビルダー – イベント ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform[ セグメントビルダー – 時間制約 ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience （）関数](../building-journeys/functions/functioninaudience.md)


関連トピック:

* [チャネルと通信タイプによるフリークエンシーキャップ](../conflict-prioritization/channel-capping.md)



## メッセージ固有の包含/除外

特定のメッセージを受信したかどうかに基づいてプロファイルを含めたり除外したりするには、このロジックをカプセル化してジャーニー条件で参照するバッチオーディエンスを作成します。


詳細情報：

* Adobe Experience Platform[ セグメントビルダー – イベント ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform[ セグメントビルダー – 時間制約 ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience （）関数](../building-journeys/functions/functioninaudience.md)

## 買い物かごまたは閲覧放棄のパーソナライゼーション

最新の買い物かごに基づいて通信をパーソナライズしたり、複数の買い物かごタイプまたは製品表示をまたいでイベントを参照したりするには：

* [Adobe Experience Platform Data Distiller](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview){target="_blank"} にアクセスできる場合は、自動クエリを設定してイベントから必要なデータを抽出し、ユースケースに合わせて操作してから、アクティブ化のためにプロファイル対応データセットに書き戻します。
* 放棄データをスカラー属性を持つプロファイルをモデル化できる場合は、計算済み属性を使用して最新の情報を取得してから、ジャーニーでこれらの属性を参照して通信を構築することを検討してください。 [詳しくは、Adobe Experience Platform ドキュメントを参照してください](https://experienceleague.adobe.com/en/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}


## 行動ベースのジャーニー終了

特定の動作を示した場合にプロファイルをジャーニーから削除するには、特定のイベントを受信した場合またはプロファイルが特定のオーディエンスに該当する場合に、終了条件を使用してジャーニーからプロファイルを終了します。

詳細情報：

* [ジャーニープロパティの設定 – 終了条件](journey-properties.md#exit-criteria)

## 値のしきい値を使用した購入ベースの選定

購入に基づいてジャーニーのトリガーを設定し、値がしきい値を超えたり下回ったりした場合に抑制するには、計算済み属性を定義して、特定の期間の購入を合計します。 支出額が特定の条件を満たすプロファイルを含むオーディエンスを作成します。

詳細情報：

* Adobe Experience Platform[ 計算済み属性の概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}



## よくある質問 {#faq-ee}

ジャーニー式/条件でのエクスペリエンスイベントの使用はサポートされなくなりました。 影響については、以下の FAQ を参照してください。

+++影響を受ける特定の機能

式エディターでのエクスペリエンスイベントの参照のみが影響を受けます。 次の機能は影響を受けず **同じまま** す。

* プロファイル UI での特定のプロファイルに関連付けられたエクスペリエンスイベントの監視

* 計算属性ルールでのエクスペリエンスイベントの使用と、ジャーニーでの計算属性へのアクセス

* 単一イベントまたはビジネスイベントを使用したジャーニーのトリガー

* 式およびパーソナライゼーションエディターで、ジャーニーをトリガーするイベントのジャーニーコンテキストデータを使用する

* ジャーニー内のイベントのリッスン

* ジャーニーをトリガーにするイベントの設定

* マーケティングコミュニケーション（電子メールの開封など）に対するエンドユーザーの反応イベントの検出

+++

+++この更新により、既存のAdobe組織は影響を受けますか？

Adobe組織が影響を受けるのは、エクスペリエンスイベントルックアップをまだ使用していない場合のみです。 [Experience Platform データソース ](../datasource/adobe-experience-platform-data-source.md) で既にエクスペリエンスイベントを使用している場合、Adobe組織では引き続きエクスペリエンスイベントの検索がサポートされます。

+++

+++新しいAdobe組織があります。 エクスペリエンスイベントデータが必要なユースケースを解決するにはどうすればよいですか？

上記で、目的のユースケースを達成するための代替アプローチと、エクスペリエンスイベントに関するベストプラクティスを利用できます。

+++

+++ 代替のアプローチがユースケースに適していない場合はどうすればよいですか？

上記の代替方法のいずれかを使用してユースケースを解決できない場合は、Adobe担当者にお問い合わせください。

+++
