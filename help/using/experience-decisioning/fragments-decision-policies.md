---
title: 決定ポリシーでのフラグメントの活用
description: 決定ポリシーでフラグメントを活用する方法を学ぶ
feature: Decisioning
topic: Integrations
role: User
level: Experienced
source-git-commit: 083545ff7b2dc5ce45ef3766321fdf12e1b96c5c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 91%

---


# 決定ポリシーでのフラグメントの活用 {#fragments}

決定ポリシーにフラグメントを含む決定項目が含まれている場合は、決定ポリシーコードでこれらのフラグメントを活用できます。[詳しくは、フラグメントを参照してください。](../content-management/fragments.md)

>[!AVAILABILITY]
>
>この機能は現在、**コードベースのエクスペリエンス** チャネルと一連の組織（限定提供）でのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。

例えば、複数のモバイルデバイスモデルに対して異なるコンテンツを表示するとします。決定ポリシーで使用している決定項目に、これらのデバイスに対応するフラグメントが追加されていることを確認します。[方法についてはこちらを参照してください](items.md#attributes)。

![](assets/item-fragments.png){width=70%}

完了したら、次のいずれかの方法を使用できます。

>[!BEGINTABS]

>[!TAB コードを直接挿入する]

以下のコードブロックを決定ポリシーコードにコピー＆ペーストするだけです。`variable` をフラグメント ID に、`placement` をフラグメント参照キーに置き換えます。

```
{% let variable =  get(item._experience.decisioning.offeritem.contentReferencesMap, "placement").id %}
{{fragment id = variable}}
```

>[!TAB 詳細な手順に従う]

1. 「**[!UICONTROL ヘルパー関数]**」に移動し、コードパネルに **Let** 関数 `{% let variable = expression %} {{variable}}` を追加します。ここでフラグメントの変数を宣言できます。

   ![](assets/decision-let-function.png)

1. **Map**／**Get** 関数 `{%= get(map, string) %}` を使用して、式を作成します。マップは、決定項目で参照されるフラグメントです。文字列は、決定項目で&#x200B;**[!UICONTROL フラグメント参照キー]**&#x200B;として入力したデバイスモデルに指定できます。

   ![](assets/decision-map-function.png)

1. また、このデバイスモデル ID を含むコンテキスト属性を使用することもできます。

   ![](assets/decision-contextual-attribute.png)

1. フラグメントに選択した変数をフラグメント ID として追加します。

   ![](assets/decision-fragment-id.png)

>[!ENDTABS]

フラグメント ID と参照キーは、決定項目の「**[!UICONTROL フラグメント]**」セクションから選択されます。

>[!WARNING]
>
>フラグメントキーが正しくない場合や、フラグメントコンテンツが有効でない場合、レンダリングは失敗し、Edge 呼び出しでエラーが発生します。

## フラグメント使用時のガードレール {#fragments-guardrails}

**決定項目とコンテキストの属性**

[!DNL Journey Optimizer] のフラグメントでは、決定項目属性とコンテキスト属性はデフォルトでサポートされていません。ただし、以下に説明するように、代わりにグローバル変数を使用できます。

例えば、フラグメントで *sport* 変数を使用するとします。

1. フラグメント内でこの変数を参照します。例：

   ```
   Elevate your practice with new {{sport}} gear!
   ```

1. 決定ポリシーブロック内で、**Let** 関数を使用して変数を定義します。以下の例では、決定項目属性を使用して *sport* が定義されています。

   ```
   {#each decisionPolicy.13e1d23d-b8a7-4f71-a32e-d833c51361e0.items as |item|}}
   {% let sport = item._cjmstage.value %}
   {{fragment id = get(item._experience.decisioning.offeritem.contentReferencesMap, "placement1").id }}
   {{/each}}
   ```

**決定項目フラグメントコンテンツの検証**

* これらのフラグメントは動的な性質を持つため、キャンペーンで使用する場合、決定項目で参照されるフラグメントでは、キャンペーンコンテンツ作成時のメッセージ検証がスキップされます。

* フラグメントコンテンツの検証は、フラグメントの作成中と公開中にのみ行われます。

* JSON フラグメントの場合、JSON オブジェクトの有効性は保証されません。 式フラグメントコンテンツが決定項目で使用できるように、有効な JSON であることを確認します。

実行時に、キャンペーンコンテンツ（決定項目のフラグメントコンテンツを含む）が検証されます。検証に失敗した場合、キャンペーンはレンダリングされません。
