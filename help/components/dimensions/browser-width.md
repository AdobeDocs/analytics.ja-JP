---
title: ブラウザーの幅 - グループ
description: ブラウザーウィンドウの幅をピクセルで指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 88%

---


# ブラウザーの幅

「ブラウザーの幅 — グループ」ディメンションは、ブラウザーウィンドウの幅を 100 ピクセルのグループに分類して表示します。このディメンションは、訪問者がコンテンツをどの程度広い範囲で閲覧しているかを把握する場合に役立ちます。コンテンツの一般的な表示幅を把握することで、コンテンツを最適化して表示できます。

このディメンションは画面の幅とは異なります。ブラウザーの幅は、表示可能なブラウザースペース内のピクセル数です。画面の幅は、モニター全体の幅（ピクセル単位）です。ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

ブラウザーの幅はスクロールバーや境界線を含まないので、常に画面の幅以下になります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`bw`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `window.innerWidth` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、各訪問の最初のヒットに `bw` クエリー文字列パラメーターを必ず含めてください。

1 回の訪問でのブラウザーの幅は維持されます。訪問中にブラウザーの幅を調整した場合、調整は記録されません。

## Dimension項目

Dimension項目には、収集されたすべてのブラウザーの幅が含まれ、100ピクセルのグループに分類されます。 For example, if the browser width of a hit is `1280`, then it is grouped in the dimension item `1200 to 1299`.
