---
title: 離脱リンク
description: 離脱リンクの名前。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 22%

---

# 離脱リンク

「離脱リンク」 [ ディメンション ](overview.md)は、サイトに実装された離脱リンクの名前を報告します。 離脱リンク現在のドメインから訪問者を離れるアウトバウンドクリックを追跡します。 このディメンションは、最も頻繁にクリックされるアウトバウンドリンクを把握したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、`pe` クエリ文字列の値に応じて、イメージリクエストの[`pev2` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。 `pe` クエリ文字列によって、どのリンクディメンションが`pev2`値を受け取るかが決まります。

* **[カスタムリンク](custom-link.md)**: `lnk_o`
* **[ダウンロードリンク](download-link.md)**: `lnk_d`
* **リンクを終了** （このページ）: `lnk_e`

`pev2`が指定されていない場合は、代わりにリンク URL （`pev1`）がディメンション値として使用されます。 リンク名を明示的に指定した場合、最大長は100 バイトになります。 リンク URLから派生した値は、この制限の対象ではありません。

AppMeasurementを使用してこのディメンションにデータを入力するには、リンクタイプ引数`"e"`を指定して[`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。 リンク名引数を目的の値に設定します。

```js
s.tl(true,"e","Example exit link");
```

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。 レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。 リンク名が指定されていない場合、ディメンション項目は代わりに生のURLとして表示されます。 これらの生のURLは、レポートで解釈するのが難しいため、可能な限り記述的なリンク名を指定します。
