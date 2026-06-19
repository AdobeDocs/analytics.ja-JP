---
title: ブラウザーの幅 - グループ
description: ブラウザーウィンドウの幅をピクセルで指定します。
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 75%

---

# ブラウザーの幅

「Browser width - bucketed&#39; [dimension](overview.md)」には、ブラウザーウィンドウの幅が表示され、定義済みのグループに分類されます。 このディメンションは、訪問者がコンテンツをどの程度広い範囲で閲覧しているかを把握する場合に役立ちます。 通常、コンテンツが表示される幅を把握することで、そのコンテンツを最適化できます。

このサイズは画面の幅とは異なります。 ブラウザーの幅は、表示可能なブラウザースペース内のピクセル数です。画面の幅は、モニター全体の幅（ピクセル単位）です。 ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

ブラウザーの幅はスクロールバーや境界線を含まないので、常に画面の幅以下になります。

>[!NOTE]
>
>Data Warehouseでは、値を定義済みのバケットにグループ化する代わりに、正確なピクセル幅をレポートする&#39;[!UICONTROL  ブラウザー幅 – 詳細]&#39; ディメンションも提供されています。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`bw`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、ブラウザーの JavaScript `window.innerWidth` 変数を使用してこのデータを収集します。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、各訪問の最初のヒットに `bw` クエリ文字列パラメーターを必ず含めてください。

1 回の訪問でのブラウザーの幅は維持されます。 訪問中にブラウザーの幅を調整した場合、調整は記録されません。

## ディメンション項目

Dimensionの項目には、収集されたすべてのブラウザー幅が含まれ、定義済みのグループに分類されます。 例えば、ヒットのブラウザーの幅が `1280` ある場合、ディメンション項目 `1200 to 1299` にグループ化されます。
