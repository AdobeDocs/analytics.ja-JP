---
title: 画面の解像度
description: 訪問者のモニターの解像度（ピクセル単位）。
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# 画面の解像度

&#39;画面の解像度&#39;の寸法は、アクティブなディスプレイの高さと幅をピクセル単位で表示します。 このディメンションは、訪問者がサイト上で「折りたたむ」の位置や、訪問者のブラウザーウィンドウの幅を把握したい場合に役立ちます。 フォールドの位置を把握することで、コンテンツを表示用に最適化できます。

この寸法は、ブラウザーの高さおよび幅とは異なります。 ブラウザの高さ/幅は、表示可能なブラウザスペース内のピクセル数です。モニタの解像度は、モニタ全体のピクセル数です。 ご使用のマシン上でこれら2つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーではF12）、次のコードをコピーしてコンソールに貼り付けます。

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

ブラウザーのサイズにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーのサイズは、常にモニターの解像度よりも小さくなります。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`s` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、JavaScript変数を使用してこのデータを収集し、ブラウザ `screen.width` ー `screen.height` でデータを収集します。 （Adobe Experience Platform Launch経由などの）AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外の（API経由などの）データ収集方法を使用する場合は、クエリリクエストに `s` 文字列パラメーターを必ず含めてください。

## 分析コード値

ディメンション値には、収集されたすべてのモニター解像度が含まれます。 例えば、、、 `1920 x 1080`、な `1366 x 768`どの値があり `1280 x 720`ます。
