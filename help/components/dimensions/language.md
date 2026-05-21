---
title: 言語
description: ブラウザーの優先言語設定。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 91%

---

# 言語

「言語」 [ ディメンション ](overview.md)には、訪問者がコンテンツを見たいと思う上位の言語が表示されます。 このディメンションは、ローカライゼーションの取り組みに役立つ、訪問者の最も頻繁に使用する言語を理解したい場合に役立ちます。

>[!NOTE]
>
>このディメンションは、サイトの言語を収集しません。 ディメンションでサイトの言語を収集する場合、[eVar](evar.md) などのカスタム変数を使用することをお勧めします。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `Accept-Language` HTTP ヘッダーに基づきます。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、訪問者の優先言語のわかりやすい名前が含まれます。 例として、`"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"`、`"Spanish (Spain)"` があります。 イメージリクエストの HTTP ヘッダーに有効な言語が含まれていない場合、ディメンション項目は `"None"` です。
