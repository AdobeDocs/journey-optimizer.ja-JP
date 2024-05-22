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
source-git-commit: 644e0959ee0d0ec8ee0c4ec54c3bcd1cc3c4dda9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 38%

---

# AI アシスタントの基本を学ぶ {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="AI アシスタント"
>abstract="配信を作成してパーソナライズしたら、AI アシスタントを使用してコンテンツを強化できます。 この機能を使用すると、生成対象を記述することでコンテンツを微調整できるので、パーソナライゼーションとコンテンツ改善のプロセスが簡略化されます。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="AI アシスタントでコンテキストを定義"
>abstract="選択したコンテンツをコンテンツ生成用の入力として使用するには、 **元のコンテンツを使用** 切り替えます。 また、ブランドアセットをアップロードして、ソースとして使用することもできます。 選択したコンテンツを使用しない場合、ブランドアセットのアップロードおよび選択は必須です。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe生成 AI の用語"
>abstract="この機能にアクセスするには、Adobe Experience Cloud ジェネレーティブ AI ユーザーガイドラインに同意する必要があります。 この機能に提供するプロンプト、コンテキスト、補足情報、またはその他の入力は、特定のコンテキストに結び付ける必要があります。このコンテキストには、ブランド資料、web サイトコンテンツ、データ、そのようなデータ、テンプレート、その他の信頼できるドキュメントのスキーマを含めることができ、個人情報を含めることはできません（個人情報には、特定の個人にリンクできるものを含みます）。 この機能からの出力の正確性を確認し、ユースケースに適していることを確認する必要があります"
>additional-url="https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html" text="Adobe生成 AI のユーザーガイドライン"

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

Adobe Journey Optimizer の AI アシスタントは、テキストや画像に対してコンテンツのバリエーションをプロアクティブに提案する機能を提供します。メール、プッシュ、SMS の各チャネルで使用できます。この新しい機能は、プロンプトベースのテキストおよび画像の生成を提供します。画像の生成は、Adobe Firefly で管理されます。

Journey Optimizer の AI アシスタントを使用して、様々なメインタイトルや画像を試すことで、メッセージの影響を最適化します。複数のバリアントを生成し、それらを比較する実験を作成します。Journey Optimizer のコンテンツ実験を使用すると、ターゲットオーディエンスに最適なパフォーマンスを発揮するのはどれかを測定するために、複数のメッセージ処理を定義できます。配信コンテンツまたは件名を変更できます。メッセージオーディエンスが各処理にランダムに割り当てられて、指定の指標に関して最も効果が高い処理が判断されます。コンテンツ実験について詳しくは、[この節](../campaigns/content-experiment.md)を参照してください。

## ガードレールと制限 {#generative-guardrails}

メールの生成に Journey Optimizer の AI アシスタントを使用する際の一般的なガイドラインは次のとおりです。

* 生成されるコンテンツの品質は、定義したマーケティング目的/プロンプトの影響を強く受けます。 GenAI モデルに明確に定義されたプロンプトを使用して、正確に解釈します。 
* 正確な情報が得られるように、ブランドコンテンツでブランドアセットをアップロードします。 それ以外の場合、コンテンツは、公開されている情報に基づきます。 アップロードされるコンテンツの形式は、PDF、JPEG、PNG、ZIP ファイル（サポートされているファイル形式）のいずれかです。
* アップロードされるブランドアセットの最大サイズは 50 MB です。 サイズの大きいファイルや多数の画像を処理できますが、処理時間は長くなります。
* Adobe Campaignで作成したメールテンプレートを使用する（できれば） [ビルトインのメールテンプレート](../email/use-email-templates.md)：メールコンテンツを作成するためのブランド固有のテンプレートまたはカスタムテンプレート。 最大 8～10 個の画像を含むメールテンプレートを使用することをお勧めします。
* バリアントを選択する際は、サムアップ、サムダウンまたはフラグアイコンを使用して、問題のある出力を報告してください。
* AI アシスタントの使用は、Adobe Experience Cloud ジェネレーティブ AI ユーザーガイドラインの対象となります。 [詳細情報](https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html)

Journey Optimizer の AI アシスタントには、次の制限が適用されます。

* サポートされている言語は英語のみです。
* メール、プッシュ、SMS チャネルでのみ使用できます。
* GenAI のコンテンツは必ずしも正確でない場合があります。当社のエンジニアがモデルを改良できるように、フィードバックをお寄せください。
* 複数のブランドアセットをアップロードできますが、特定の世代に利用できるのは 1 つのみです。

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
