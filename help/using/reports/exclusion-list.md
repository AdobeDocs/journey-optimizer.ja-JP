---
solution: Journey Optimizer
product: journey optimizer
title: 除外リスト
description: 送信中に発生した除外の詳細情報
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: a34ba1a8-87d5-4f9c-a181-2f49e74e8f09
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 100%

---

# 除外の理由 {#exclusion-list}

| 除外の理由 | エラーコード | チャネル | 説明 |
|-|-|-|-|
| RuntimeDispatchError | 050301 | すべてのチャネル | 任意のランタイムディスパッチエラーの汎用除外イベント。 |
| RuntimeRenderingError | 050302 | すべてのチャネル | 任意のランタイムレンダリングエラーの汎用除外イベント。 |
| NamespaceErrorForExperimentation | 050017 | すべてのチャネル | 除外イベントは、実験の名前空間がプロファイルの名前空間と異なる場合に生成されます。 |
| ExperimentationHoldoutExclusion | 050018 | すべてのチャネル | この除外イベントは、実験の対象となる処理が「除外」である場合に生成されます。 |
| ExcludedForControlRules | 050002 | すべてのチャネル | この除外イベントは、現在のメッセージの配信が制御ルール（例：1 か月に許可されるメールの数）に違反する場合に生成されます。 |
| DirectMailNoVariantDefined | 050062 | DirectMail | 除外イベントは、ダイレクトメールのバリアントが定義されていない場合に生成されます。 |
| DirectMailNoMessageFoundForTreatment | 050061 | DirectMail | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
| EmailNoConsent | 050101 | メール | 除外イベントは、ユーザーがマーケティングメールの受信をオプトアウトした場合に生成されます。 |
| Suppressed | 050107 | メール | 抑制理由の 1 つによる除外。 |
| EmailSuppressed | 050102 | メール | 除外イベントは、ターゲットメールが抑制される場合に生成されます。 |
| DomainSuppressed | 050105 | メール | 除外イベントは、ターゲットメールのドメインが抑制される場合に生成されます。 |
| NotAllowed | 050108 | メール | 除外イベントは、許可リストが有効になっていて、ターゲットメールが許可リストから除外される場合に生成されます。 |
| EmailNotAllowed | 050103 | メール | 除外イベントは、許可リストが有効になっていて、ターゲットメールが許可リストから除外される場合に生成されます。 |
| DomainNotAllowed | 050106 | メール | 除外イベントは、許可リストが有効になっていて、ターゲットメールのドメインが許可リストから除外される場合に生成されます。 |
| EmailNoSubscriberIdFoundInProfile | 050025 | メール | 除外イベントは、購読メールのプロファイルに subscriberId が見つからない場合に生成されます。 |
| EmailNoAddressFoundInProfile | 050020 | メール | 除外イベントは、実行アドレスにメールアドレスが見つからない場合に生成されます。 |
| EmailNoAddressDefinedInPreset | 050021 | メール | 除外イベントは、設定で実行アドレスが定義されていない場合に生成されます。 |
| EmailNoVariantDefined | 050026 | メール | 除外イベントは、メールメッセージでバリアントが定義されていない場合に生成されます。 |
| EmailNoMessageFoundForTreatment | 050027 | メール | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
| EmailMalformedAddress | 050024 | メール | 除外イベントは、メールに不正なアドレスが含まれている場合に生成されます。 |
| InAppNoVariantDefined | 050041 | アプリ内 | 除外イベントは、アプリ内メッセージのバリアントが定義されていない場合に生成されます。 |
| InAppNoMessageFoundForTreatment | 050042 | アプリ内 | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
| PushNoTokenFoundInProfile | 050030 | プッシュ | 除外イベントは、プロファイルにプッシュトークンがない場合に生成されます。 |
| PushNoValidTokenFoundForApps | 050031 | プッシュ | 除外イベントは、設定でターゲットアプリの有効なトークンが見つからない場合に生成されます。 |
| PushMalformedProfile | 050034 | プッシュ | 除外イベントは、プロファイルの pushNotificationDetails の形式が正しくない場合に生成されます。 |
| PushNoConsent | 050111 | プッシュ | 除外イベントは、ユーザーがマーケティングプッシュ通知をオプトアウトした場合に生成されます。 |
| PushNoApplicationDefinedInPreset | 050033 | プッシュ | 除外イベントは、設定にターゲットとなるアプリケーションが含まれていない場合に生成されます。 |
| PushNoVariantDefined | 050035 | プッシュ | 除外イベントは、バリアントが定義されていない場合に生成されます。 |
| PushNoMessageFoundForTreatment | 050036 | プッシュ | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
| SMSNoConsent | 050104 | SMS | 除外イベントは、ユーザーがマーケティング SMS をオプトアウトした場合に生成されます。 |
| SMSFromNumberNotDefinedInPreset | 050152 | SMS | 除外イベントは、設定で「FromNumber」が定義されていない場合に生成されます。 |
| SMSNoToNumberDefinedInProfile | 050153 | SMS | 除外イベントは、設定で「ToNumber」が定義されていない場合に生成されます。 |
| SMSNoVariantDefined | 050154 | SMS | 除外イベントは、バリアントが定義されていない場合に生成されます。 |
| SMSNoMessageFoundForTreatment | 050155 | SMS | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
| WebNoVariantDefined | 050041 | Web | 除外イベントは、web メッセージのバリアントが定義されていない場合に生成されます。 |
| WebNoMessageFoundForTreatment | 050042 | Web | 除外イベントは、メッセージに対して実験が有効になっていて、対象となる処理に対するメッセージが見つからない場合に生成されます。 |
