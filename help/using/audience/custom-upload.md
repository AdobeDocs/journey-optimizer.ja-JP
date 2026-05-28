---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform オーディエンスについて
description: Adobe Experience Platform オーディエンスの使用方法を説明します
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 71c652ba-f38f-452c-9c1b-dcd728307baf
TQID: https://experienceleague.adobe.com/HkybhydJwQDHVEXCKM5o16ZNeiBk-n9mogm-2pwFKus
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: baecb07f-ce89-4ebb-9cd9-0f7c053f944f
subfeature_v2: id: f42b4d14-fe8a-428b-b62e-e7995eaab1b3id: b32bb433-f8c6-4931-8e52-e657230a3bf2id: e95b6013-acbe-46e9-a3b5-b80e14088d7d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 89%

---

# カスタムアップロード {#custom-upload}

Adobe Experience Platform オーディエンスポータルでは、CSV ファイルを使用してオーディエンスを読み込むことができます。

カスタムアップロードプロセス中に、ID として使用する CSV 属性と、そのマッピング先のプロファイル ID を指定します。 これにより、オーディエンスデータとプロファイルの間にリンクが作成されます。 CSV ファイルに、プロファイルで見つからない ID 値が含まれている場合、その ID 値を使用して新しいプロファイルが作成されます。

>[!NOTE]
>
>カスタムアップロードオーディエンスでは、繰り返しジャーニーで「増分読み取り」が有効になっている場合、これらのオーディエンスは固定されているので、プロファイルは最初の繰り返しでのみ取得されます。

![](assets/import-audience.png)

オーディエンスの読み込み方法について詳しくは、Adobe Experience Platform [ セグメント化サービスのドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}を参照してください。

オーディエンスを CSV 形式でアップロードする方法について詳しくは、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)
