---
title: 離脱リンク
description: 離脱リンクの名前。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 22%
---
# 離脱リンク

「離脱リンク」 [ ディメンション ](overview.md)は、サイトに実装された離脱リンクの名前を報告します。 離脱リンク現在のドメインから訪問者を離れるアウトバウンドクリックを追跡します。 このディメンションは、最も頻繁にクリックされるアウトバウンドリンクを把握したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションには、[ リンクトラッキング呼び出し（`tl()`） ](/help/implement/vars/functions/tl-method.md)が入力されています。 設定できる専用の変数はありません。 代わりに、リンクタイプ引数`"e"`を持つ`tl()`画像リクエストを送信し、リンク名引数を目的の値に設定します。 `pe` クエリ文字列は、リンク名を正しいリンクディメンション （[ カスタムリンク ](custom-link.md)の`lnk_o`、[ ダウンロードリンク ](download-link.md)の`lnk_d`、[終了リンク ](exit-link.md)の`lnk_e`）にルーティングします。 リンク名が指定されていない場合、代わりにリンク URLがディメンション値として使用され、URL派生値はバイト制限の対象にはなりません。

```js
s.tl(true,"e","Example exit link");
```

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Web SDK / XDM フィールド** | なし |
| **クエリパラメーター** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

この変数は、実装のカスタム文字列に基づいているため、どのディメンション項目にするかは組織側で決定します。 レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。 リンク名が指定されていない場合、ディメンション項目は代わりに生のURLとして表示されます。 これらの生のURLは、レポートで解釈するのが難しいため、可能な限り記述的なリンク名を指定します。
