---
title: ブラウザーの高さ（バケット分割）
description: ブラウザーウィンドウの高さをピクセル単位で示します。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
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
source-wordcount: '318'
ht-degree: 40%
---
# ブラウザーの高さ

「ブラウザーの高さ – バケット化された」ディメンション [&#x200B; ディメンション &#x200B;](overview.md)には、ブラウザーのウィンドウの高さが表示され、定義済みのグループに分類されます。 このディメンションは、訪問者にとってサイト上の「折り目」（スクロールせずに見える範囲の下端）がどこにあるかを把握したい場合に役立ちます。 折りたたみの位置を把握することで、コンテンツを表示用に最適化できます。

画面の高さとは異なります。 ブラウザーの高さは、表示可能なブラウザー空間内のピクセル数です。画面の高さは、モニター全体の高さ（ピクセル単位）です。 ご使用のマシン上でこれら 2 つの変数の違いを確認したい場合は、ブラウザーコンソールを開き（ほとんどのブラウザーでは F12）、次のコードをコピーしてコンソールに貼り付けます。

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

ブラウザーの高さはブラウザーのナビゲーションや境界線が含まれていないため、ブラウザーの高さは通常、画面の高さ以下です。

>[!NOTE]
>
>Data Warehouseでは、値を定義済みのバケットにグループ化する代わりに、正確なピクセル高さをレポートする&#39;[!UICONTROL &#x200B; ブラウザーの高さ – 詳細]&#39;ディメンションも提供されています。

## このディメンションへのデータ入力

ブラウザーの高さは、ブラウザーの`window.innerHeight` プロパティからクライアントサイドで自動的に収集されます。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。 AppMeasurementやWeb SDK以外（API経由など）でデータを収集する場合は、各訪問の最初のヒット時に値を送信します。 訪問中にブラウザーの高さが調整されている場合、調整は記録されません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | なし（自動収集） |
| **クエリパラメーター** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **値範囲** | 0-65,535 |
| **永続性** | 訪問 |

## ディメンション項目

Dimensionの項目には、収集されたすべてのブラウザーの高さが含まれ、定義済みのグループに分類されます。 例えば、ヒットのブラウザーの高さが `720` ある場合、そのヒットは `700 to 799` ディメンション項目にグループ化されます。
