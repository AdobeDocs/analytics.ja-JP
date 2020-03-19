---
title: 関数とメソッド
description: 導入時にアドビが提供する機能とメソッドを使用する方法を説明します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 関数とメソッド

アドビでは、実装で使用できるいくつかの機能と方法を提供しています。 これらの関数やメソッドを参照する場合、1行のコードで一般的なタスクを実行します。

これらの1行のコードの一部は、次のカテゴリに属します。

* **コールの追跡**:最も一般的なメソッドで、多くの実装で不可欠です。 メソッドとメソッド [`t()`](t-method.md) が含ま [`tl()`](tl-method.md) れます。
* **AppMeasurementユーティリティ**:以前のバージョンのAppMeasurementでは、これらのタスクを実行するには、実装で独自のコードを作成する必要がありました。 アドビでは、これらの一般的なタスクを合理化するための次のユーティリティメソッドを提供しています。 AppMeasurementユーティリティには、、、 [`Util.cookieRead()`](util-cookieread.md)および [`Util.cookieWrite()`](util-cookiewrite.md)が含まれま [`Util.getQueryParam()`](util-getqueryparam.md)す。
* **関数の登録**:独自の関数を作成し、アドビにトラッキングコールを送信する前または送信した後に、AppMeasurementで自動的に関数を実行することができます。 このカテゴリに該当する変数は、、お [`doPlugins()`](doplugins.md)よび [`registerPreTrackCallback()`](registerpretrackcallback.md)です [`registerPostTrackCallback()`](registerposttrackcallback.md)。
