---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerの AI アシスタントの基本を学ぶ – コンテンツアクセラレーター
description: Journey Optimizerの AI アシスタントにアクセスして操作する方法 – コンテンツアクセラレーター
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
exl-id: 6e291ce3-f324-4e5d-975b-5229dea4d581
source-git-commit: 616a9c30da4558d1e8b71733732dd4fd1f531ef8
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 43%

---

# Journey Optimizerの AI アシスタントの基本を学ぶ – コンテンツアクセラレーター {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="コンテンツアクセラレーションのためのJourney Optimizerの AI アシスタント"
>abstract="配信を作成してパーソナライズしたら、Journey Optimizerのコンテンツアクセラレーション用 AI アシスタントを使用してコンテンツを強化できます。 この機能により、何を生成したいかを記述して、コンテンツを微調整できるので、パーソナライゼーションとコンテンツの改善のプロセスが簡素化されます。"

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="ブランドアセットのアップロード"
>abstract="「ブランドアセットをアップロード」メニューを使用すると、コンテンツを含む任意のブランドアセットを追加できます。これにより、コンテンツ高速化のためにJourney Optimizerの AI アシスタントのコンテキストを追加で提供したり、以前にアップロードしたアセットを選択したりできます。 このオプションにより、AI アシスタントは機能と関連性を高めるために必要なすべての資料にアクセスできます。"

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe 生成 AI 用語"
>abstract="この機能にアクセスするには、Adobe Experience Cloud 生成 AI ユーザーガイドラインに同意する必要があります。この機能からの出力の正確性を確認し、ユースケースに適していることを確認してください。"
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe 生成 AI ユーザーガイドライン"

>[!INFO]
>
>その機能を直接探索し、その機能を完全に理解できるように設計された [ インタラクティブなデモ ](https://experienceleague.adobe.com/en/apps/journey-optimizer/ai-assistant-content-accelerator){target="_blank"} を使用して、実践的な体験に浸ってください。


Microsoft Azure OpenAI とAdobe Fireflyを活用したAdobe Journey Optimizerのコンテンツアクセラレーション用 AI アシスタントは、テキストや画像に対するプロアクティブなコンテンツバリエーションの提案を行います。 メール、プッシュ、SMS の各チャネルで使用できます。この新しい機能は、プロンプトベースのテキストおよび画像の生成を提供します。画像の生成は、Adobe Firefly で管理されます。

Adobe Journey Optimizerのコンテンツアクセラレーション用 AI アシスタントを使用して、様々なメインタイトルや画像で実験することで、メッセージの影響を最適化します。 複数のバリアントを生成し、それらを比較する実験を作成します。Journey Optimizer のコンテンツ実験を使用すると、ターゲットオーディエンスに最適なパフォーマンスを発揮するのはどれかを測定するために、複数のメッセージ処理を定義できます。配信コンテンツまたは件名を変更できます。メッセージオーディエンスが各処理にランダムに割り当てられて、指定の指標に関して最も効果が高い処理が判断されます。コンテンツ実験について詳しくは、[この節](../content-management/content-experiment.md)を参照してください。

>[!IMPORTANT]
>
>* この機能の使用を開始する前に、関連する[ガードレールと制限](#generative-guardrails)のトピックに目を通してください。
>
>
>* コンテンツアクセラレーションのためにAdobe Journey Optimizerで AI アシスタントを使用するには、[ ユーザー使用許諾契約 ](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} に同意する必要があります。 詳しくは、アドビ担当者にお問い合わせください。

## AI Assistant コンテンツ アクセラレータにアクセスする {#generative-access}

Adobe Journey Optimizerのコンテンツアクセラレーション機能で AI アシスタントにアクセスするには、**コンテンツを生成** 権限を付与されている必要があります。 [詳細情報](../administration/permissions.md)

+++  コンテンツ生成関連の権限を割り当てる方法を学ぶ

1. **権限** 製品で、「**役割**」タブに移動し、目的の **役割** を選択します。

1. **編集** をクリックして、権限を変更します。

1. **AI アシスタント** リソースを追加し、ドロップダウンメニューから **コンテンツを生成** を選択します。

   ![](assets/gen-ai-role.png){zoomable="yes"}

1. 「**保存**」をクリックして、変更を適用します。

   この役割に既に割り当てられているユーザーの権限は自動的に更新されます。

1. この役割を新しいユーザーに割り当てるには、**役割** ダッシュボード内の **ユーザー** タブに移動し、**ユーザーを追加** をクリックします。

1. ユーザーの名前やメールアドレスを入力するか、リストから選択して、「**保存**」をクリックします。

1. ユーザーをまだ作成していない場合は、[ このドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/users) を参照してください。

インスタンスへのアクセス手順を記載したメールがユーザーに届きます。

+++

## ガードレールと制限 {#generative-guardrails}

Adobe Journey Optimizerの AI アシスタントを使用したメールのコンテンツアクセラレーションに関する一般的なガイドラインを以下に示します。

* 生成されるコンテンツの品質は、定義したマーケティング目標／プロンプトに強く影響されます。生成 AI モデルが正確に解釈できるように、明確に定義されたプロンプトを使用します。 
* 正確な情報が得られるように、ブランドコンテンツでブランドアセットをアップロードします。それ以外の場合、コンテンツは、公開されている情報に基づきます。アップロードされるコンテンツの形式は、PDF、JPEG、PNG、ZIP ファイル（サポートされているファイル形式を含む）のいずれかです。
* アップロードされるブランドアセットの最大サイズは 50 MB です。サイズの大きいファイルや多数の画像を処理できますが、処理時間は長くなります。
* ブランド固有またはカスタムテンプレートを使用して、コンテンツ高速化のためにAdobe Journey Optimizerの AI アシスタントを使用してメールコンテンツを作成します。 最大 8～10 個の画像を含むメールテンプレートを使用することをお勧めします。
* バリアントを選択する際は、サムアップ、サムダウンまたはフラグのアイコンを使用して、問題のある出力を報告する必要があります。
* AI アシスタントの使用には、Adobe Experience Cloud 生成 AI ユーザーガイドラインが適用されます。[詳細情報](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html)
* メディア制作における生成 AI ツールの使用に関する透明性を高めるためのAdobeの取り組みの一環として、Adobeは、Firefly生成アセットを含むコンテンツまたはプロジェクトがダウンロードまたは書き出されたときにContent credentialsを適用します。 [詳細情報](https://helpx.adobe.com/firefly/using/content-credentials.html)

コンテンツアクセラレーション向けAdobe Journey Optimizerの AI アシスタントには次の制限が適用されます。

* サポートされている言語は英語のみです。 英語以外の入力では、一貫性のない結果や誤った結果が生じる場合があります。 英語以外の回答に起因する問題は、現時点では解決または改善されません。
* メール、プッシュ、web および SMS チャネルでのみ使用できます。
* 生成 AI コンテンツは必ずしも正確ではない可能性があります。エンジニアがモデルを改良できるよう、フィードバックをお寄せください。
* 複数のブランドアセットをアップロードできますが、特定の世代に活用できるのは 1 つだけです。


## AI アシスタントのコンテンツ生成機能 {#generative-features}


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
<td>
<a href="generative-web.md">
<img alt="Web 生成" src="assets/do-not-localize/web-genai.jpeg">
</a>
<div><a href="generative-web.md"><strong>Web ページの生成 </strong>
</div>
<p>
</td>
</tr></table>
