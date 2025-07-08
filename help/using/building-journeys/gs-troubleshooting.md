---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのトラブルシューティング
description: ジャーニーのトラブルシューティング方法を学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: トラブルシューティング, ジャーニー, チェック, エラー
source-git-commit: b9db2b39629750ead953a229a46e3a75467fd203
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 11%

---

# ジャーニーのトラブルシューティング {#troubleshooting}

カスタマージャーニーが期待どおりに動作しない場合、根本原因の特定が困難な可能性があります。 問題を効率的に解決するために、最も一般的な問題領域に関するトラブルシューティングのリソースを以下に示します。 ジャーニーの失敗、実行の不整合、アクションレベルの問題のどれが表示されたかに関わらず、各セクションでは、それらを調査して解決するためのターゲットを絞ったガイダンスを提供します。

次のページで、特定のトラブルシューティングトピックを詳しく説明します。



<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="../building-journeys/troubleshooting.md"><img src="../assets/do-not-localize/troubleshooting.jpeg"></a>
    <div><strong> ジャーニーエラーのトラブルシューティング </strong><br/> テストまたは公開の前にアクティビティまたはジャーニーエラーを特定して解決する方法、およびジャーニーアクティビティにエラーが発生した場合に代替アクションを定義する方法について説明します。</div>
    </td>
    <td>
    <a href="../building-journeys/troubleshooting-execution.md"><img src="../assets/do-not-localize/ao-audiences.jpeg"></a>
    <div><strong> ジャーニー実行のトラブルシューティング </strong><br/> ジャーニーイベントのトラブルシューティング、プロファイルがジャーニーにエントリしたかどうか、ジャーニー内を移動する方法、メッセージが送信されたかどうかを確認する方法について説明します。</div>
    </td>
    <td>
    <a href="../building-journeys/troubleshooting-inbound.md" "><img src="../assets/do-not-localize/in-app.jpg"></a>
    <div><strong> インバウンドアクションのトラブルシューティング </strong><br/> インバウンドアクションに関する問題をジャーニーでデバッグする方法を説明し、インバウンドアクションを自分で特定して解決できるようにします。</div>
    </td>
    <td>
    <a href="../action/troubleshoot-custom-action.md"><img src="../assets/do-not-localize/lp-list.jpg"></a>
    <div><strong> カスタムアクションのトラブルシューティング </strong><br/>Journey Optimizer ユーザーインターフェイスの「管理」セクションから API 呼び出しを送信して、カスタムアクションをテストする方法を説明します。 この機能は、ジャーニーでカスタムアクションを使用する前または使用した後に、カスタムアクションのトラブルシューティングを行うのに役立ちます。</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="../building-journeys/troubleshooting.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="../building-journeys/troubleshooting-execution.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="../building-journeys/troubleshooting-inbound.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="../action/troubleshoot-custom-action.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    </tr>
</table>

<!--

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="Troubleshoot journey errors" src="../assets/do-not-localize/troubleshooting.jpeg" /> 
    <br><ul><li><a href="../building-journeys/troubleshooting.md">Troubleshoot journey errors</a> - Learn how to identify and resolve activity or journey errors before test or publication, and how to define a fallback action in case of an error in journey activities.</li>
    <li><a href="../building-journeys/troubleshooting-execution.md">Troubleshoot journey execution</a> - Understand how to troubleshoot journey events, check if profiles entered your journey, how they navigate through it, and if messsages are sent.</li>
     <li><a href="../building-journeys/troubleshooting-inbound.md">Troubleshoot inbound actions</a> - Learn how to debug issues related to inbound actions in a journey, in order to help you identify and resolve them on your own.</li>
     <li><a href="../action/troubleshoot-custom-action.md">Troubleshoot a custom action</a> - Learn how to test your custom actions by sending API calls from the administration section of Journey Optimizer user interface. This capability helps you troubleshoot your custom actions before or after using them in a journey.</li>
    <ul>
    <div>
     <a href="../integrations/ajo-integrations.md">Learn more</a></div>
    </div>
    <br>
  </td>
</tr>
</table>
-->

<!--
* **[Troubleshoot journey errors](../building-journeys/troubleshooting.md)**
  Learn how to identify and resolve activity or journey errors before test or publication, and how to define a fallback action in case of an error in journey activities.

* **[Troubleshoot journey execution](../building-journeys/troubleshooting-execution.md)**
  Understand how to troubleshoot journey events, check if profiles entered your journey, how they navigate through it, and if messsages are sent.

* **[Troubleshoot inbound actions](../building-journeys/troubleshooting-inbound.md)**
  Learn how to debug issues related to inbound actions in a journey, in order to help you identify and resolve them on your own.

* **[Troubleshoot a custom action](../action/troubleshoot-custom-action.md)**
  Learn how to test your custom actions by sending API calls from the administration section of Journey Optimizer user interface. This capability helps you troubleshoot your custom actions before or after using them in a journey.

-->



<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div>
    <a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/ba-p/760884?profile.language=ja">
    <img alt="一般的なエラーコードについて" src="../assets/do-not-localize/icon-quick-start.svg" /></a> 
    <br> さらに、<strong> 一般的なエラーコード </strong> とその効果的な解決方法について詳しく説明した、このAdobe Community のブログ投稿も参照してください。
    </div>
      <div>
     <a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/ba-p/760884?profile.language=ja" target="_blank">詳細情報</a></div>
    </div>
  </td>
</tr>
</table>


