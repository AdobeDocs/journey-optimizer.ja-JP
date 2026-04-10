---
solution: Journey Optimizer
product: journey optimizer
title: Dynamic Media
description: Journey Optimizer での Dynamic Media の使用
topic: Content Management
role: User
level: Beginner
hide: true
exl-id: 4c1d39c4-3154-4bec-ac3c-c2ead7164d69
source-git-commit: 3b5bb49a1774112192d41a86d53d605618fe32e5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 2%

---

# カウントダウンタイマーを挿入 {#countdown}

受信者が電子メールを開いたときにリアルタイムで更新されるダイナミックメディアのカウントダウンタイマーを活用して、緊急性を高め、コンバージョンを最大化します。 この機能は、フラッシュセール、期間限定オファー、時間制限のあるプロモーションに最適です。

たとえば、小売企業のマーケターとして、48時間のフラッシュセールを実施しているとします。 プロモーションメールにカウントダウンタイマーを使用する：

* すぐに開いた受信者に「残り47時間」と表示される
* 24時間後に開封した受信者に「残り23時間」と表示
* セール終了後に開封した受信者には、「タイムズアップ！」と表示されます。

Adobe Experience ManagerのDynamic Media テンプレートにカウントダウンタイマーを追加する方法について詳しくは、[このドキュメント ](assets/do-not-localize/countdown.pdf)を参照してください。


1. **[!DNL Adobe Experience Manager]**&#x200B;で、Dynamic Media テンプレートを作成し、カウントダウンタイマーコンポーネントを追加します。

   ![](assets/timer-1.png)

1. **[!DNL Journey Optimizer]**&#x200B;で、新しいキャンペーンを作成するか、既存のキャンペーンを開いてから、メール Designerにアクセスします。

1. **HTML**&#x200B;または&#x200B;**Asset** コンポーネントをメールコンテンツにドラッグ&amp;ドロップします。

1. コンポーネントにカーソルを合わせ、**[!UICONTROL ソースコードを表示]** （HTML コンポーネントの場合）または&#x200B;**[!UICONTROL 参照]** （アセットコンポーネントの場合）をクリックします。

   ![](assets/timer-2.png)

1. **[!UICONTROL HTMLを編集]** メニューから、**[!UICONTROL Assets]**&#x200B;に移動し、**[!UICONTROL アセットセレクターを開く]**&#x200B;をクリックして、公開したDynamic Media テンプレートを参照して選択します。

   ![](assets/timer-3.png)

1. ピルをオンに切り替えて、ピルのエクスペリエンスを有効にします。 これにより、長い属性パスを非表示にすることで、読みやすさが向上します。

   ![](assets/timer-6.png)

1. **[!UICONTROL カスタム属性]** メニューで、テンプレートに必要に応じてカスタマイズ可能なURL パラメーターを設定します。

   完了したら、**[!UICONTROL 保存]**&#x200B;をクリックします。

   ![](assets/timer-4.png)

1. または、メールDesignerでアセットを選択し、**[!UICONTROL Settings]** メニューにアクセスして、Dynamic Media テンプレートのパラメーターにアクセスすることもできます。

   次の設定を行います。

   * **バナーテキスト**: タイマーで表示されるテキスト
   * **終了時間**: カウントダウンの有効期限が切れる日時。 時間はGMT （グリニッジ標準時）のみで入力します。 システムは他のタイムゾーンを受け入れません。
   * **代替テキスト**: タイマーが終了した後に表示されるメッセージ

   ![](assets/timer-5.png)

1. 「**[!UICONTROL プレビュー]**」をクリックして、リアルタイムのカウントダウン更新を含むタイマーを表示し、設定を確認します。

受信者が電子メールを開くと、Flash セールの残り時間が正確に表示されます。 後で電子メールを再度開くと、現在の残り時間を反映してカウントダウンが自動的に更新されます。 終了日の後、デフォルトのメッセージが自動的に表示されます。
