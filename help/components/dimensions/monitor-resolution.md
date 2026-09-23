---
title: モニターの解像度
description: 訪問者のモニターの解像度（ピクセル単位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 51%
---
# モニターの解像度

「モニター解像度」 [ ディメンション ](overview.md)は、アクティブなディスプレイの高さと幅をピクセル単位で示します。 このディメンションは、訪問者がサイト上で「折りたたむ」場所や、訪問者のブラウザーウィンドウの幅を把握したい場合に役立ちます。 折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

このディメンションは、ブラウザー[height](browser-height.md)および[width](browser-width.md)とは異なります。 ブラウザーの高さと幅は、表示可能なブラウザースペース内のピクセル数です。モニターの解像度は、モニター全体のピクセル数です。 ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

ブラウザーのサイズにはブラウザーのナビゲーションやボーダーが含まれないので、ブラウザーのサイズは常にモニターの解像度よりも小さくなります。

## このディメンションへのデータ入力

モニターの解像度は、ブラウザーの`screen.width`および`screen.height` プロパティからクライアント側で自動的に収集されます。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。 AppMeasurementまたはWeb SDK以外（API経由など）でデータを収集する場合は、イメージリクエストで値を送信します。 データ収集ライブラリが見つからない場合、または他の方法でモニターの解決を収集できない場合、そのデータは[!UICONTROL `Not Specified`]の下に一覧表示されます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | なし（自動収集） |
| **クエリパラメーター** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 20 バイト |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、収集されたすべてのモニター解像度が含まれます。 例えば、`1920 x 1080`、`1366 x 768`、`1280 x 720` などの値があります。
