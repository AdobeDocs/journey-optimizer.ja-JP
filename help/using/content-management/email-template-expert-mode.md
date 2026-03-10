---
solution: Journey Optimizer
product: journey optimizer
title: 高度なHTML エディターでのメールテンプレートの編集
description: エキスパートモードを使用すると、WYSIWYG エディターでメールコンテンツのHTML ソースを表示および編集することができ、機能フラグ制御、ガードレール、保存検証機能が備わります。
feature: Templates
topic: Content Management
role: User
level: Experienced
exl-id: 0c586565-0c65-435f-986d-cd08b59de159
source-git-commit: 145944952ad9aca752085588526f71e8034b8611
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 7%

---

# 高度なHTML エディターでのメールテンプレートの編集 {#email-template-expert-mode}

>[!AVAILABILITY]
>
>この機能は、限定提供で使用できます。アクセス権を取得するには、アドビ担当者にお問い合わせください。

**高度なHTML エディター** は、メールコンテンツテンプレートの生のソースコードを、[!DNL Journey Optimizer] Email Designer インターフェイスから直接表示して編集できるエキスパートモードです。

この機能を使用すると、条件などの高度な式をソース内に直接挿入できます。 ビジュアル（デスクトップ）ビューに戻すと、コンテンツが再レンダリングされるので、外観を確認して、どちらのビューでも編集を続行できます。

>[!NOTE]
>
>この機能は、コンテンツテンプレートおよびメールチャネルでのみ使用できます。

## ガードレール {#guardrails}

高度なHTML エディターを使用する場合、次のガードレールによってコンテンツの互換性が保護され、期待値が設定されます。

* コードの高度なHTML エディター **検証されません**。 構文エラーや壊れたレイアウトはチェックされません。 保存する前に、コンテンツを慎重にレビューします。

* 今後、システムを更新すると、既定のマークアップに対して行った変更が上書きされる場合があります。 **変更内容が保持されない場合があります**。

* [!DNL Adobe] サポートチーム **カスタムコードと手動の変更が原因で発生した問題のトラブルシューティングや解決ができない** 場合。 元に戻す必要がある場合に備えて、コンテンツのバックアップを保持します。

* HTMLの詳細表示でコンテンツをシミュレートすることはできません。 デスクトップビューに切り替えて、コンテンツをプレビューします。

* コンテンツの互換性を確保するには、HTMLの詳細表示で **保存することはできません**。 変更を保存する準備ができたら、デスクトップビューに戻ります。

>[!WARNING]
>
>コンテンツテンプレートの高度なHTML エディターは、メールDesignerの **[!UICONTROL 独自にコーディング]** モードとは異なります。 [!UICONTROL &#x200B; 独自にコーディング &#x200B;] モードでは、ビジュアルエディターに戻すことはできません。そのパスを選択すると、コードのみの編集になります。 これに対して、高度なHTML エディターでは、HTML表示とデスクトップ（ビジュアル）表示をいつでも切り替えることができます。 [詳しくは、コードエディターを参照してください](../email/code-content.md)

## HTMLの詳細表示に切り替える {#switch-to-html-view}

高度なHTML エディターを開き、テンプレートソースを編集するには、次の手順に従います。

1. [&#x200B; メールテンプレート &#x200B;](../content-management/create-content-templates.md) を開くか作成し、[&#x200B; メールDesigner](../email/get-started-email-design.md) を開いてコンテンツを編集します。

1. 画面の右上隅にある「**[!UICONTROL HTML]**」ボタンをクリックします。

   ![&#x200B; メールDesignerツールバーの「HTML」ボタンの場所 &#x200B;](assets/email-template-expert-mode-button.png)

1. 高度なHTML エディターを初めて開くと、警告メッセージが表示されます。 慎重に確認し、「**[!UICONTROL OK]**」をクリックして続行します。 [詳細情報](#guardrails)

   ![&#x200B; 高度なHTML エディターを初めて開く際の警告ダイアログ &#x200B;](assets/email-template-expert-mode-warning.png){zoomable="yes"}

   >[!NOTE]
   >
   >この警告は、HTMLの詳細編集を初めて開いたときに表示され、毎月リセットされます。

1. 高度なHTML エディターが表示されます。

   ![&#x200B; メールテンプレートのソースコードを表示する高度なHTML エディターインターフェイス &#x200B;](assets/email-template-expert-mode.png)

1. メールコンテンツに必要な変更を追加します。

   >[!WARNING]
   >
   >構文の検証プロセスはなく、[!DNL Adobe] によるサポートも提供されていないので、正しいHTMLと CSS コードを入力してください。 [詳細情報](#guardrails)

1. 互換性の理由から、高度なHTML ビューではコンテンツのシミュレーションと保存を使用できません。 デスクトップビューに戻ってコンテンツをプレビューし、変更を保存します。

   ![&#x200B; デスクトップビューに戻って変更を保存します &#x200B;](assets/email-template-expert-mode-save.png){zoomable="yes"}

   >[!NOTE]
   >
   >編集内容は、ビューを切り替えても保持されます。

<!--
    ![](assets/email-template-expert-mode-simulate.png){zoomable="yes"}-->

## 関連トピック

* [独自のメールコンテンツをコーディングする](../email/code-content.md)
* [コンテンツテンプレートの作成](create-content-templates.md)
* [E メールデザイナーの基本を学ぶ](../email/get-started-email-design.md)

