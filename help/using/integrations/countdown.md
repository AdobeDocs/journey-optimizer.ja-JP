---
solution: Journey Optimizer
product: journey optimizer
title: Dynamic Media
description: Journey Optimizer での Dynamic Media の使用
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 1b0b2b5aa8c5b4ea0a101583ee1132574996bd98
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 3%

---

# カウントダウンタイマーの挿入 {#countdown}

受信者がメールを開いたときにリアルタイムに更新される Dynamic Media カウントダウンタイマーを使用して、緊急度を高め、コンバージョンを最大化します。 この機能は、フラッシュ販売、期間限定オファー、時間依存のプロモーションに最適です。

例えば、小売ブランドのマーケターとして、48 時間のフラッシュセールを実行しているとします。 プロモーションメールでカウントダウンタイマーを使用する方法：

* 直ちに開いた受信者には、「残り 47 時間」と表示されます
* 24 時間後に開封した受信者には、「残り 23 時間」と表示されます
* セール終了後に開いた受信者には、「セールが終了しました」と表示されます

Adobe Experience Manager で Dynamic Media を作成する方法について詳しくは、[&#x200B; このドキュメント &#x200B;](assets/do-not-localize/Dynamic%20Media%20Templates.pdf) を参照してください。


1. ま **[!DNL Adobe Experience Manager]**、Dynamic Media テンプレートを作成し、カウントダウンタイマーコンポーネントを追加します。

   ![](assets/timer-1.png)

1. **[!DNL Journey Optimizer]** で、新しいキャンペーンを作成するか、既存のキャンペーンを開いて、メールDesignerにアクセスします。

1. **[!UICONTROL HTML コンポーネント]** をメールコンテンツにドラッグ&amp;ドロップします。

1. **[!UICONTROL ソースコードを表示]** を選択して、HTMLを直接編集します。

   ![](assets/timer-2.png)

1. **[!UICONTROL Dynamic Media を編集]** メニューから **[!UICONTROL HTMLに移動し]**&#x200B;**[!UICONTROL アセットセレクターを開く]** をクリックして、公開済みのAssets テンプレートを参照して選択します。

   ![](assets/timer-3.png)

1. **[!UICONTROL カスタム属性]** メニューで、テンプレートに必要なカスタマイズ可能な URL パラメーターを設定します。

   終了したら「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/timer-4.png)

1. E メールDesignerでアセットを選択し、**[!UICONTROL スタイル]** メニューにアクセスします。

   以下の設定を指定します。
   * **バナーテキスト**：タイマーで表示されるテキスト
   * **終了時間**：カウントダウンが期限切れになる日時。 時刻は GMT （グリニッジ標準時）のみで入力してください。 システムは他のタイムゾーンを受け入れません。
   * **代替テキスト**：タイマー終了後に表示されるメッセージ

   ![](assets/timer-5.png)

1. **[!UICONTROL プレビュー]** をクリックして、リアルタイムのカウントダウンアップデートでタイマーを表示し、設定を確認します。

受信者がメールを開くと、フラッシュセールの残り時間が正確に表示されます。 メールを後で再度開くと、現在の残り時間に合わせてカウントダウンが自動的に更新されます。 終了日が過ぎると、デフォルトのメッセージが自動的に表示されます。

