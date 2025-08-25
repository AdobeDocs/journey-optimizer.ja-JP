---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのエクスペリエンスイベント参照
description: ジャーニーのエクスペリエンスイベント参照の使用方法について説明します
exl-id: 35e2e347-0669-44a3-92ba-aee52e54c219
source-git-commit: a587b8754e94781b7735f3d7d5abb9b9767a74a5
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 97%

---

# ジャーニーのエクスペリエンスイベント参照 {#ee-journeys}

>[!CAUTION]
>
>2025年7月8日（PT）以降、新しい顧客組織では、ジャーニー条件で使用される式エディターで、エクスペリエンスイベントを使用した式の作成はサポートされなくなります。その結果、[Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)のエクスペリエンスイベントは式の作成に使用できません。エクスペリエンスイベントを使用して式／ロジックを作成する別のアプローチとベストプラクティスについて詳しくは、以下を参照してください。
>
>さらに詳細が必要ですか？[詳しくは、FAQ を参照してください](#faq-ee)。

このページでは、Adobe Journey Optimizer のエクスペリエンスイベントを最大限に活用する一般的なパターンとスケーラブルなアプローチについて説明します。これらのユースケースは、オプトアウトの管理、メッセージ頻度の制御、ユーザー行動に基づくコンテンツのパーソナライズ、リアルタイムシグナルへの対応など、頻繁に発生する課題の解決に役立つように設計されています。

これらの戦略を活用することで、行動データを意味のあるアクションに変換し、トリガーされるイベントやプロファイルが持つ属性に基づきプロファイルを抑制、選定、除外できます。購入しきい値、放棄トリガー、バウンス処理のロジックを作成している場合でも、これらの例では、ニーズに合わせて調整できる実践的なガイダンスを提供します。

最適なアプローチを評価する際には、ジャーニーのレスポンシブで効果的な状態を維持できるように、ユースケースの待ち時間の要件を考慮します。

## オプトアウト抑制

マーケティング通信をオプトアウトしたプロファイルを抑制するには、ビルトインの同意管理を使用します。オプトアウト環境設定は、プロファイルの同意フィールドに自動的に取り込まれ、ジャーニー条件で直接参照でき、メッセージ配信中に Journey Optimizer によって自動的に適用されます。

詳細情報：

* [同意を管理](../privacy/opt-out.md)
* [メールオプトアウトの管理](../email/email-opt-out.md)
* [テキストメッセージのオプトアウト管理](../sms/sms-opt-out.md)


## バウンスベースの抑制

メールバウンスが発生したプロファイルを除外するには、Adobe Journey Optimizer のバウンスしたアドレスの自動抑制リストを活用します。このビルトインメカニズムにより、カスタムロジックを必要とせずに、無効なメールや未到達メールが今後の送信から除外されます。

詳細情報：

* [抑制リストの管理](../configuration/manage-suppression-list.md)


## 汎用抑制

特定の動作を示したプロファイルを抑制するには、イベントベースのロジックを備えたバッチオーディエンスを使用して、抑制条件を満たすプロファイルを取得します。ジャーニー条件でこのオーディエンスを参照します。

詳細情報：

* Adobe Experience Platform [セグメントビルダー - イベント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [セグメントビルダー - 時間制約](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience() 関数](../building-journeys/functions/functioninaudience.md)


## 通信受信の除外

最近の時間枠内に通信を受信したプロファイルにメッセージを送信しないようにするには：

* 時間ベースの条件を持つバッチオーディエンスを使用し、ジャーニー条件で参照します。
* フリークエンシーキャップのビジネスルールを適用して、毎日または毎週のメッセージ制限を適用します。


オーディエンスの使用の詳細情報：

* Adobe Experience Platform [セグメントビルダー - イベント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [セグメントビルダー - 時間制約](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience() 関数](../building-journeys/functions/functioninaudience.md)


関連トピック:

* [チャネルと通信タイプによるフリークエンシーキャップ](../conflict-prioritization/channel-capping.md)



## メッセージ固有の包含／除外

特定のメッセージを受信したかどうかに基づいてプロファイルを含めるか除外するには、このロジックをカプセル化し、ジャーニー条件で参照するバッチオーディエンスを作成します。


詳細情報：

* Adobe Experience Platform [セグメントビルダー - イベント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [セグメントビルダー - 時間制約](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [条件でのオーディエンスの使用](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [inAudience() 関数](../building-journeys/functions/functioninaudience.md)

## 買い物かごまたは参照放棄のパーソナライゼーション

最新の買い物かごに基づいて通信をパーソナライズしたり、複数の買い物かごタイプや製品ビューをまたいでイベントを参照するには：

* [Adobe Experience Platform Data Distiller](https://experienceleague.adobe.com/ja/docs/experience-platform/query/data-distiller/overview){target="_blank"} へのアクセス権がある場合は、自動クエリを設定してイベントから必要なデータを抽出し、ユースケースに合わせて操作し、アクティブ化にプロファイル対応データセットに書き戻します。
* スカラー属性を使用してプロファイルで放棄データをモデル化できる場合は、計算属性を使用して最新情報を取得し、ジャーニーでこれらの属性を参照して通信を構築することを考慮します。[詳しくは、Adobe Experience Platform ドキュメントを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}


## 行動ベースのジャーニー終了

プロファイルが特定の動作を示した際にそのプロファイルをジャーニーから削除するには、特定のイベントを受信した場合や、プロファイルが特定のオーディエンスを選定した場合に、終了条件を使用してプロファイルをジャーニーから終了させます。

詳細情報：

* [ジャーニーのプロパティの設定 - 終了条件](journey-properties.md#exit-criteria)

## 値のしきい値を使用した購入ベースの選定

購入に基づいてジャーニーをトリガーし、値がしきい値を上回る／下回る場合に抑制するには、計算属性を定義して、特定の期間の購入を合計します。支出額が特定の条件を満たすプロファイルを含むオーディエンスを作成します。

詳細情報：

* Adobe Experience Platform [計算属性の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}



## よくある質問 {#faq-ee}

ジャーニーの式／条件でのエクスペリエンスイベントの使用はサポートされなくなりました。影響について詳しくは、以下の FAQ を参照してください。

+++影響を受ける特定の機能 

式エディターでのエクスペリエンスイベントの検索のみが影響を受けます。次の機能は影響を受け&#x200B;**ず**、同じままです。

* プロファイル UI での特定のプロファイルに関連付けられたエクスペリエンスイベントの監視

* 計算属性ルールでのエクスペリエンスイベントの使用と、ジャーニーでの計算属性へのアクセス

* 単一イベントまたはビジネスイベントを使用したジャーニーのトリガー

* 式およびパーソナライゼーションエディターで、ジャーニーをトリガーするイベントのジャーニーコンテキストデータの使用

* ジャーニー内のイベントのリッスン

* ジャーニーをトリガーするイベントの設定

* マーケティング通信に対するエンドユーザーの反応イベント（メールの開封など）の検出

+++

+++既存のAdobe組織は、この更新の影響を受けますか？ 

アドビ組織が影響を受けるのは、エクスペリエンスイベント参照をまだ使用していない場合のみです。[Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)で既にエクスペリエンスイベントを使用している場合、アドビ組織では引き続きエクスペリエンスイベント参照をサポートします。

+++

+++新しいAdobe組織があります。 エクスペリエンスイベントデータを必要とするユースケースを解決するにはどうすればよいですか？ 

目的のユースケースを実現するには、上記のエクスペリエンスイベントに関する別のアプローチとベストプラクティスが使用できます。

+++

+++ 別のアプローチが私のユースケースに適していない場合はどうすればよいですか？

上記の別のアプローチのいずれかを使用してユースケースを解決できない場合は、アドビ担当者にお問い合わせください。

+++
