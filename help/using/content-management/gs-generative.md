---
solution: Journey Optimizer
product: journey optimizer
title: AI アシスタントの基本を学ぶ
description: Journey Optimizer の AI アシスタントへのアクセスおよび操作方法を説明します
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
exl-id: 6e291ce3-f324-4e5d-975b-5229dea4d581
source-git-commit: 392fe9d87e1061a2ba40fbcae042cd1a0891a829
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 99%

---

# AI アシスタントの基本を学ぶ {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="AI アシスタント"
>abstract="配信を作成してパーソナライズしたら、AI アシスタントを使用してコンテンツを強化できます。この機能により、何を生成したいかを記述して、コンテンツを微調整できるので、パーソナライゼーションとコンテンツの改善のプロセスが簡素化されます。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="ブランドアセットのアップロード"
>abstract="ブランドアセットをアップロードメニューを使用すると、AI アシスタントに追加のコンテキストを提供できるコンテンツを含むブランドアセットを追加するか、以前にアップロードしたアセットを選択することができます。このオプションにより、AI アシスタントは機能と関連性を高めるために必要なすべての資料にアクセスできます。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe 生成 AI 用語"
>abstract="この機能にアクセスするには、Adobe Experience Cloud 生成 AI ユーザーガイドラインに同意する必要があります。この機能からの出力の正確性を確認し、ユースケースに適していることを確認してください。"
>additional-url="https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html" text="Adobe 生成 AI ユーザーガイドライン"

>[!BEGINSHADEBOX]

**目次**

* AI アシスタントの基本を学ぶ
* [AI アシスタントを使用したメールの生成](generative-email.md)
* [AI アシスタントを使用した SMS の生成](generative-sms.md)
* [AI アシスタントを使用したプッシュの生成](generative-push.md)
* [AI アシスタントを使用したコンテンツ実験](generative-experimentation.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>現在、Adobe Journey Optimizer の AI アシスタントは、一部のユーザーのみがベータ版として利用できます。

Azure OpenAI を利用した Adobe Journey Optimizer の AI アシスタントは、テキストと画像に対するプロアクティブなコンテンツバリエーションの提案を提供します。メール、プッシュ、SMS の各チャネルで使用できます。この新しい機能は、プロンプトベースのテキストおよび画像の生成を提供します。画像の生成は、Adobe Firefly で管理されます。

Journey Optimizer の AI アシスタントを使用して、様々なメインタイトルや画像を試すことで、メッセージの影響を最適化します。複数のバリアントを生成し、それらを比較する実験を作成します。Journey Optimizer のコンテンツ実験を使用すると、ターゲットオーディエンスに最適なパフォーマンスを発揮するのはどれかを測定するために、複数のメッセージ処理を定義できます。配信コンテンツまたは件名を変更できます。メッセージオーディエンスが各処理にランダムに割り当てられて、指定の指標に関して最も効果が高い処理が判断されます。コンテンツ実験について詳しくは、[この節](../content-management/content-experiment.md)を参照してください。

## ガードレールと制限 {#generative-guardrails}

メールの生成に Journey Optimizer の AI アシスタントを使用する際の一般的なガイドラインは次のとおりです。

* 生成されるコンテンツの品質は、定義したマーケティング目標／プロンプトに強く影響されます。生成 AI モデルが正確に解釈できるように、明確に定義されたプロンプトを使用します。 
* 正確な情報が得られるように、ブランドコンテンツでブランドアセットをアップロードします。それ以外の場合、コンテンツは、公開されている情報に基づきます。アップロードされるコンテンツの形式は、PDF、JPEG、PNG、ZIP ファイル（サポートされているファイル形式を含む）のいずれかです。
* アップロードされるブランドアセットの最大サイズは 50 MB です。サイズの大きいファイルや多数の画像を処理できますが、処理時間は長くなります。
* Adobe Campaign で作成したメールテンプレート（[ビルトインのメールテンプレート](../email/use-email-templates.md)、ブランド固有のテンプレート、またはカスタムテンプレートをお勧めします）を使用して、メールコンテンツを作成します。最大 8〜10 個の画像を含むメールテンプレートをお勧めします。
* バリアントを選択する際は、サムアップ、サムダウンまたはフラグのアイコンを使用して、問題のある出力を報告する必要があります。
* AI アシスタントの使用には、Adobe Experience Cloud 生成 AI ユーザーガイドラインが適用されます。[詳細情報](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html)

Journey Optimizer の AI アシスタントには、次の制限が適用されます。

* サポートされている言語は英語のみです。
* メール、プッシュ、SMS チャネルでのみ使用できます。
* 生成 AI コンテンツは必ずしも正確ではない可能性があります。エンジニアがモデルを改良できるよう、フィードバックをお寄せください。
* 複数のブランドアセットをアップロードできますが、特定の世代に活用できるのは 1 つだけです。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="generative-email.md">
<img alt="メールの生成" src="assets/do-not-localize/text-genai.jpeg">
</a>
<div>
<a href="generative-email.md"><strong>メールの生成</strong></a>
</div>
<p>
</td>
<td>
<a href="generative-sms.md">
<img alt="SMS の生成" src="assets/do-not-localize/image-genai.jpeg">
</a>
<div><a href="generative-sms.md"><strong>SMS の生成</strong>
</div>
<p>
</td>
<td>
<a href="generative-push.md">
<img alt="プッシュの生成" src="assets/do-not-localize/email-genai.jpeg">
</a>
<div>
<a href="generative-push.md"><strong>プッシュ通知の生成</strong></a>
</div>
<p></td>
</tr></table>
