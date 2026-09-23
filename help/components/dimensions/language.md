---
title: 言語
description: ブラウザーの優先言語設定
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 65%
---
# 言語

「言語」 [&#x200B; ディメンション &#x200B;](overview.md)には、訪問者がコンテンツを見たいと思う上位の言語が表示されます。 このディメンションは、ローカライゼーションの取り組みに役立つ、訪問者の最も頻繁に使用する言語を理解したい場合に役立ちます。

>[!NOTE]
>
>このディメンションは、サイトの言語を収集しません。 ディメンションでサイトの言語を収集する場合、[eVar](evar.md) などのカスタム変数を使用することをお勧めします。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `Accept-Language` HTTP ヘッダーに基づきます。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（HTTP ヘッダー） |
| **Web SDK / XDM フィールド** | なし（HTTP ヘッダー） |
| **クエリパラメーター** | なし（`Accept-Language` ヘッダーを使用） |
| **XML タグ** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、訪問者の優先言語のわかりやすい名前が含まれます。 例として、`"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"`、`"Spanish (Spain)"` があります。 イメージリクエストの HTTP ヘッダーに有効な言語が含まれていない場合、ディメンション項目は `"None"` です。
