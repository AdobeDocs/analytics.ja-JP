---
title: 言語
description: ブラウザーの優先言語設定。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 100%

---

# 言語

「言語」ディメンションは、訪問者がコンテンツの表示を好む上位の言語を示します。このディメンションは、ローカライゼーションの取り組みに役立つ、訪問者の最も頻繁に使用する言語を理解したい場合に役立ちます。

>[!NOTE]
>
>このディメンションは、サイトの言語を収集しません。ディメンションでサイトの言語を収集する場合、[eVar](evar.md) などのカスタム変数を使用することをお勧めします。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `Accept-Language` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、訪問者の優先言語のわかりやすい名前が含まれます。例として、`"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"`、`"Spanish (Spain)"` があります。イメージリクエストの HTTP ヘッダーに有効な言語が含まれていない場合、ディメンション項目は `"None"` です。
