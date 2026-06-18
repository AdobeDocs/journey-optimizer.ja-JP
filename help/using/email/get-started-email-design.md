---
solution: Journey Optimizer
product: journey optimizer
title: メールのデザイン
description: メールの設計方法を学ぶ
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: メール, デザイン, Stock, アセット
exl-id: e4f91870-f06a-4cd3-98b7-4c413233e310
TQID: https://experienceleague.adobe.com/fyUHQD4jpIUI2KdyrGbgktEhNNc4OWYRJ8AkgZhrIoQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d556b755-390a-43f0-be32-a08cf6236126id: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: ee5bb250-0884-4d71-86eb-d8489e8bcaddid: f550d0f2-143d-4093-9463-467fbec95fccid: fb9a80eb-bebc-492f-a0e9-584595621ebbid: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 94f6692162ca7d37cf5d9df4c0f48371bafec9fc
workflow-type: tm+mt
source-wordcount: 821
ht-degree: 87%

---

# メールデザインの基本を学ぶ {#get-started-content-design}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;電子メール Designerで電子メールコンテンツをデザインする方法、ゼロから作成する主な手順、コードを作成する方法、HTMLをインポートする方法、および電子メールをクライアント間で適切にレンダリングするベストプラクティスについて説明します。

>[!ENDSHADEBOX]

E メールデザイナーにアクセスしてメールコンテンツのデザインを開始するには、まずジャーニーまたはキャンペーンで[メールを作成](create-email.md)する必要があります。

その後、[!DNL Journey Optimizer] **メールデザイン機能**&#x200B;を使用して既存のコンテンツを読み込んだり、レスポンシブなメールをゼロから作成したりできます。 [詳細情報](content-from-scratch.md)

また、E メールデザイナーでは、次の操作も実行できます。

* **Adobe Experience Manager Assets Essentials** を活用してメールを強化し、独自のアセットデータベースを作成および管理します。 [詳細情報](../integrations/assets.md)

* **Adobe Stock の写真**&#x200B;を検索しコンテンツを作成し、メールデザインを向上します。 [詳細情報](../integrations/stock.md)

* プロファイル属性に基づいてパーソナライズされたメッセージと動的メッセージを作成し、カスタマーエクスペリエンスを強化します。 [パーソナライズ機能](../personalization/personalize.md)および[動的コンテンツ](../personalization/get-started-dynamic-content.md)の詳細をご覧ください。

➡️ [この機能をビデオで確認](#video)

## メールコンテンツ作成の主な手順 {#key-steps}

メールを作成したら、メールコンテンツのデザインを開始できます。

1. ジャーニーまたはキャンペーンの設定画面から、**[!UICONTROL コンテンツを編集]**&#x200B;画面に進み、E メールデザイナーにアクセスします。 [詳細情報](create-email.md#define-email-content)

   ![](assets/email_designer_edit_email_body.png)

1. E メールデザイナーのホームページで、次のオプションからメールのデザイン方法を選択します。

   * E メールデザイナーのインターフェイスで&#x200B;**メールをゼロから設計**&#x200B;し、[Adobe Experience Manager Assets](../integrations/assets.md) の画像を活用します。 メールコンテンツのデザイン方法については、[この節](content-from-scratch.md)を参照してください。

   * E メールデザイナーで直接 **Raw HTML をコーディングまたは貼り付け**&#x200B;ます。 独自のコンテンツのコーディング方法については、[この節](code-content.md)を参照してください。

     >[!NOTE]
     >
     >キャンペーンでは、**[!UICONTROL コンテンツを編集]**&#x200B;画面から「**[!UICONTROL コードエディター]**」ボタンを選択することもできます。 [詳細情報](create-email.md#define-email-content)

   * ファイルまたは .zip フォルダーから&#x200B;**既存の HTML コンテンツを読み込み**&#x200B;ます。 メールコンテンツの読み込み方法については、[この節](existing-content.md)を参照してください。

   * AI を活用した画像から HTML へのコンバーターを使用して、**画像デザインを HTML テンプレートに変換します**。 静的画像を編集可能なメールテンプレートに変換する方法について詳しくは、[この節](../content-management/image-to-html.md)を参照してください。

   * ビルトインまたはカスタムテンプレートのリストから&#x200B;**既存のコンテンツを選択します**。 メールテンプレートの操作方法については、[この節](../email/use-email-templates.md)を参照してください。

   ![](assets/email_designer_create_options.png)

1. メールコンテンツを定義してパーソナライズしたら、**自動コンテンツチェック**&#x200B;を使用してメールコンテンツを検証し、サポートされていないタグ、空のdiv、サイズ制限の違反など、HTMLやCSSの問題を送信前にオーサリングパネルで直接検出できます。 [詳細情報](content-check.md)

   ![問題のある電子メール Designerのコンテンツチェックペイン ](assets/content-check.png)

1. また、コンテンツ品質を検証して、読みやすさ、コンテンツのまとまり、有効性に関する潜在的な問題を特定することもできます。 [コンテンツ品質の検証の詳細情報](../content-management/brands-score.md#validate-quality)

   ![](../content-management/assets/brand-score-7.png)

1. 最後に、コンテンツを書き出して検証または後で使用できます。 「**[!UICONTROL HTML をエクスポート]**」をクリックして、 コンピューターに HTML とアセットを含む zip ファイルを保存します。

   ![](assets/email_designer_export.png)

## メールデザインのベストプラクティス {#best-practices}

メールを送信する際は、受信者がメールを転送する可能性があることを考慮することが重要です。これにより、メールのレンダリングで問題が発生する可能性があります。 これは、転送に使用されるメールプロバイダーでサポートされていない可能性がある CSS クラスを使用する場合に特に当てはまります。例えば、モバイルデバイスで画像を非表示にするのに「is-desktop-hidden」CSS クラスを使用している場合などです。

こうしたレンダリングの問題を最小限にするために、メールのデザイン構造をできるだけ簡単に保つことをお勧めします。 デスクトップデバイスとモバイルデバイスの両方で適切に機能する単一のデザインを使用し、複雑な CSS クラスや、すべてのメールクライアントで完全にはサポートされない他のデザイン要素を使用しないようにします。

これらのベストプラクティスに従うと、受信者による表示や転送の方法に関係なく、一貫して正しくメールをレンダリングできます。

メールデザインのベストプラクティスについては、以下の表を参照してください。

| 推奨 | 慎重に使用 | 推奨しない |
|-|-|-|
| <ul><li>構造用の<b>静的なテーブルベースのレイアウト</b></li> <li>レイアウトの一貫性を保つための <b>HTML テーブルとネストされたテーブル</b></li> <li><b>テンプレートの幅</b>は 600～800 ピクセル </li> <li>スタイル設定用の<b>シンプルなインライン CSS</b> </li> <li>ユニバーサル互換性のための <b>web セーフフォント</b></li> | <ul><li><b>背景画像</b>は、特定のメールプラットフォームでは表示されない場合があります。</li><li><b>カスタム web フォント</b>にはユニバーサルサポートがありません。</li><li><b>ワイドレイアウト</b>は、小さな画面では適切に表示されない場合があります。</li><li><b>画像マップ</b>の機能は限定的です。</li><li><b>埋め込み CSS</b> は、メール配信中に削除される場合があります。</li> | <ul><li><b>JavaScript</b> は、通常、メール環境ではサポートされていません。</li> <li> <b>`<iframe>`</b> タグは、ほとんどのプラットフォームでブロックされています。 </li> <li><b>Flash</b> は旧式で、サポートされなくなりました。</li> <li><b>埋め込みオーディオ</b>は、多くの場合、再生できません。</li> <li><b>埋め込みビデオ</b>は、多くのメールプラットフォームと互換性がありません。</li> <li> <b>Forms</b> は、メール内では機能しません。</li> <li> `<div>` レイヤ化はレンダリングの問題を引き起こす可能性があります。</li> |

>[!NOTE]
>
>[欧州アクセシビリティ法](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32019L0882){target="_blank"}では、すべてのデジタル通信がアクセス可能である必要があると規定しています。 この節に示すメールデザインのベストプラクティスに加えて、[このページ](accessible-content.md)に記載されている、E メールデザイナーを使用してアクセシブルなコンテンツを作成する際に固有のガイドラインにも必ず従ってください。

## チュートリアルビデオ {#video}

メッセージエディターでメールコンテンツを作成する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334150?quality=12)

A/B テストを行うようにコンテンツ実験を設定し、ビジネス目標を最大限に推進するメールコンテンツを探索する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419893)
