---
title: ダウンロードリンク
description: ダウンロードリンクの名前。
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
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
source-wordcount: '268'
ht-degree: 27%
---
# ダウンロードリンク

「ダウンロードリンク」 [&#x200B; ディメンション &#x200B;](overview.md)は、サイトに実装されたダウンロードリンクの名前を報告します。 このディメンションは、次のようなダウンロードリンクに関する訪問者行動を詳しく知りたい場合に役立ちます。

* サイトから最も頻繁にダウンロードされるファイル。
* 特定の期間に特定のファイルをより頻繁にダウンロードするかどうか。
* 訪問者が提供されたときに異なるファイルタイプをダウンロードするかどうか。

## このディメンションへのデータ入力

このディメンションには、[&#x200B; リンクトラッキング呼び出し（`tl()`） &#x200B;](/help/implement/vars/functions/tl-method.md)が入力されています。 設定できる専用の変数はありません。 代わりに、リンクタイプ引数`"d"`を持つ`tl()`画像リクエストを送信し、リンク名引数を目的の値に設定します。 `pe` クエリ文字列は、リンク名を正しいリンクディメンション （[&#x200B; カスタムリンク &#x200B;](custom-link.md)の`lnk_o`、[&#x200B; ダウンロードリンク &#x200B;](download-link.md)の`lnk_d`、[終了リンク &#x200B;](exit-link.md)の`lnk_e`）にルーティングします。 リンク名が指定されていない場合、代わりにリンク URLがディメンション値として使用され、URL派生値はバイト制限の対象にはなりません。

```js
s.tl(true,"d","Example download link");
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
