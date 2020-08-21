---
title: ブラウザーの高さ - グループ
description: ソース画像の高さをピクセルで指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 88%

---


# ブラウザーの高さ

「ブラウザーの高さ — グループ」ディメンションは、ブラウザーウィンドウの高さを 100 ピクセルのグループに分類して表示します。このディメンションは、訪問者がサイト上で「折りたたむ」場所を把握したい場合に役立ちます。折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

この寸法は、画面の高さとは異なります。ブラウザーの高さは、表示可能なブラウザスペース内のピクセル数です。画面の高さは、モニター全体の高さ（ピクセル単位）です。ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

ブラウザーの高さにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーの高さは常に画面の高さ以下になります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`bh`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `window.innerHeight` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、各訪問の最初のヒットに `bh` クエリー文字列パラメーターを必ず含めてください。

1 回の訪問でのブラウザーの高さは維持されます。訪問中にブラウザーの高さを調整した場合、調整は記録されません。

## Dimension項目

Dimension項目には、収集されたすべてのブラウザーの高さが含まれ、100ピクセルのグループに分類されます。 For example, if the browser height of a hit is `720`, then it is grouped in the dimension item `700 to 799`.
