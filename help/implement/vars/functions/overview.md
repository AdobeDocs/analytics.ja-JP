---
title: 関数とメソッド
description: アドビが提供する関数とメソッドを実装で使用する方法について説明します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 100%

---


# 関数とメソッド

アドビのオファーは、実装で使用できる複数の機能とメソッドを提供します。これらの関数やメソッドを参照すると、1 行のコードで一般的なタスクが実行されます。

これらの 1 行のコードは、次のカテゴリに分類されます。

* **トラッキングコール**：最も一般的なメソッドであり、多くの実装で不可欠です。[`t()`](t-method.md) メソッドおよび [`tl()`](tl-method.md) メソッドが含まれます。
* **AppMeasurement ユーティリティ**：以前のバージョンの AppMeasurement でこれらのタスクを実行するには、独自のコードを作成する必要がありました。アドビでは、これらの一般的なタスクを合理化する次のユーティリティ方法を提供しています。AppMeasurement ユーティリティには、[`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) および [`Util.getQueryParam()`](util-getqueryparam.md) が含まれます。
* **関数を登録**：独自の関数を作成し、アドビへのトラッキングコールの送信前または送信後に、AppMeasurement で自動的に関数を実行することができます。このカテゴリに該当する変数は、[`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) および [`registerPostTrackCallback()`](registerposttrackcallback.md) です。
