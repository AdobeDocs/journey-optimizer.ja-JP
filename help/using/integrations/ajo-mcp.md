---
solution: Journey Optimizer
product: journey optimizer
title: MCP経由でAI アシスタントと連携する
description: Model Context Protocol （MCP）サーバーを使用してAdobe Journey OptimizerをAI アシスタントに接続する方法について説明します
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="限定提供" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 019a4d601ecd5f6d6127ab8616de0b3ee0f77a9c
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 1%

---

# MCP経由でAI アシスタントと連携する {#ajo-mcp}

>[!AVAILABILITY]
>
>[!DNL Adobe Journey Optimizer] MCP サーバーは現在、**Claude Web**&#x200B;および&#x200B;**Claude Desktop**&#x200B;でのみ利用できます。

## モデル コンテキスト プロトコルとは何ですか？ {#mcp-overview}

マーケティングチームやカスタマーエクスペリエンスチームは、次第にチャットベースのアプリケーションや開発者ツール（Anthropic Claude、OpenAI ChatGPT、Cursor、Microsoft Copilot Studioなど）に依存するようになり、日常業務の合理化を進めています。 これらのアプリケーションは、**Model Context Protocol （MCP）**&#x200B;をサポートしています。これは、アプリケーションがバックエンドツールを大規模言語モデル（LLM）に統一された方法で公開できるようにするオープンスタンダードです。

[!DNL Adobe Journey Optimizer]は、キャンペーン、ジャーニー、ロイヤルティ、サンドボックスの操作をMCP互換アプリケーション内に直接表示するMCP サーバーを提供するようになりました。 [!DNL Adobe Journey Optimizer] MCP統合により、異なるペルソナは、[!DNL Adobe Journey Optimizer] REST APIに対してクエリを作成したり、複数のUI画面を操作したりすることなく、同じオーケストレーションデータを中心に共同作業を行うことができます。 顧客は自分の意図を対話的に説明でき、LLMが適切なMCP ツールを呼び出せます。

## 主な機能 {#mcp-capabilities}

[!DNL Adobe Journey Optimizer] MCP サーバーを使用すると、[!DNL Adobe Journey Optimizer]件のジャーニー、キャンペーン、オファーをAI アシスタントから直接検査、要約、トラブルシューティングできます。 [!DNL Adobe Journey Optimizer]の取得APIは平易な言語の回答に変換されるので、次のことが可能になります。

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

[!DNL Adobe Journey Optimizer] MCP サーバーをAI アシスタントに接続する前に、次の点を確認してください。

* アクティブな[!DNL Adobe Journey Optimizer] ライセンスがあります。
* サポートされているMCP互換アプリケーション（現在Claude WebまたはClaude Desktop）にアクセスできます。
* キャンペーン、ジャーニー、オファーを表示するために必要な権限が[!DNL Adobe Journey Optimizer]にあります。

## [!DNL Adobe Journey Optimizer] MCP サーバーを接続します {#mcp-connect}

>[!NOTE]
>
>統合が一般公開されると、詳細な設定手順が追加されます。 早期アクセスについては、Adobe担当者にお問い合わせください。

<!--
Step-by-step connection instructions to be added here, including:
- How to obtain MCP server credentials from [!DNL Adobe Journey Optimizer]
- How to configure the MCP server in Claude Desktop / Claude Web
- How to authenticate
-->

## よくある質問 {#mcp-faq}

+++どのAI アシスタントがサポートされていますか？

[!DNL Adobe Journey Optimizer] MCP サーバーは現在、**Claude Web**&#x200B;および&#x200B;**Claude Desktop**&#x200B;で利用できます。 今後のリリースで、MCP互換アプリケーションのサポートが追加される可能性があります。
+++

+++MCP経由でアクセスできる[!DNL Adobe Journey Optimizer] オブジェクトは何ですか？

キャンペーン、ジャーニー、オファー、ロイヤルティデータ、サンドボックス情報にアクセスできます。 操作は読み取り専用（取得API）です。書き込み操作は現在のリリースではサポートされていません。
+++

+++[!DNL Adobe Journey Optimizer] MCP サーバーを使用するには、開発者アクセス権が必要ですか？

いいえ。 MCP サーバーは、マーケティングとテクノロジーの両方のペルソナ向けに設計されています。 マーケターは、Claudeの自然言語プロンプトを使用してMCPと対話できます。また、開発者は、MCPをサポートする開発者ツールでもMCPを使用できます。
+++

+++データはAI アシスタントプロバイダーに送信されますか？

プロンプトを送信すると、AI アシスタントは、関連するコンテキスト（MCP サーバーから返された[!DNL Adobe Journey Optimizer] データを含む）をモデルに送信して処理する場合があります。 本番データに接続する前に、AI アシスタントプロバイダーのプライバシーポリシーとデータ処理ポリシーを確認しましょう。
+++
