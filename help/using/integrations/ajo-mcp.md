---
solution: Journey Optimizer
product: journey optimizer
title: MCP クライアントの操作
description: MCP サーバーを使用してAdobe Journey OptimizerをMCP クライアントに接続する方法について説明します
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="ベータ版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: 0a2c384faea70dcbc9b99596740e375d85b2bc64
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 1%

---

# MCP クライアントの操作 {#ajo-mcp}

>[!AVAILABILITY]
>
>[!DNL Adobe Journey Optimizer] MCP サーバーは現在、**Claude Web**&#x200B;および&#x200B;**Claude Desktop**&#x200B;でのみ利用できます。 MCP互換アプリケーションのサポートは、今後のリリースで追加される予定です。

[!DNL Adobe Journey Optimizer]のMCP統合により、API呼び出しを記述したり、製品画面を移動したりすることなく、平易な言語のプロンプトを使用してキャンペーン、ジャーニー、オファーをクエリできます。 このページでは、統合がどのように機能するのか、何ができるのか、どのように始めればよいのかについて説明します。

## モデルコンテキストプロトコルとは何ですか？ {#mcp-overview}

マーケティングチームやカスタマーエクスペリエンスチームは、次第にチャットベースのアプリケーションや開発者ツール（Anthropic Claude、OpenAI ChatGPT、Cursor、Microsoft Copilot Studioなど）に依存するようになり、日常業務の合理化を進めています。 これらのアプリケーションは、**Model Context Protocol （MCP）**&#x200B;をサポートしています。これは、アプリケーションがバックエンドツールを大規模言語モデル（LLM）に統一された方法で公開できるようにするオープンスタンダードです。

[!DNL Adobe Journey Optimizer]は、キャンペーン、ジャーニー、ロイヤルティ、サンドボックスの操作をMCP互換アプリケーション内に直接表示するMCP サーバーを提供するようになりました。 [!DNL Adobe Journey Optimizer] MCP統合により、異なるペルソナは、[!DNL Adobe Journey Optimizer] REST APIに対してクエリを作成したり、複数のUI画面を操作したりすることなく、同じオーケストレーションデータを中心に共同作業を行うことができます。 顧客は自分の意図を対話的に説明でき、LLMが適切なMCP ツールを呼び出せます。

## 主な機能 {#mcp-capabilities}

[!DNL Adobe Journey Optimizer] MCP サーバーでは、AI アシスタントから直接、ジャーニー、キャンペーン、オファーを検査、要約、トラブルシューティングできます。 すべての操作は&#x200B;**読み取り専用**&#x200B;です。MCP サーバーサーフェスは、APIを平易な言語の回答として取得するため、次のことが可能です。

* **ジャーニーロジックを理解** – あらゆるジャーニーの分岐、条件、アクションについて、人間が理解できる要約を取得します。
* **キャンペーンの準備状況を確認** — キャンペーンの公開を妨げるブロッカーを特定します。
* **カバーされていない部分を特定** — ライブジャーニーとキャンペーン全体でどのチャネルがカバーされているか、およびギャップが存在する部分を確認します。
* **オーケストレーションポートフォリオを監査** — JSONを解析したり、製品画面を移動したりすることなく、キャンペーンとジャーニーの完全なステータスを確認できます。

## ユースケース {#mcp-use-cases}

次の例は、自然言語を使用して[!DNL Adobe Journey Optimizer] MCP サーバーを操作する方法を示しています。

| 目標 | プロンプト例 |
|---|---|
| **キャンペーンの詳細を要約** | 「キャンペーン cmp456を取得し、オーディエンス、スケジュール、ステータス、パッケージを要約します。」 |
| **在庫とステータスの監査** | 「何を持っていて、どんな状態にあるのか？ キャンペーンのライブ数とドラフト数と完了/停止/アーカイブ数を表示します。」 |
| **公開の準備状況を確認** | 「キャンペーン cmp456が公開する準備ができていないのはなぜですか？ ブロッカーを見せてくれ。」 |
| **オブジェクトを比較** | 「キャンペーン abc123とxyz789の比較 – ステータスとスケジュールの変更は？」 |
| **ポートフォリオを監査** | 「すべてのライブジャーニーとキャンペーンで、どのチャネルがカバーされ、ギャップはどこにありますか？」 |
| **チャネルのカバレッジとミックス** | 「ジャーニー、キャンペーン、オファーの配置をまたいで、チャネルのフットプリントを表示する（メールのみ、マルチチャネル、プッシュ/SMS/アプリ内での使用状況、ジャーニーチャネル間のミスマッチなど）」。 |

## 前提条件 {#mcp-prerequisites}

[!DNL Adobe Journey Optimizer] MCP サーバーをMCP クライアントに接続する前に、次の点を確認してください。

* アクティブな[!DNL Adobe Journey Optimizer] ライセンスがあります。
* サポートされているMCP互換アプリケーション（現在Claude WebまたはClaude Desktop）にアクセスできます。
* キャンペーン、ジャーニー、オファーを表示するために必要な権限が[!DNL Adobe Journey Optimizer]にあります。

## [!DNL Adobe Journey Optimizer] MCP サーバーを接続します {#mcp-connect}

>[!NOTE]
>
>この統合はBetaにあります。 詳細な設定手順は、一般公開に達したときに公開されます。 Adobeの担当者に連絡して、早期アクセスをリクエストし、設定手順を受け取る。

Betaフェーズでは、Adobeの担当者が次の内容を提供します。

* 組織に固有のMCP サーバーエンドポイント URL。
* AI アシスタントを[!DNL Adobe Journey Optimizer]に接続するための認証情報。
* Claude DesktopまたはClaude WebでのMCP サーバーの設定に関するガイダンス。

<!--
Step-by-step connection instructions to be added here, including:
- How to obtain MCP server credentials from [!DNL Adobe Journey Optimizer]
- How to configure the MCP server in Claude Desktop / Claude Web
- How to authenticate
-->

## よくある質問 {#mcp-faq}

+++どのMCP クライアントがサポートされていますか？

[!DNL Adobe Journey Optimizer] MCP サーバーは現在、**Claude Web**&#x200B;および&#x200B;**Claude Desktop**&#x200B;で利用できます。 今後のリリースで、MCP互換アプリケーションのサポートが追加される可能性があります。
+++

+++MCP経由でアクセスできる[!DNL Adobe Journey Optimizer] オブジェクトは何ですか？

キャンペーン、ジャーニー、オファー、ロイヤルティデータ、サンドボックス情報にアクセスできます。 操作は読み取り専用（取得API）です。書き込み操作は現在のリリースではサポートされていません。
+++

+++[!DNL Adobe Journey Optimizer] MCP サーバーを使用するには、開発者アクセス権が必要ですか？

いいえ。 MCP サーバーは、マーケティングとテクノロジーの両方のペルソナ向けに設計されています。 マーケターは、サポートされているMCP クライアントで自然言語プロンプトを使用してMCPと対話できます。また、開発者は、MCPをサポートする開発者ツールでもMCPを使用できます。
+++

+++データはMCP クライアントプロバイダーに送信されますか？

プロンプトを送信すると、MCP クライアントは、関連するコンテキスト（MCP サーバーから返された[!DNL Adobe Journey Optimizer] データを含む）をモデルに送信して処理する場合があります。 本番データに接続する前に、MCP クライアントプロバイダーのプライバシーおよびデータ処理ポリシーを確認してください。
+++

+++[!DNL Adobe Journey Optimizer]でどのような権限が必要ですか？

クエリするオブジェクト（キャンペーン、ジャーニー、オファー）に対して、最低&#x200B;**表示**&#x200B;権限が必要です。 MCP サーバーは読み取り操作のみを実行するため、書き込み権限は必要ありません。 現在のアクセス レベルが不明な場合は、[!DNL Adobe Journey Optimizer]管理者にお問い合わせください。
+++

+++サンドボックス環境でMCP サーバーを使用できますか？

はい。 MCP サーバーは、[!DNL Adobe Journey Optimizer] サンドボックス設定を尊重します。 サンドボックス固有のデータをクエリするには、プロンプトでサンドボックスを指定するか、特定のサンドボックスにスコープ付きの資格情報で接続します。
+++
