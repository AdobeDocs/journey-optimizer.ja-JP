---
title: シングルページアプリケーションの実装
description: Journey OptimizerでSPAビューを実装する方法を説明します。
feature: Web Channel
topic: Content Management
role: User
level: Intermediate
exl-id: c36d793d-0aa6-4a7a-94f2-dbfe6b644df8
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 3%

---

# シングルページアプリケーションの実装 (SPA) {#web-spa-implementation}

Adobe Experience Platform Web SDK は、シングルページアプリケーション (SPA) など、次世代のクライアント側テクノロジーでパーソナライゼーションを実行するための機能を提供します。

従来の Web サイトは、「ページ間」ナビゲーションモデル（複数ページアプリケーションと呼ばれます）で動作します。Web サイトデザインが URL に緊密に結合され、Web ページ間の遷移にページ読み込みが必要になります。

代わりに、シングルページアプリケーション (SPA) などの最新の Web アプリケーションでは、ブラウザー UI レンダリングの迅速な使用を推進するモデルを採用しています。これは、多くの場合、ページのリロードとは無関係です。 これらのエクスペリエンスは、スクロール、クリック、カーソル移動などの顧客のインタラクションによってトリガーできます。 最新の Web の枠組みが進化するにつれ、パーソナライゼーションと実験をデプロイするためのページ読み込みなどの従来の汎用イベントは機能しなくなりました。

![](assets/web-spa-vs-traditional-lifecycle.png)

## SPA向けAdobe Experience Platform Web SDK のメリット {#web-spa-benefits}

シングルページアプリケーションでAdobe Experience Platform Web SDK を使用するメリットを紹介します。

* ページ読み込み時にすべてのオファーをキャッシュし、複数のサーバー呼び出しを単一のサーバー呼び出しに減らす機能。
* 従来のサーバー呼び出しで発生する遅延時間なしで、キャッシュ経由でオファーが即座に表示されるので、サイトでのユーザーエクスペリエンスが著しく向上します。
* マーケターは、開発者による 1 回限りのセットアップで、SPA上のAdobe Journey Optimizer Web ビジュアルエディターを使用して、パーソナライゼーションおよび実験アクティビティを作成し、実行できます。

## XDM ビューとシングルページアプリケーション {#web-spa-xdm}

Adobe **[!UICONTROL Journey Optimizer]** web エディターは、ビューと呼ばれる概念を活用します。ビューとはビジュアル要素の論理的なグループで、全体でSPAエクスペリエンスを構成します。 したがって、単一ページアプリケーションは、URL ではなくユーザーのインタラクションに基づいてビュー間を移行すると考えることができます。 通常、ビューは、サイト全体、単一のページ、またはページ内のグループ化されたビジュアル要素を表すことができます。

ビューの詳細を説明するために、次の例では、架空のオンライン e コマースサイトを使用しています。

* ホームサイトに移動した後、ヒーロー画像は、季節のコレクションと、サイトで使用可能な様々な製品カタログをプロモートします。 この場合、ビューはホーム画面全体に対して定義できます。 このビューは、単に「home」と呼ぶことができます。

  ![](assets/web-spa-home.png)

* 顧客が販売している製品に興味を持つようになると、顧客は、 **メン** リンク。 ホームページと同様、 **メン** ページは、ビューとして定義できます。 このビューには「men」という名前を付けることができます。

  ![](assets/web-spa-men.png)

* ビューはサイト全体またはサイト上の視覚要素のグループとして定義できるので、製品サイトに表示される 4 つの製品をグループ化し、ビューと見なすことができます。 このビューには、「products」という名前を付けることができます。

  ![](assets/web-spa-men-products.png)

* 顧客が **すべての男性用製品** ボタンを使用してサイト上の他の製品を参照する場合、この場合、web サイトの URL は変わりませんが、表示される製品の 2 行目のみを表すビューをここで作成できます。 ビュー名は「products-page-2」になります。

* 顧客がサイトでいくつかの製品を購入することを決定し、チェックアウト画面に進みます。 買い物かご画面自体を、「cart」という名前のビューに関連付けることができます。 または、チェックアウト画面内で別のビューを使用して、以下の推奨商品を処理することもできます。

  ![](assets/web-spa-cart.png)

ビューの概念は、これよりもはるかに長く拡張できます。 これらは、サイトで定義できるビューの例に過ぎません。

## XDM ビューの実装 {#implement-xdm-views}

XDM ビューは、Adobe Journey Optimizerで活用して、マーケターがJourney Optimizerの Web ビジュアルエディターを使用して、SPA上で Web パーソナライゼーションおよび実験キャンペーンを実行できるようにすることができます。

これには、1 回限りの開発者向けの設定を完了するために、次の手順を実行する必要があります。

1. インストール [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja){target="_blank"} そして、 [web チャネルの前提条件](web-prerequisites.md) ページに貼り付けます。

2. パーソナライズするシングルページアプリケーション内のすべての XDM ビューを決定します。

3. XDM ビューを定義した後、これらのビューにコンテンツを配信するには、 `sendEvent()` ～と機能する `renderDecisions` に設定 `true` と、対応する XDM ビューをシングルページアプリケーションで表示します。 XDM ビューを渡す必要があります `xdm.web.webPageDetails.viewName`. この手順を使用すると、マーケターは、Journey Optimizer Web エディター内でこれらの表示を検出し、それらの表示に対してコンテンツの変更を適用できます。

```
 alloy("sendEvent", {
  "renderDecisions": true,
  "xdm": {
   "web": {
    "webPageDetails": {
    "viewName":"home"
   }
  }
 }
});
```

>[!NOTE]
>
>最初の `sendEvent()` を呼び出すと、エンドユーザーにレンダリングされる必要のあるすべての XDM ビューが取得され、キャッシュされます。 後続 `sendEvent()` XDM ビューが渡された呼び出しは、キャッシュから読み取られ、サーバー呼び出しなしでレンダリングされます。

## `sendEvent()` 関数の例

この節では、 `sendEvent()` 関数を React で使用して、仮想的な e コマースSPAに対応させることができます。

### 例 1:A/B テストのホームページ {#web-spa-sample-1}

マーケティングチームは、ホームページ全体で A/B テストを実行したいと考えています。

![](assets/web-spa-home.png)

ホームサイト全体で A/B テストを実行するには、 `sendEvent()` は、XDM と共に呼び出す必要があります `viewName` に設定 `home`:

```
function onViewChange() {

  var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash

  viewName = viewName || 'home'; // view name cannot be empty

  // Sanitize viewName to get rid of any trailing symbols derived from URL

  if (viewName.startsWith('#') || viewName.startsWith('/')) {
    viewName = viewName.substr(1);
  }

  alloy("sendEvent", {
    "renderDecisions": true,

    "xdm": {
      "web": {
        "webPageDetails": {
          "viewName":"home"
        }
      }
    }
  });
}

// react router v4

const history = syncHistoryWithStore(createBrowserHistory(), store);

history.listen(onViewChange);

// react router v3

<Router history={hashHistory} onUpdate={onViewChange} >
```

### 例 2：パーソナライズされた製品 {#web-spa-sample-2}

マーケティングチームは、ユーザーがすべての男性向け製品をクリックした後で、価格ラベルの色を赤に変更して、2 行目の製品をパーソナライズしたいと考えています。

![](assets/web-spa-men-products.png)

```
function onViewChange(viewName) {

  alloy("sendEvent", {
    "renderDecisions": true,
    "xdm": {
      "web": {
        "webPageDetails": {
          "viewName": viewName
        }
      }
    }
  });
}

class Products extends Component {

  render() {
    return (

        <button type="button" onClick={this.handleLoadMoreClicked}>All Men's Products</button>
    );
  }

  handleLoadMoreClicked() {
    var page = this.state.page + 1; // assuming page number is derived from component's state
    this.setState({page: page});
    onViewChange('PRODUCTS-PAGE-' + page);
  }

}
```
