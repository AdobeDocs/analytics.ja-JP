---
title: リロード回数
description: ページがリロードされた回数。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 21%

---

# リロード回数

「リロード」 [指標](overview.md)は、リロード中にディメンション項目が存在した回数を示します。 訪問者によるブラウザーの更新は、再読み込みをトリガーする最も一般的な方法です。

## この指標の計算方法

この指標は、[ ページ ](../dimensions/page.md) ディメンションに前のヒットと同じ値が含まれるヒット数をカウントします。

リロードの概念は、レポートで使用するディメンションに関係なく、ページディメンションに適用されます。 例えば、[eVar1](../dimensions/evar.md)をディメンションとして使用し、リロードを指標として使用する場合、リロード中に各eVar値が存在した回数（連続した2つのページ値）がテーブルに表示されます。 これは、連続した2つのeVar1値が存在した回数を示すものではありません。
