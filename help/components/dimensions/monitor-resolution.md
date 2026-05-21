---
title: 画面の解像度
description: 訪問者のモニターの解像度（ピクセル単位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 82%

---

# 画面の解像度

「モニター解像度」 [ ディメンション ](overview.md)は、アクティブなディスプレイの高さと幅をピクセル単位で示します。 このディメンションは、訪問者がサイト上で「折りたたむ」場所や、訪問者のブラウザーウィンドウの幅を把握したい場合に役立ちます。 折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

このディメンションは、ブラウザー[height](browser-height.md)および[width](browser-width.md)とは異なります。 ブラウザーの高さと幅は、表示可能なブラウザースペース内のピクセル数です。モニターの解像度は、モニター全体のピクセル数です。 ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

ブラウザーのサイズにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーのサイズは、常にモニターの解像度よりも小さくなります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`s`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、ブラウザーの JavaScript `screen.width` および `screen.height` 変数を使用してこのデータを収集します。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、イメージリクエストに `s` クエリ文字列パラメーターを必ず含めてください。 `s` クエリ文字列が見つからないか、データ収集ライブラリがモニター解決を収集できない場合、そのデータは[!UICONTROL `Not Specified`]に一覧表示されます。

## ディメンション項目

ディメンション項目には、収集されたすべての画面解像度が含まれます。 例えば、`1920 x 1080`、`1366 x 768`、`1280 x 720` などの値があります。
