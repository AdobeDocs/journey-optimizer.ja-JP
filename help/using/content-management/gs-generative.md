---
solution: Journey Optimizer
product: journey optimizer
title: AI アシスタントの基本を学ぶ
description: Journey Optimizer の AI アシスタントへのアクセスおよび操作方法を説明します
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="ベータ版" type="Informative"
hide: true
hidefromtoc: true
exl-id: 6e291ce3-f324-4e5d-975b-5229dea4d581
source-git-commit: 644e0959ee0d0ec8ee0c4ec54c3bcd1cc3c4dda9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 85%

---

# AI アシスタントの基本を学ぶ {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="AI アシスタント"
>abstract="配信を作成しパーソナライズしたら、AI アシスタントを使用してコンテンツを強化できます。この機能を使用すると、生成する内容を記述してコンテンツを微調整できるので、パーソナライゼーションとコンテンツ改善のプロセスが簡素化されます。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="AI アシスタントでコンテキストを定義"
>abstract="選択したコンテンツをコンテンツ生成用の入力として使用するには、 **元のコンテンツを使用** 切り替えます。 また、ブランドアセットをアップロードして、ソースとして使用することもできます。選択したコンテンツを使用しない場合は、ブランドアセットのアップロードと選択が必須です。"


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe 生成 AI の用語"
>abstract="この機能へアクセスするには、Adobe Experience Cloud 生成 AI ユーザーガイドラインへの同意が必要です。この機能に対して提供するプロンプト、コンテキスト、補足情報、その他の入力は、特定のコンテキストに関連付ける必要があります。これには、ブランディング資料、web サイトのコンテンツ、データ、データのスキーマ、テンプレート、その他の信頼できるドキュメントを含めることができますが、個人情報は含めないでください（個人情報には、特定の個人に関連付けることができるあらゆる情報が含まれます）。この機能からの出力が正確であるかどうかを確認し、ユースケースに適切であることを確認する必要があります。"
>additional-url="https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html" text="Adobe 生成 AI ユーザーガイドライン"

>[!BEGINSHADEBOX]

**目次**

* AI アシスタントの基本を学ぶ
* [AI アシスタントを使用したメールの生成](generative-email.md)
* [AI アシスタントを使用した SMS の生成](generative-sms.md)
* [AI アシスタントによるプッシュ生成](generative-push.md)
* [AI アシスタントを使用したコンテンツ実験](generative-experimentation.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Adobe Journey Optimizerの AI アシスタントは現在、一部のユーザーのみがベータ版として利用できます。

Adobe Journey Optimizer の AI アシスタントは、テキストと画像に対するプロアクティブなコンテンツのバリエーションの提案を提供します。これは、メール、プッシュおよび SMS チャネルで使用できます。 この新しい機能は、プロンプトベースのテキストおよび画像の生成を提供します。画像の生成は、Adobe Firefly で管理されます。

Journey Optimizer の AI アシスタントを使用して、様々なメインタイトルや画像を試すことで、メッセージの影響を最適化します。複数のバリアントを生成し、それらを比較する実験を作成します。Journey Optimizer のコンテンツ実験を使用すると、ターゲットオーディエンスに最適なパフォーマンスを発揮するのはどれかを測定するために、複数のメッセージ処理を定義できます。配信コンテンツまたは件名を変更できます。メッセージオーディエンスが各処理にランダムに割り当てられて、指定の指標に関して最も効果が高い処理が判断されます。コンテンツ実験について詳しくは、[この節](../campaigns/content-experiment.md)を参照してください。

## ガードレールと制限 {#generative-guardrails}

Journey Optimizerの AI アシスタントをメールの作成に使用する場合の一般的なガイドラインを以下に示します。

* 生成されるコンテンツの品質は、定義したマーケティング目的やプロンプトに大きく左右されます。生成 AI モデルで正確に解釈できるように、適切に定義されたプロンプトを使用します。 
* ブランドアセットをアップロードして、正確なオンブランドコンテンツを確保します。それ以外の場合は、公開されている情報に基づいたコンテンツになります。アップロードされるコンテンツは、PDF、JPEG、PNG または ZIP ファイル（サポートされているファイル形式のもの）の形式です。
* アップロードされたブランドアセットの最大サイズは 50MB です。これより大きなファイルや多数の画像の場合でも動作しますが、処理時間が長くなります。
* Adobe Campaign で作成したメールテンプレートを使用するか、できれば[組み込みのメールテンプレート](../email/use-email-templates.md)、ブランド固有のテンプレートまたはカスタムテンプレートを使用して、メールコンテンツを作成します。最大 8～10 個の画像を含むメールテンプレートをお勧めします。
* バリアントを選択する際は、サムアップ、サムダウンまたはフラグのアイコンを使用して、問題のある出力を報告してください。
* AI アシスタントの使用は、Adobe Experience Cloud 生成 AI ユーザーガイドラインの対象となります。[詳細情報](https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html)

Journey Optimizerの AI アシスタントには次の制限が適用されます。

* サポートされている言語は英語のみです。
* メール、プッシュ、SMS の各チャネルにのみ使用できます。
* 生成 AI のコンテンツは必ずしも正確でない場合があります。エンジニアがモデルを改善できるように、フィードバックを共有してください。
* 複数のブランドアセットをアップロードできますが、特定の生成に利用できるのは 1 つだけです。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="generative-email.md">
<img alt="メール生成" src="assets/do-not-localize/text-genai.jpeg">
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
<div><a href="generative-sms.md"><strong>SMS 生成</strong>
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
