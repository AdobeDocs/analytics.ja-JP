---
title: 言語
description: ブラウザーの優先言語設定。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---


# 言語

「言語」ディメンションは、訪問者がコンテンツの表示を好む上位の言語を示します。このディメンションは、ローカライゼーションの取り組みに役立つ、訪問者の最も頻繁に使用する言語を理解したい場合に役立ちます。

>[!NOTE]
>
>このディメンションは、サイトの言語を収集しません。ディメンションでサイトの言語を収集する場合、[eVar](evar.md) などのカスタム変数を使用することをお勧めします。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `Accept-Language` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## Dimension項目

Dimension項目には、訪問者の優先言語のわかりやすい名前が含まれます。 例として、`"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"`、`"Spanish (Spain)"` があります。If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
