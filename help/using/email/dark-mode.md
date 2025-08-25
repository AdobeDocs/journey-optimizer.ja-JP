---
solution: Journey Optimizer
product: journey optimizer
title: ダークモードに切り替え
description: E メールデザイナーでのダークモードの使用方法について説明します。
badge: label="ベータ版" type="Informative"
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: ダークモード, メール, カラー, エディター
hide: true
hidefromtoc: true
exl-id: 27442cb0-5027-4d9c-9d3c-9ec33af7c9ff
source-git-commit: 23684c906d11c7f54eb28cac7c2697964e723a2e
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 100%

---

# ダークモードコンテンツの管理 {#dark-mode}

>[!CONTEXTUALHELP]
>id="ac_edition_darkmode"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えると、レンダリング方法のプレビューや、特定のカスタム設定の定義ができます。 <br>注意：最終的なレンダリングは、受信者のメールクライアントに応じて異なります。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

>[!CONTEXTUALHELP]
>id="ac_edition_darkmode_image"
>title="特定の画像をダークモードで使用"
>abstract="ダークモードがオンの場合に表示される別の画像を選択できます。 <br>注意：ダークモードで使用する特定の画像を追加しても、すべてのメールクライアントで正しくレンダリングされるとは限りません。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

>[!CONTEXTUALHELP]
>id="ac_edition_darkmode_preview"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えると、サポートされているメールクライアントでどのようにレンダリングされるかをプレビューできます。 <br>注意：最終的なレンダリングは、受信者のメールクライアントに応じて異なります。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

>[!AVAILABILITY]
>
>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。

メールをデザインする際に、[!DNL Journey Optimizer] [E メールデザイナー](get-started-email-design.md)を使用すると、特定のカスタム設定を定義できる&#x200B;**[!UICONTROL ダークモード]**&#x200B;に切り替えることができます。ダークモードがオンの場合、サポートするメールクライアントでは、このモード用に定義した設定が表示されます。

>[!WARNING]
>
>ダークモードの最終的なレンダリングは、受信者のメールクライアントに応じて異なります。
>
>すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。<!--[See the list](#non-supporting-email-clients)-->さらに、一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードのみが適用されます。この場合、E メールデザイナーで定義したカスタム設定はレンダリングできません。

ダークモードをサポートするメールクライアントのリストについて詳しくは、[この節](#supporting-email-clients)を参照してください。

## ダークモードとは {#what-is-dark-mode}

ダークモードを使用すると、サポートされているメールクライアントとアプリで、メールの背景を暗くし、テキスト、ボタン、他の UI 要素を明るい色で表示できます。目への負担を軽減し、バッテリー寿命を短縮し、低照度環境での読みやすさを向上させて、より快適な視聴エクスペリエンスを実現します。

<!--Dark Mode uses a dark color palette with light text and UI elements to reduce eye strain, save battery life, and improve readability in low-light environments.-->

これは、主要なオペレーティングシステムとアプリ（Apple メール、Gmail、Outlook、Twitter、Slack）全体で高まるトレンドとして、すべてのユーザーにとってコンテンツが読みやすく視覚的に魅力的であることを確保するために、最新のメールデザインでは重要な考慮事項になっています。

ただし、ダークモードでは、すべてのデバイスでメールの表示がまったく同じになることを保証することはできません。また、メールアプリやデバイスにより元のデザインが上書きされることで、視覚的な変化が発生する場合もあります。

実際、メールクライアントによりダークモードを適用する方法は、次のように異なる場合があります<!--between different devices and apps-->。

* すべてのメールクライアントがこの機能をサポートしているわけではありません。

  >[!NOTE]
  >
  >ダークモードをサポートしないメールクライアントのリストについて詳しくは、[この節](#non-supporting-email-clients)を参照してください。

* 一部のメールクライアントでは、色、背景、画像を自動的に調整します。この場合、E メールデザイナーでカスタム設定を定義しても、これらの設定はレンダリングされない可能性があります。

* 他のメールクライアントには、カスタムダークモードをレンダリングするオプションが用意されています（`@media (prefers-color-scheme: dark)` メソッドを使用する場合など）。この場合、E メールデザイナーで定義した特定の設定が表示されます。E メールデザイナーでカスタムダークモード設定を定義する方法について詳しくは、[この節](#define-custom-dark-mode)を参照してください。

## E メールデザイナーでのダークモード {#dark-mode-email-designer}

E メールデザイナーでのダークモードに関しては、考慮すべき 2 つの側面があります。

* サポートされているほとんどのメールクライアントで、デフォルトのダークモードがどのようにレンダリングされるかをプレビューできます。[詳細情報](#preview-dark-mode)

<!--
    >[!CAUTION]
    >
    >The final rendering may vary according to the recipient's email client. To see the exact rendering for each email client, use the [Email rendering](../content-management/rendering.md) option.-->

* サポートされているメールクライアントのデフォルト設定を上書きする場合は、編集中のメールに適用するカスタムダークモード設定を定義できます。[詳細情報](#define-custom-dark-mode)

<!--
    >[!WARNING]
    >
    >Not all email clients support custom dark mode. Some email clients only apply their own default dark mode for all emails that are received. In this case, the custom settings that you defined in the Email Designer cannot be rendered. [Learn more](#guardrails)-->

### デフォルトのダークモードのプレビュー {#preview-dark-mode}

E メールデザイナーでダークモードにアクセスし、デフォルトのダークモード設定のプレビューを取得するには、次の手順に従います。

1. E メールデザイナーのホームページで、「**[!UICONTROL ゼロからデザイン]**」オプションを選択します。[詳細情報](content-from-scratch.md)

<!--Should work with templates and themes, NOT for LP and fragments - but TBC with eng.
    >[!NOTE]
    >
    >Currently you may not be able to switch to dark mode if you select an [email template](use-email-templates.md) or if you apply a [theme](apply-email-themes.md).-->

1. [構造](content-from-scratch.md)と[コンテンツコンポーネント](content-components.md)をコンテンツに追加します。

1. 中央のキャンバスの右上で、切替スイッチを&#x200B;**[!UICONTROL ダークモード]**&#x200B;に切り替えます。

   ![](assets/light-mode-toggle.png)

1. デフォルトのダークモードのプレビューが表示されます。

   ![](assets/dark-mode-default.png)

デフォルトでは、E メールデザイナーのダークモードのプレビューには、画像とアイコンを除くすべての要素に「フルカラー反転」カラースキームが適用されます。

つまり、明るい要素と暗い要素の領域を検出して反転させることで、明るい背景は暗く、暗いテキストは明るくなり、暗い背景は明るく、明るいテキストは暗くなります。

>[!CAUTION]
>
>最終的なレンダリングは、受信者のメールクライアントによって異なる場合があります。各メールクライアントの最終結果にできるだけ近いシミュレーションを表示するには、「[メールレンダリング](../content-management/rendering.md)」オプションを使用します。

<!--This is custom dark mode:

  ![](assets/dark-mode-custom.png)

Here you can see that we have applied a different background, defined another image and change the color of the text and button.-->

### カスタムダークモードの定義 {#define-custom-dark-mode}

**[!UICONTROL ダークモード]**&#x200B;に切り替えたら、受信者のメールクライアントでダークモードが有効になっている場合にのみ表示されるコンテンツの特定のスタイル要素の編集を選択できます（その機能がサポートされている場合）。

>[!WARNING]
>
>すべてのメールクライアントがダークモードをサポートしているわけではありません。さらに、一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードのみが適用されます。どちらの場合も、E メールデザイナーで定義したカスタム設定はレンダリングできません。

E メールデザイナーのカスタムダークモードのスタイル設定を活用するには、Journey Optimizer では<!-- `@media (prefers-color-scheme: dark)` method--> `@media (prefers-color-scheme: dark)` CSS クエリを使用します。このクエリでは、ユーザーのメールクライアントがダークモードに設定されているかどうかを検出し、メールで定義したダークテーマのデザインが適用されます。

カスタムダークモードの設定を定義するには、次の手順に従います。

1. E メールデザイナーで&#x200B;**[!UICONTROL ダークモード]**&#x200B;プレビューに切り替えます。[詳細情報](#preview-dark-mode)

1. テキスト、背景、ボタンなどのスタイル設定の色属性を編集します。

1. 画像やアイコンの色は変更できませんが、特定のアセットはダークモード用にのみ定義できます。これを行うには、任意の画像を選択します。**[!UICONTROL 設定]**&#x200B;パネルの専用切替スイッチを使用して&#x200B;**[!UICONTROL ダークモード]**&#x200B;に切り替え、別のアセットを選択します。

   ![](assets/dark-mode-image.png)

   <!--![](assets/dark-mode-custom.png)-->

1. いつでも&#x200B;**[!UICONTROL ライブビューに切り替えて]**、様々なデバイスサイズでコンテンツがどのようにレンダリングされる可能性があるかを確認できます。このビューから、画面上部のダークモード切替スイッチを選択すると、様々なデバイスをまたいでコンテンツのダークモードバージョンをプレビューできます。

   ![](assets/dark-mode-live-view.png){width="80%" align="center"}

   >[!CAUTION]
   >
   >ライブビューは、様々なデバイスサイズをまたいでレンダリングがどのように表示される可能性があるかを比較するのにデザインされた汎用プレビューです。最終的なレンダリングは、受信者のメールクライアントによって異なる場合があります。

1. ダークモードの変更に満足したら、「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

   ![](assets/dark-mode-simulate.png)

1. 「**[!UICONTROL メールをレンダリング]**」を選択し、Litmus アカウントに接続します。様々なメールクライアントでの最終的なダークモードレンダリングを確認できます。詳しくは、[メールのレンダリング](../content-management/rendering.md)を参照してください。

   >[!WARNING]
   >
   >シミュレーションではダークモードでのメールの表示に非常に近いですが、メールサービスプロバイダーやデバイスレベルの設定の違いにより、実際のレンダリングは異なる場合があります。

## ベストプラクティス {#best-practices}

主要なメールクライアント間でダークモードの採用が増加するにつれて、[カスタムダークモード](#define-custom-dark-mode)を使用しているかどうかに関係なく、明るい環境と暗い環境の両方でメールがどのようにレンダリングされるかを考慮することが重要になります。

ダークモードでは、色、背景、画像が変更される可能性があり、場合によってはデザインの選択が上書きされることもあります。 視覚的な一貫性、アクセシビリティ、ブランドの整合性を確保するには、次に示すベストプラクティスに従ってください。

**画像とロゴの最適化**

* 白色の背景または明るい背景がハードコードされた画像は回避します。

* ロゴやアイコンを透明な背景の PNG として保存し、ダークモードで白いボックスが表示されないようにします。

* 透明度がオプションでない場合は、不自然な色の反転を防ぐために、デザインでは単色の背景に画像を配置します。

**背景に対する注意**

* ライトモードとダークモードの両方で読みやすくするには、テキストと背景色の間に十分なコントラストを確保します。

* 重要なコンテンツについては、背景色にのみ依存することは回避します。一部のクライアントでは、ダークモードで背景色を上書きすることがあるので、重要な情報が表示されていることを確認します。

**ダークモードでのアクセス可能なコンテンツのデザイン**

* 色覚異常のある人物でも簡単に区別できる色の組み合わせを使用します。

* 明るい背景と暗い背景の両方に対してコントラストを確保するのに、ミッドトーンパレットを使用します。

* 読みやすさを向上させ、Web コンテンツアクセシビリティガイドライン（WCAG）標準を満たすには、コントラストの高いアクセシブルな色の組み合わせを使用します。WebAIM のコントラストチェッカーなどのツールを使用して、色のコントラストを検証します。

* 読みやすさに影響する場合があるので、細いフォントは回避します。ブランドに細いフォントが必要な場合は、ダークモードで太字にします。

* 純粋な白色に純粋な黒色を重ねると、目への負担の原因となる場合があり、一部のメールクライアントにより自動的に反転される可能性があるので、これを回避します。

* ダークモードがサポートされていない場合は、アクセスできるフォールバックスタイル設定を指定します。

**ダークモード環境でのメールのテスト**

* 問題を早期に発見するには、反転したカラースキームを使用する E メールデザイナーの[ダークモードのプレビュー](#preview-dark-mode)を使用します。

* Litmus を活用した「[メールレンダリング](../content-management/rendering.md)」オプションを使用して、主要なメールクライアント（Apple メール、Gmail、Outlook）でデザインをシミュレートし、ダークモードでの色と画像の動作を確認します。

<!--**Inline critical styles**

Inline CSS helps maintain more control over styling, as some clients strip external styles in dark mode.-->

## ダークモードをサポートしているメールクライアント {#supporting-email-clients}

ダークモードをサポートしている主なメールクライアントのリストを以下に示します。

>[!NOTE]
>
>これらのメールクライアントの一部のバージョンはダークモードをサポートしてませんが、分かりやすくするために、この表に含めています。

| ダークモードをサポートしているメールクライアント | 互換性のあるバージョン | *サポートされていないバージョン* |
|---------|----------|---------|
| Apple メール macOS | 12.4、16.0 | *10.3* |
| Apple メール iOS | 13.0、16.1 | *12.2* |
| Outloook macOS | 2019、16.70、16.80 | 該当なし |
| Outlook.com | 2019-07、2022-12 | 該当なし |
| Outlook iOS | 2020-01、2022-12 | 該当なし |
| Outlook Android | 2023-03 | *2020-01、2022-12* |
| Samsung メール（Android） | 6.1 | *6.0* |
| Mozilla Thunderbird（macOS） | 68.4 | *60.8、78.5、91.13* |
| Fastmail（デスクトップ Web メール） | 2022-12 | *2021-07* |
| HEY（デスクトップ Web メール） | 2020-06 | *2022-12* |
| Orange デスクトップ Web メール | 2019-08、2021-03、2022-12、2024-04 | 該当なし |
| Orange iOS | 2022-12、2024-04 | *2020-01* |
| Orange Android | 2024-04 | *2020-01、2022-12* |
| LaPoste.net | 2021-08、2022-12 | 該当なし |
| SFR デスクトップ Web メール | 2019-08、2022-12 | 該当なし |
| GMX（iOS と Android） | 2022-06 | 該当なし |
| 1&amp;1（デスクトップ Web メールと Android） | 2022-06 | 該当なし |
| WEB.DE（iOS と Android） | 2022-06 | 該当なし |
| Free.fr | 2022-12 | 該当なし |

>[!WARNING]
>
>ダークモードの最終的なレンダリングは、各メールクライアントに応じて異なるので、結果はクライアントごとに異なる場合があります。

<!--
* Check out the list of [email clients supporting dark mode](https://www.caniemail.com/search/?s=dark){target="_blank"}

* Learn more on Dark mode in this [Litmus blog post](https://www.litmus.com/blog/the-ultimate-guide-to-dark-mode-for-email-marketers){target="_blank"}
-->

## ダークモードをサポートしていないメールクライアント {#non-supporting-email-clients}

一部のメールクライアントでは、ユーザーがインターフェイスをダークモードに切り替えることができますが、この設定は HTML メールの表示方法には影響しません。インターフェイスがライトモードかダークモードかに関係なく、メールは同じようにレンダリングされます。これらのクライアントのリストを次に示します。

| ダークモードをサポートしていないメールクライアント |
|---------|
| Gmail（デスクトップ web メール、iOS、Android、モバイル web メール） |
| Outlook Windows |
| Outlook Windows メール |
| Yahoo! メール |
| AOL |
| ProtonMail |
| SFR iOS |
| SFR Android |
| GMX デスクトップ Web メール |
| Mail.ru |
| WEB.DE デスクトップ Web メール |
| T-online.de |
