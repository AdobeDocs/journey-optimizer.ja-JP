---
solution: Journey Optimizer
product: journey optimizer
title: 高度なHTMLエディターでメールテンプレートを編集できます
description: エキスパートモードを使用すると、WYSIWYGエディターでHTMLのメールコンテンツのソースを表示および編集し、機能フラグの制御、ガードレール、検証の保存を行うことができます。
feature: Templates
topic: Content Management
role: User
level: Experienced
exl-id: 0c586565-0c65-435f-986d-cd08b59de159
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 7%

---

# 高度なHTMLエディターでメールテンプレートを編集できます {#email-template-expert-mode}

>[!AVAILABILITY]
>
>この機能は、限定提供で使用できます。アクセス権を取得するには、アドビ担当者にお問い合わせください。

**高度なHTML エディター**&#x200B;は、[!DNL Journey Optimizer]電子メール Designer インターフェイスから直接、電子メールコンテンツテンプレートの生のソースコードを表示および編集できるエキスパートモードです。

この機能を使用すると、条件などの高度な式をソースに直接挿入できます。 ビジュアル（デスクトップ）ビューに切り替えると、コンテンツが再レンダリングされるので、どのビューでもコンテンツの外観を確認し、編集を続行できます。

>[!NOTE]
>
>この機能は、コンテンツテンプレートとメールチャネルでのみ使用できます。

## ガードレール {#guardrails}

高度なHTML エディターを使用する場合、次のガードレールはコンテンツの互換性を保護し、期待値を設定します。

* 高度なHTML エディター&#x200B;**でコードが検証されません**。 構文エラーや壊れたレイアウトはチェックしません。 保存する前に、コンテンツを注意深く確認してください。

* 今後のシステムの更新によって、デフォルトのマークアップに加えた変更が上書きされる可能性があります。 **変更が保持されない可能性があります**。

* [!DNL Adobe] サポートチーム **は、カスタムコードと手動での変更による問題**&#x200B;のトラブルシューティングや解決を行うことができません。 元に戻す必要がある場合に備えて、コンテンツのバックアップを取っておきます。

* 高度なHTML ビューでコンテンツをシミュレートすることはできません。 デスクトップ表示に切り替えて、コンテンツをプレビューします。

* コンテンツの互換性を確保するために、高度なHTML ビューに&#x200B;**保存できません**。 変更を保存する準備ができたら、デスクトップ表示に切り替えます。

>[!WARNING]
>
>コンテンツテンプレートの高度なHTML エディターは、電子メールDesignerの&#x200B;**[!UICONTROL 独自の]** モードをコード化するのとは異なります。 [!UICONTROL 独自の] モードでコードを記述すると、ビジュアルエディターに戻すことはできません。パスを選択すると、コードのみの編集が維持されます。 対照的に、高度なHTML エディターでは、いつでもHTML ビューとデスクトップ（ビジュアル）ビューを切り替えることができます。 [詳しくは、コードエディターを参照してください](../email/code-content.md)

## 高度なHTML ビューに切り替える {#switch-to-html-view}

高度なHTML エディターを開き、テンプレートソースを編集するには、次の手順に従います。

1. [電子メールテンプレート &#x200B;](../content-management/create-content-templates.md)を開くか作成し、[電子メールDesigner](../email/get-started-email-design.md)を開いて内容を編集します。

1. 画面の右上隅にある「**[!UICONTROL HTML]**」ボタンをクリックします。

   ![電子メールのDesigner ツールバーのHTML ボタンの場所](assets/email-template-expert-mode-button.png)

1. HTMLの詳細エディターを初めて開くと、警告メッセージが表示されます。 それを注意深く確認し、**[!UICONTROL OK]**&#x200B;をクリックして続行します。 [詳細情報](#guardrails)

   ![高度なHTML エディターを初めて開く際の警告ダイアログ &#x200B;](assets/email-template-expert-mode-warning.png){zoomable="yes"}

   >[!NOTE]
   >
   >この警告は、HTMLの詳細エディターを初めて開いたときにのみ表示され、毎月更新されます。

1. 高度なHTML エディターが表示されます。

   ![電子メールテンプレートのソースコードを表示する高度なHTML エディターインターフェイス &#x200B;](assets/email-template-expert-mode.png)

1. メールコンテンツに変更を加えます。

   >[!WARNING]
   >
   >構文の検証プロセスはなく、[!DNL Adobe]によるサポートも提供されていないため、正しいHTMLとCSS コードを入力してください。 [詳細情報](#guardrails)

1. コンテンツのシミュレーションと保存は、互換性の理由により、高度なHTML ビューでは使用できません。 デスクトップビューに戻して、コンテンツをプレビューし、変更を保存します。

   ![変更を保存するには、デスクトップ表示に切り替えます](assets/email-template-expert-mode-save.png){zoomable="yes"}

   >[!NOTE]
   >
   >ビューを切り替えると、編集内容は保持されます。

<!--
    ![](assets/email-template-expert-mode-simulate.png){zoomable="yes"}
-->

## 関連トピック

* [独自のメールコンテンツをコーディングする](../email/code-content.md)
* [コンテンツテンプレートの作成](create-content-templates.md)
* [E メールデザイナーの基本を学ぶ](../email/get-started-email-design.md)

