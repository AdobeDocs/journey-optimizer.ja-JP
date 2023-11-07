---
solution: Journey Optimizer
product: journey optimizer
title: エラーリスト
description: 送信中に発生したエラーの詳細を表示します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: deaa72f235a64dd2cb9bfbafef3574fdb025a026
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 9%

---

# エラー理由リスト {#error-list}

| 除外の理由 | エラーコード | チャネル | 説明 |
|-|-|-|-|
| RuntimeDispatchError | 050301 | すべてのチャネル | 任意の Runtime ディスパッチエラーに対する汎用の除外イベント。 |
| RuntimeRenderingError | 050302 | すべてのチャネル | Runtime レンダリングエラーの一般的な除外イベント。 |
| NamespaceErrorForExperimentation | 050017 | すべてのチャネル | 除外イベントは、Experiment の名前空間がプロファイルの名前空間と異なる場合に生成されます。 |
| ExperimentationHoldoutExclusion | 050018 | すべてのチャネル | この除外イベントは、実験の対象となる処理が「除外」の場合に生成されます。 |
| ExcludedForControlRules | 050002 | すべてのチャネル | この除外イベントは、現在のメッセージの配信によって、1 ヶ月で許可される E メールの数など、制御ルールに違反した場合に生成されます。 |
| DirectMailNoVariantDefined | 050062 | DirectMail | 除外イベントは、ダイレクトメールバリアントでが定義されていない場合に生成されます。 |
| DirectMailNoMessageFoundForTreatment | 050061 | DirectMail | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
| EmailNoConsent | 050101 | メール | 除外イベントは、ユーザーがマーケティング E メールの受信をオプトアウトしたときに生成されます。 |
| 抑制 | 050107 | メール | 抑制の理由の 1 つによる除外。 |
| EmailSuppressed | 050102 | メール | 除外イベントは、ターゲット E メールが抑制されると生成されます。 |
| DomainSuppressed | 050105 | メール | 除外イベントは、ターゲット E メールのドメインが抑制されると生成されます。 |
| NotAllowed | 050108 | メール | 除外イベントは、除外が有効になっていて、許可リスト先の E メールが許可リストから除外された場合に生成されます。 |
| EmailNotAllowed | 050103 | メール | 除外イベントは、除外が有効になっていて、許可リスト先の E メールが許可リストから除外された場合に生成されます。 |
| DomainNotAllowed | 050106 | メール | 除外イベントは、許可リストが有効で、ターゲット E メールのドメインがドメインから除外された場合に生成されます。許可リスト |
| EmailNoSubscriberIdFoundInProfile | 050025 | メール | 除外イベントは、購読 E メールのプロファイルに subscriberId が見つからない場合に生成されます。 |
| EmailNoAddressFoundInProfile | 050020 | メール | 除外イベントは、実行アドレスに電子メールアドレスが見つからない場合に生成されます。 |
| EmailNoAddressDefinedInPreset | 050021 | メール | 除外イベントは、実行アドレスがサーフェスで定義されていない場合に生成されます。 |
| EmailNoVariantDefined | 050026 | メール | 除外イベントは、E メールメッセージでバリアントが定義されていない場合に生成されます。 |
| EmailNoMessageFoundForTreatment | 050027 | メール | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
| EmailMalformatedAddress | 050024 | メール | 除外イベントは、E メールに正しくないアドレスが含まれている場合に生成されます。 |
| InAppNoVariantDefined | 050041 | InApp | InApp メッセージのバリアントが定義されていない場合、除外イベントが生成されます。 |
| InAppNoMessageFoundForTreatment | 050042 | InApp | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
| PushNoTokenFoundInProfile | 050030 | プッシュ | 除外イベントは、プロファイルにプッシュトークンがない場合に生成されます。 |
| PushNoValidTokenFoundForApps | 050031 | プッシュ | 除外イベントは、サーフェスにターゲットアプリの有効なトークンが見つからない場合に生成されます。 |
| PushMalformedProfile | 050034 | プッシュ | プロファイルの pushNotificationDetails の形式が正しくない場合、除外イベントが生成されます。 |
| PushNoConsent | 050111 | プッシュ | 除外イベントは、ユーザーがマーケティングプッシュ通知をオプトアウトした場合に生成されます。 |
| PushNoApplicationDefinedInPreset | 050033 | プッシュ | 除外イベントは、サーフェスにターゲット設定するアプリケーションが含まれていない場合に生成されます。 |
| PushNoVariantDefined | 050035 | プッシュ | バリアントが定義されていない場合、除外イベントが生成されます。 |
| PushNoMessageFoundForTreatment | 050036 | プッシュ | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
| SMSNoConsent | 050104 | SMS | 除外イベントは、ユーザーがマーケティング SMS をオプトアウトしたときに生成されます。 |
| SMSFromNumberNotDefinedInPreset | 050152 | SMS | サーフェスで「FromNumber」が定義されていない場合、除外イベントが生成されます。 |
| SMSNoToNumberDefinedInProfile | 050153 | SMS | サーフェスで「ToNumber」が定義されていない場合、除外イベントが生成されます。 |
| SMSNoVariantDefined | 050154 | SMS | バリアントが定義されていない場合、除外イベントが生成されます。 |
| SMSNoMessageFoundForTreatment | 050155 | SMS | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
| WebNoVariantDefined | 050041 | Web | 除外イベントは、Web メッセージのバリアントが定義されていない場合に生成されます。 |
| WebNoMessageFoundForTreatment | 050042 | Web | 除外イベントは、メッセージに対する実験が有効になっていて、適格な治療のためのメッセージが見つからない場合に生成されます。 |
