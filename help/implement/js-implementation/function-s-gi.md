---
description: s_gi() 関数は、レポートスイート ID を使用して AppMeasurement のインスタンスを作成したり、検索したりする際に使用します。AppMeasurement は作成されるすべてのインスタンスを内部で追跡しており、s_gi() はレポートスイートに対応する既存のインスタンスがある場合にそれを返します。インスタンスが存在しなければ、新しいインスタンスが作成されて返されます。
keywords: Analytics の実装
seo-description: s_gi() 関数は、レポートスイート ID を使用して AppMeasurement のインスタンスを作成したり、検索したりする際に使用します。AppMeasurement は作成されるすべてのインスタンスを内部で追跡しており、s_gi() はレポートスイートに対応する既存のインスタンスがある場合にそれを返します。インスタンスが存在しなければ、新しいインスタンスが作成されて返されます。
seo-title: s_gi() 関数
solution: Analytics
title: s_gi() 関数
topic: 開発者と実装
uuid: a77de90e-c60e-4946-90cf-loam8aa3d755
translation-type: tm+mt
source-git-commit: 506c670e4b2903cc71bb6880cd74c3392bbc751c

---


# s_gi() 関数

s_gi() 関数は、レポートスイート ID を使用して AppMeasurement のインスタンスを作成したり、検索したりする際に使用します。AppMeasurement は作成されるすべてのインスタンスを内部で追跡しており、s_gi() はレポートスイートに対応する既存のインスタンスがある場合にそれを返します。インスタンスが存在しなければ、新しいインスタンスが作成されて返されます。

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. そうすることで、s 変数が誤って上書きされていた場合でも正しいオブジェクトを使用してトラッキングコールを実行することができます。

## 複数のレポートスイートの使用 {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

返されるオブジェクトは、渡されるレポートスイート ID に応じて変わります。例えば、最初に `s_gi()` () を以下のように呼び出すとします。

```
var s=s_gi('rsid1,rsid2')
```

以降の呼び出しで返されるオブジェクトを、以下の表に示します。

| **s_gi の以降の呼び出し** | **返されるオブジェクトの説明** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | 前に参照されたものと同じオブジェクト。 |
| `s=s_gi('rsid1')` | 前に作成されたオブジェクトのコピー（オリジナルではありません）。 |
| `s=s_gi('rsid1,rsid3')` | 前に作成されたオブジェクトのコピー（オリジナルではありません）。 |
| `s=s_gi('rsid3')` | 設定変数が設定されていない、新しい空のオブジェクト（例：linkTrackVars、linkDownloadFileTypes は空です）。 |
