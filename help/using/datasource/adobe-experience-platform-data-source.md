---
solution: Journey Optimizer
product: journey optimizer
title: Adobe エクスペリエンス Platform データソース
description: Adobe エクスペリエンス Platform のデータソースを設定する方法について説明します。
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
exl-id: 9083e355-15e3-4d1f-91ae-03095e08ad16
source-git-commit: 69037a070f43fa89d0971cedc03adb577e1450d9
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Adobe エクスペリエンス Platform データソース {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Adobe エクスペリエンス Platform データソース"
>abstract="Adobe エクスペリエンス Platform データソースによって、アドビのリアルタイムカスタマープロファイルとの接続が定義されます。 このデータソースは組み込まれていて、事前に設定されています。削除することはできません。 これは、リアルタイムカスタマープロファイルサービスからデータを取得して使用するように設計されています (例えば、旅に入った人物が女性であるかどうかを確認します)。 これを使用すると、プロファイルデータを使用して、イベントデータを体験することができます。"

Adobe エクスペリエンス Platform データソースによって、アドビのリアルタイムカスタマープロファイルとの接続が定義されます。 このデータソースは組み込まれていて、事前に設定されています。削除することはできません。 このデータソースは、リアルタイムカスタマープロファイルサービスからのデータを取得して使用するように設計されています (例えば、旅に入った人物が女性であるかどうかをチェックします)。 これを使用すると、プロファイルデータを使用して、イベントデータを体験することができます。 Adobe リアルタイムカスタマープロファイルについて詳しくは、『 adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) {target = &quot;_blank&quot;} を [ 参照してください。


リアルタイムカスタマープロファイルサービスに接続するには、キーを使用して人物を識別し、名前空間でキーを contextualizes する必要があります。 そのため、このデータソースを使用できるのは、journeys がキーと名前空間を含むイベントで開始する場合に限られます。 [詳しく ](../building-journeys/journey.md) は、こちらを参照してください。

&quot;ProfileFieldGroup&quot; という名前の事前に設定されたフィールドグループを編集して、新規に追加し、ドラフトまたはライブ journeys で使用されていないものを削除できます。 [詳しく ](../datasource/configure-data-sources.md#define-field-groups) は、こちらを参照してください。


>[!NOTE]
>
>1年未満で作成された最新の1000イベントを取得することができます。

ここでは、フィールドグループを build インデータソースに追加するための主な手順について説明します。

1. データソースのリストから、「Adobe エクスペリエンスプラットフォームデータソース」を選択します。

   これにより、画面の右側にデータソースの構成ペインが表示されます。

   ![](assets/journey23.png)

1. クリックし **[!UICONTROL Add a New Field Group]** て、取得する一連の新しいフィールドを定義します。 [詳しく ](../datasource/configure-data-sources.md#define-field-groups) は、こちらを参照してください。

   ![](assets/journey24.png)

1. ドロップダウンリストから **[!UICONTROL Schema]** スキーマを選択します。 このフィールドには、Adobe エクスペリエンスプラットフォームで利用可能なプロファイルと経験イベントのスキーマが一覧表示されます。 では、スキーマの [!DNL Journey Optimizer] 作成は実行されません。 この機能は、Adobe エクスペリエンスプラットフォームで実行されます。
1. 使用するフィールドを選択します。
1. 「」を **[!UICONTROL Save]** クリックします。

フィールドグループの名前の上にカーソルを置くと、右側に2つのアイコンが表示されます。 これを使用すると、フィールドグループを削除したり、複製したりすることができます。 **[!UICONTROL Delete]**&#x200B;このアイコンは、どのライブまたはドラフトにもフィールドグループが使用されていない場合にのみ使用できます (この **[!UICONTROL Used in]** フィールドに表示される情報)。
