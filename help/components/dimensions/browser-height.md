---
title: ブラウザーの高さ - グループ
description: ソース画像の高さをピクセルで指定します。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 87%

---

# ブラウザーの高さ

「ブラウザーの高さ – バケット化された」ディメンション [&#x200B; ディメンション &#x200B;](overview.md)には、ブラウザーのウィンドウの高さが表示され、定義済みのグループに分類されます。 このディメンションは、訪問者がサイト上で「折りたたむ」場所を把握したい場合に役立ちます。 折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

画面の高さとは異なります。 ブラウザーの高さは、表示可能なブラウザスペース内のピクセル数です。画面の高さは、モニター全体の高さ（ピクセル単位）です。 ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

ブラウザーの高さにはブラウザーのナビゲーションや境界線が含まれないので、ブラウザーの高さは常に画面の高さ以下になります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`bh`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、ブラウザーの JavaScript `window.innerHeight` 変数を使用してこのデータを収集します。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、各訪問の最初のヒットに `bh` クエリ文字列パラメーターを必ず含めてください。

1 回の訪問でのブラウザーの高さは維持されます。 訪問中にブラウザーの高さを調整した場合、調整は記録されません。

## ディメンション項目

Dimensionの項目には、収集されたすべてのブラウザーの高さが含まれ、定義済みのグループに分類されます。 例えば、ヒットのブラウザーの高さが `720` ある場合、そのヒットは `700 to 799` ディメンション項目にグループ化されます。
