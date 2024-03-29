---
title: 決定管理の概要
description: Adobe Journey Optimizer が、的確なオファーを適切なタイミングで顧客に送信する方法を説明します
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: 659984cb-b232-47ba-9f5a-604bf97a5e92
source-git-commit: d4a91dcd032af03504ab7bbf97b2e19338c32397
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 100%

---

# 意思決定管理について {#about-decision-management}

[!DNL Journey Optimizer] を使用すると、すべてのタッチポイントをまたいで、適切なタイミングで最高のオファーとエクスペリエンスを顧客に提供できます。デザインが完了すると、パーソナライズされたオファーを使用してオーディエンスをターゲットに設定できます。

意思決定管理では、マーケティングオファーの一元化されたライブラリと、Adobe Experience Platform が作成するリッチなリアルタイムプロファイルにルールと制約を適用する意思決定エンジンを使用して、的確なオファーを適切なタイミングで顧客に送信します。

意思決定管理の機能は、2 つの主要コンポーネントで構成されています。


* **一元化されたオファーライブラリ**&#x200B;は、オファーを構成する様々な要素を作成および管理し、それらの規則と制約を定義するインターフェイスです。
* **Offer Decisioning エンジン**&#x200B;は、Adobe Experience Platform のデータとリアルタイム顧客プロファイルをオファーライブラリとともに活用し、オファーの配信に適切な時間、顧客およびチャネルを選択します。

![](../assets/architecture.png)

次のような利点があります。

* 複数のチャネルをまたいでパーソナライズされたオファーを提供することで、キャンペーンのパフォーマンスが向上します。
* ワークフローの向上：マーケティングチームは、配信やキャンペーンを複数作成する代わりに、単一の配信を作成し、テンプレートの各部分のオファーを変えることでワークフローを向上させることができます。
* キャンペーンと顧客全体にオファーを表示する回数を制御します。

➡️ [意思決定管理について詳しくは、これらのビデオをご覧ください](#video)


>[!NOTE]
>
>**Offer Decisioning** アプリケーションサービスを利用する [ Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} ユーザーの場合は、この節で説明する意思決定管理機能もすべて適用されます。

## オファーと決定について {#about-offers-and-decisions}

**オファー**&#x200B;は、顧客に提示する条件を定義するコンテンツ、実施要件ルール、制約で構成されます。

オファーは&#x200B;**オファーライブラリ**&#x200B;を使用して作成されます。このライブラリは、実施要件ルールや制約を複数のコンテンツに関連付けてオファーを作成および公開できる中央オファーカタログを提供します（「[オファーライブラリユーザーインターフェイス](../get-started/user-interface.md)」を参照）。

![](../assets/offer_structure.png)

オファーライブラリがオファーで強化されたら、オファーを&#x200B;**決定**&#x200B;に統合できます。

決定とは、配信ターゲットに応じて提供すべき最適なオファーを選択するために、Offer Decisioning エンジンを利用するオファーのコンテナです。

## よくあるユースケース {#common-use-cases}

意思決定管理の機能および Adobe Experience Platform との統合により、多くのユースケースが対象となり、顧客エンゲージメントやコンバージョンを向上できます。


* Adobe Experience Platform からのデータに基づいて、web サイトのホームページに、訪問顧客の興味ポイントに一致するオファーを表示します。

  ![](../assets/website.png)

* 顧客がいずれかの店舗のそばを通りかかった場合、属性（ロイヤルティ、性別、以前の購入など）に応じて利用可能なオファーを通知するプッシュ通知を送信します。

  ![](../assets/push_sample.png)

* 意思決定管理は、顧客がサポートチームに連絡する際のエクスペリエンスを向上できるようサポートします。
意思決定管理 API を使用すると、顧客が取り消したオファーと次善のオファーに関する情報を、コールセンター担当者のポータルに表示することができます。


  ![](../../assets/do-not-localize/call-center.png)

## 意思決定管理へのアクセスの許可 {#granting-acess-to-decision-management}

意思決定管理機能へのアクセス権限および使用権限は、[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html){target="_blank"} で管理します。

意思決定管理機能へのアクセス権を付与するには、**[!UICONTROL 製品プロファイル]**&#x200B;を作成し、対応する権限をユーザーに割り当てる必要があります。[!DNL Journey Optimizer] のユーザーと権限の管理について詳しくは、[この節](../../administration/permissions.md)を参照してください。

意思決定管理に特有の権限の一覧については、[この節](../../administration/high-low-permissions.md#decisions-permissions)を参照してください。

## 用語集 {#glossary}

意思決定管理を使用する際の主な概念のリストを以下に示します。


* **キャッピング**&#x200B;または&#x200B;**フリークエンシーキャップ**：キャッピングは、オファーの表示回数を定義する制約として使用されます。キャップには 2 種類あり、組み合わせターゲットオーディエンスでオファーを提案できる回数（別名「合計キャップ」）と、同じエンドユーザーにオファーを提案できる回数（別名「プロファイルキャップ」）があります。

* **コレクション**：マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。

* **決定**：オファーの選択を通知するロジックが含まれています。

* **決定ルール**：決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するためにプロファイルに適用されます。

* **実施要件を満たすオファー**：実施要件を満たすオファーは、アップストリームで定義された制約に一致し、プロファイルに対して一貫して提示できるものです。

* **意思決定管理**：ビジネスロジックと決定ルールを使用して、エンドユーザー向けにパーソナライズされたオファーエクスペリエンスを作成し、あらゆるチャネルやアプリケーションで配信できます。

* **フォールバックオファー**：フォールバックオファーは、エンドユーザーが使用されるコレクションのパーソナライズされたオファーの対象でない場合に表示されるデフォルトのオファーです。

* **オファー**：オファーは、オファーを表示する資格のあるユーザーを指定するルールが関連付けられているマーケティングメッセージです。

* **オファーライブラリ**：オファーライブラリは、パーソナライズされたオファーやフォールバックオファー、決定ルールおよび決定を管理するために使用される一元化されたライブラリです。

* **パーソナライズされたオファー**：パーソナライズされたオファーは、実施要件ルールおよび制約に基づいてカスタマイズできるマーケティングメッセージです。

* **プレースメント**：プレースメントは、エンドユーザー用のオファーが表示される場所および／またはコンテキストです。

* **優先度**：優先度は、実施要件、日付、キャッピングなど、すべての制約を満たすオファーのランク付けに使用されます。

* **表示域**：表示域とは、チャネルがオファーを表示する際に使用する情報（場所や言語など）です。

## チュートリアルビデオ{#video}

### 意思決定管理とは {#what-is-offer-decisioning}

以下のビデオでは、 意思決定管理の主な機能、アーキテクチャおよび使用例を紹介しています。


>[!VIDEO](https://video.tv.adobe.com/v/326961?quality=12&learn=on)

### オファーの定義と管理 {#use-offer-decisioning}

次のビデオでは、意思決定管理を使用してオファーを定義および管理し、リアルタイムの顧客データを活用する方法を示します。


>[!VIDEO](https://video.tv.adobe.com/v/326841?quality=12&learn=on)


