---
title: 検索
description: ヒットが外部検索条件に一致した回数。
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 88%

---

# 検索

「検索」指標[指標](overview.md)は、Adobeの外部検索検出結果に一致するヒット数を示します。 この指標は、非検索ディメンション項目を調べて、それらが検索エンジントラフィックにどのように貢献したかを確認する場合に役立ちます。

## この指標の計算方法

この指標では、アドビの外部検索検出に一致するヒット数をカウントします。 次の両方と一致する必要があります。

* ヒットのリファラー値は、アドビが認識する検索ドメインです
* ヒットの参照 URL には、キーワードクエリ文字列パラメーターが含まれています。 最新のプライバシー慣行により、このクエリ文字列の値は一般的に空白です。 アドビでは、検索検出の一部として空白のキーワードクエリ文字列を認識します。
