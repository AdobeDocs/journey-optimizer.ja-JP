---
solution: Journey Optimizer
product: journey optimizer
title: ユーザー管理の概要
description: 権限の定義と管理方法を学ぶ
feature: Access Management
topic: Administration
role: Admin, Developer
level: Intermediate
keywords: 権限, 制限, アクセス, サンドボックス
exl-id: b8e266b1-d8eb-4c77-9341-9761b82609b0
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 93%

---

# アクセス制御の基本を学ぶ {#permissions-overview}

[!DNL Journey Optimizer] を使用すると、さまざまなユーザーに割り当てる権限を定義して管理できます。権限とは、製品内の機能へのアクセスを許可または拒否する一連の権利と制限です。

[!DNL Journey Optimizer] のアクセス制御は、Adobe Experience Cloudの **権限** を通じて提供されます。 この機能では、ユーザーを権限とサンドボックスにリンクさせる、役割とポリシーを活用します。

Journey Optimizer のアクセス制御を設定するには、組織のシステム管理者権限または製品管理者権限が必要です。権限を付与または取り消すことができる最小の役割は、製品管理者です。権限を管理できる他の管理者の役割は、システム管理者です（制限なし）。詳しくは、管理者の役割に関する[アドビヘルプセンターの記事](https://helpx.adobe.com/jp/enterprise/using/admin-roles.html){target="_blank"}を参照してください。

<!-- A high-level workflow for gaining and assigning access permissions can be summarized as follows:

* After licensing [!DNL Journey Optimizer], an email is sent to the administrator specified during licensing.
* The administrator logs in to Adobe Admin Console and selects [!DNL Journey Optimizer] from the list of products on the overview page.
* To grant access to [!DNL Journey Optimizer], it is recommended that the administrator add users to the default product profile
* In Experience Platform Permissions, the administrator can create new roles or edit the permissions and users for any existing roles.
* When creating or editing a role, the administrator adds users to the role using the users tab, and grants permissions to these users (such as "Read Datasets" or "Manage Schemas") by editing the role's permissions. Similarly, the administrator can assign access to sandboxes using the same editing option.
* When users log in to the Journey Optimizer user interface, their access to capabilities is driven by the permissions that have been granted to them from the previous step. For example, if a user does not have the View Datasets permission, the Datasets tab in the side menu will not be visible to that user.-->


[!DNL Journey Optimizer] のユーザー管理は、次の主な概念に基づいています。

* **[!UICONTROL 役割]**：役割は、同じ権限とサンドボックスを共有するユーザーのコレクションを指します。これらの役割を使用すると、組織内の様々なユーザーグループのアクセスと権限を簡単に管理できます。役割には、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにするための、一連の単一の権利（権限）が付属しています。[!DNL Journey Optimizer] を使用すると、権限レベルの異なる既存の様々な&#x200B;**[!UICONTROL 役割]**&#x200B;から選択して、ユーザーに割り当てることができます。使用可能な&#x200B;**ビルトインの役割**&#x200B;について詳しくは、[このページ](ootb-product-profiles.md)を参照してください。

* **[!UICONTROL 権限]**：権限は、**[!UICONTROL 役割]**&#x200B;に割り当てられる許可を定義できる、単一の権利です。各権限は、リソース（[!DNL Journey Optimizer] の様々な機能やオブジェクトに相当するジャーニーやオファーなど）の下に集約されています。詳しくは、[権限レベル](high-low-permissions.md)の節を参照してください。

  ![](assets/do-not-localize/permissions_2.png)

* **[!UICONTROL サンドボックス]**：仮想サンドボックスは、インスタンスを個別の独立した仮想環境に分割します。サンドボックスは、「権限」の役割を通じて割り当てられます。詳しくは、[サンドボックスの使用](sandboxes.md)を参照してください。

* **オブジェクトベースのアクセス制御**：オブジェクトへのアクセスを制限するラベル。このアプローチでは、機密性の高いデジタルアセットを権限のないユーザーから保護し、個人データの保護を強化します。詳しくは、[オブジェクトベースのアクセス管理](object-based-access.md)を参照してください。

* **属性ベースのアクセス制御**：特定のユーザーチームまたはユーザーグループのデータアクセスを管理する権限。属性ベースのアクセス制御により、管理者は属性に基づいて、特定のオブジェクトや機能へのアクセスを制御できます。属性は、スキーマフィールドやセグメントに追加されるラベルなど、オブジェクトに追加されるメタデータである場合があります。管理者は、ユーザーアクセス権限を管理する属性を含めた、アクセスポリシーを定義します。詳しくは、[属性ベースのアクセス管理](attribute-based-access.md)を参照してください。


## さらに深く掘り下げましょう

これで、**[!DNL Journey Optimizer]** のアクセス制御の概念について理解できたので、これらのドキュメントの節で詳しく説明し、権限の設定を開始します。


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="permissions.md">
<img alt="権限" src="assets/do-not-localize/role.jpg">
</a>
<div>
<a href="permissions.md"><strong>アクセス権の付与</strong></a>
</div>
<p>
</td>
<td>
<a href="ootb-permissions.md">
<img alt="ビルトインの権限" src="assets/do-not-localize/select.jpg">
</a>
<div>
<a href="ootb-permissions.md"><strong>ビルトインの権限</strong></a>
</div>
<p>
</td>
<td>
<a href="sandboxes.md">
<img alt="サンドボックスの管理" src="assets/do-not-localize/sandboxes.jpg">
</a>
<div>
<a href="sandboxes.md"><strong>サンドボックスの管理</strong></a>
</div>
<p></td>
<td>
<a href="attribute-based-access.md">
<img alt="属性ベースのアクセス制御" src="assets/do-not-localize/data-access.jpeg">
</a>
<div>
<a href="attribute-based-access.md"><strong>属性ベースのアクセス制御</strong></a>
</div>
<p>
</td>
</tr></table>