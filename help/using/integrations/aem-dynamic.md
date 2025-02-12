---
solution: Journey Optimizer
product: journey optimizer
title: Dynamic media
description: Journey Optimizerでの Dynamic Media の使用
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ccfc0870a8d59d16c7f5b6b02856785aa28dd307
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Dynamic Media の操作 {#aem-dynamic}

>[!AVAILABILITY]
>
>この統合は、Dynamic Media Manager as a Cloud Serviceを使用しているお客様のみが利用できます。

アセットセレクターで Dynamic Media がサポートされるようになり、Journey Optimizer内で承認済みの Dynamic Media レンディションをシームレスに選択して使用できるようになりました。 Adobe Experience Managerのアセットに加えた変更は、Journey Optimizer コンテンツに即座に反映され、手動で更新することなく、常に最新のバージョンを使用できます。

Adobe Experience Manager as a Cloud Serviceの Dynamic Media について詳しくは、[Experience Manager ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media) を参照してください。

## Dynamic Media の追加と管理

Adobe Experience Manager as a Cloud Serviceから Dynamic Media をJourney Optimizer コンテンツに直接挿入することで、あらゆる画面やブラウザーに対してコンテンツを強化および最適化します。  その後、必要に応じてサイズ変更、切り抜き、拡大およびその他の調整を行うことができます。

1. **[!UICONTROL HTML コンポーネント]** をコンテンツにドラッグ&amp;ドロップします。

1. **[!UICONTROL ソースコードを表示]** を選択します。

   ![](assets/dynamic-media-1.png)

1. **[!UICONTROL アセットセレクターを編集]** メニューで、**[!UICONTROL HTMLに移動し]** 「**[!UICONTROL Assetsセレクターを開く]** をクリックします。

   または、アセットの URL をコピー&amp;ペーストすることもできます。

   ![](assets/dynamic-media-2.png)

1. AEM アセットを参照し、コンテンツに追加するアセットを選択します。

1. 必要に応じて、アセット要件に合わせて画像パラメーター（高さ、幅など）を調整します。

1. 「**[!UICONTROL 保存]**」をクリックします。

コンテンツに dynamic media が含まれるようになりました。 Experience Managerで行った更新は、Journey Optimizerに自動的に表示されます。

## テキストオーバーレイ付き画像を使用したPersonalization

テキストオーバーレイ付きの画像を使用して、コンテンツを簡単にパーソナライズします。
上記のように、URL のAJOの変更でテキストを変更できます

1. **[!UICONTROL HTML コンポーネント]** をコンテンツにドラッグ&amp;ドロップします。

1. **[!UICONTROL ソースコードを表示]** を選択します。

1. **[!UICONTROL HTMLを編集]** メニューから、**[!UICONTROL Assetsにアクセスし]** その後 **[!UICONTROL アセットセレクターを開く]** をクリックします。

   アセットの URL をコピーして貼り付けることもできます。

1. AEM アセットを参照して、コンテンツに追加するアセットを選択します。

## 送信時間のパーソナライゼーション

WYSIWYG オーサーを利用して DM レイヤーテンプレートをパラメーター化し、コンテンツをパーソナライズする
AJO パーソナライゼーションエディターを使用したプロファイル/コンテキスト属性のマッピング

1. **[!UICONTROL HTML コンポーネント]** をコンテンツにドラッグ&amp;ドロップします。

1. **[!UICONTROL ソースコードを表示]** を選択します。

1. **[!UICONTROL HTMLを編集]** メニューから、**[!UICONTROL Assetsにアクセスし]** その後 **[!UICONTROL アセットセレクターを開く]** をクリックします。

   アセットの URL をコピーして貼り付けることもできます。

1. AEM アセットを参照して、コンテンツに追加するアセットを選択します。