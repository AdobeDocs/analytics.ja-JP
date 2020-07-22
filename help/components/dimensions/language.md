---
title: 言語
description: ブラウザーでの優先言語設定。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 言語

「言語」ディメンションは、訪問者がコンテンツの表示を好む上位の言語を示します。 このディメンションは、ローカライゼーションの取り組みに役立つ、訪問者の最も頻繁に使用する言語を理解したい場合に役立ちます。

>[!NOTE]
>
>このディメンションは、サイトの言語を収集しません。 ディメンションでサイトの言語を収集する場合、eVarなどのカスタム変数を使用することをお勧めし [ます](evar.md)。

## このディメンションにデータを入力する

このディメンションは、Adobe内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `Accept-Language` HTTPヘッダーに基づきます。 (Adobe Experience Platform起動を介したなどの)AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、訪問者の優先言語のわかりやすい名前が含まれます。 Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. イメージリクエストがHTTPヘッダーに有効な言語を含まない場合、ディメンション項目はで `"None"`す。
