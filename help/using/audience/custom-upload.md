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
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
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

オーディエンスの読み込み方法について詳しくは、Adobe Experience Platform [&#x200B; セグメント化サービスのドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}を参照してください。

オーディエンスを CSV 形式でアップロードする方法について詳しくは、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)
