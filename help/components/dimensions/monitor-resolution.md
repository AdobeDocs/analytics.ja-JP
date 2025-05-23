---
title: 画面の解像度
description: 訪問者のモニターの解像度（ピクセル単位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e3a1c1fde3809cb73b1bda091b8be43778515d1a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 72%

---

# 画面の解像度

「画面の解像度 [ ディメンション ](overview.md) は、アクティブなディスプレイの高さと幅をピクセル単位で示します。 このディメンションは、訪問者がサイト上で「折りたたむ」場所や、訪問者のブラウザーウィンドウの幅を把握したい場合に役立ちます。折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

この寸法は、ブラウザー [ 高さ ](browser-height.md) および [ 幅 ](browser-width.md) とは異なります。 ブラウザーの高さと幅は、表示可能なブラウザースペース内のピクセル数です。モニターの解像度は、モニター全体のピクセル数です。ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

ブラウザーのサイズにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーのサイズは、常にモニターの解像度よりも小さくなります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`s`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `screen.width` および `screen.height` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

AppMeasurement以外の（API 経由などの）データ収集方式を使用する場合は、イメージリクエストに `s` クエリ文字列パラメーターを必ず含めてください。 `s` クエリ文字列が見つからない場合、またはデータ収集ライブラリが見つからない場合、モニターの解像度を収集できない場合、そのデータは [!UICONTROL `Not Specified`] の下に表示されます。

## ディメンション項目

ディメンション項目には、収集されたすべての画面解像度が含まれます。例えば、`1920 x 1080`、`1366 x 768`、`1280 x 720` などの値があります。
