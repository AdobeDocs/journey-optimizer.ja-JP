---
solution: Journey Optimizer
product: journey optimizer
title: ビジュアルフラグメントを使用
description: Journey Optimizerのキャンペーンとジャーニーで E メールを作成する際に、ビジュアルフラグメントを使用する方法を説明します。
feature: Email Design, Templates
topic: Content Management
role: User
level: Beginner
exl-id: 25a00f74-ed08-479c-9a5d-4185b5f3c684
source-git-commit: 8579acfa881f29ef3947f6597dc11d4c740c3d68
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 72%

---

# E メールへのビジュアルフラグメントの追加 {#use-visual-fragments}

ビジュアルフラグメントは、 [電子メール](get-started-email-design.md) ジャーニーやキャンペーン内、または [コンテンツテンプレート](../content-management/content-templates.md).

>[!NOTE]
>
>でフラグメントを作成および管理する方法について説明します。 [この節](../content-management/fragments.md).

➡️ [フラグメントの管理、作成、使用方法については、このビデオをご覧ください](../content-management/fragments.md#video-fragments)

## フラグメントを使用 {#use-fragment}

1. [E メールデザイナー](get-started-email-design.md)を使用して、メールまたはテンプレートのコンテンツを開きます。

1. 左パネルから「**[!UICONTROL フラグメント]**」アイコンを選択します。

   ![](assets/fragments-in-designer.png)

1. 現在のサンドボックスで作成されたすべてのビジュアルフラグメントのリストが表示されます。 次のことができます。

   * ラベルの入力を開始して、特定のフラグメントを検索します。
   * フラグメントを昇順または降順に並べ替えます。
   * フラグメントの表示方法（カード表示またはリスト表示）を変更します。

   >[!NOTE]
   >
   >フラグメントは作成日順で並べ替えられます。最近追加されたビジュアルフラグメントがリストの最初に表示されます。

1. リストを検索して更新できます。

   >[!NOTE]
   >
   >コンテンツの編集中に一部のフラグメントが変更または追加された場合、リストは最新の変更内容で更新されます。

1. リストからフラグメントを挿入する領域にドラッグ＆ドロップします。

   ![](assets/fragment-insert.png)

1. 他のコンポーネントと同様に、コンテンツ内でフラグメントを移動できます。

1. フラグメントを選択すると、右側に対応するパネルが表示されます。ここから、コンテンツからフラグメントを削除したり、複製したりできます。また、これらのアクションは、フラグメントの上部に表示されるコンテキストメニューから直接実行することもできます。

   ![](assets/fragment-right-pane.png)

1. 「**[!UICONTROL 設定]**」タブから、次の操作を実行できます。

   * フラグメントを表示するデバイスを選択します。
   * 必要に応じて、新しいタブでフラグメントを開いて編集します。[詳細情報](../content-management/fragments.md#edit-fragments)
   * 参照を探索します。[詳細情報](../content-management/fragments.md#explore-references)

1. 「**[!UICONTROL スタイル]**」タブを使用して、フラグメントをさらにカスタマイズできます。

1. 必要に応じて、元のフラグメントの継承を解除できます。[詳細情報](#break-inheritance)

1. 必要な数のフラグメントを追加し、変更内容を&#x200B;**[!UICONTROL 保存]**&#x200B;します。

## 継承を解除 {#break-inheritance}

ビジュアルフラグメントを編集すると、変更内容が同期されます。 これらは、そのフラグメントを含むすべての&#x200B;**[!UICONTROL ドラフト]**&#x200B;ジャーニー／キャンペーンおよびコンテンツテンプレートに自動的に生成されます。

>[!NOTE]
>
>変更内容は、**[!UICONTROL ライブ]**&#x200B;ジャーニーやキャンペーンで使用されるメールには生成されません。

メールまたはコンテンツテンプレートに追加すると、フラグメントはデフォルトで同期されます。

ただし、元のフラグメントからの継承を解除することはできます。この場合、フラグメントのコンテンツは現在のデザインにコピーされ、変更は同期されなくなります。

継承を解除するには、次の手順に従います。

1. フラグメントを選択します。

1. コンテキストツールバーのロック解除アイコンをクリックします。

   ![](assets/fragment-break-inheritance.png)

1. そのフラグメントは、元のフラグメントにリンクされなくなったスタンドアロン要素になります。コンテンツ内の他のコンテンツコンポーネントと同様に編集します。[詳細情報](content-components.md)
