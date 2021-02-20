---
title: 画面の解像度
description: 訪問者のモニターの解像度（ピクセル単位）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---


# 画面の解像度

「画面の解像度&#39;」ディメンションは、アクティブなディスプレイの高さと幅をピクセル単位で表示します。このディメンションは、訪問者がサイト上で「折りたたむ」場所や、訪問者のブラウザーウィンドウの幅を把握したい場合に役立ちます。折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

このディメンションは、ブラウザーの高さおよび幅とは異なります。ブラウザーの高さと幅は、表示可能なブラウザースペース内のピクセル数です。モニターの解像度は、モニター全体のピクセル数です。ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

ブラウザーのサイズにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーのサイズは、常にモニターの解像度よりも小さくなります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`s`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `screen.width` および `screen.height` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、クエリリクエストに `s` 文字列パラメーターを必ず含めてください。

## ディメンション項目

ディメンション項目には、収集されたすべての画面解像度が含まれます。例えば、`1920 x 1080`、`1366 x 768`、`1280 x 720` などの値があります。
