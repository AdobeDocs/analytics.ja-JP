---
title: 関数とメソッド
description: アドビが提供する関数とメソッドを実装で使用する方法について説明します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 関数とメソッド

アドビオファーは、実装で使用できるいくつかの機能とメソッドを提供します。 これらの関数やメソッドを参照すると、1行のコードで一般的なタスクが実行されます。

これらの1行のコードの一部は、次のカテゴリに属します。

* **コールの追跡**:最も一般的なメソッドで、多くの実装で不可欠です。 メソッドとメソッド [`t()`](t-method.md) が含ま [`tl()`](tl-method.md) れます。
* **AppMeasurementユーティリティ**:以前のバージョンのAppMeasurementでは、これらの機能を実行するには独自のコードを作成する必要がありましたが、タスクは アドビでは、これらの一般的な方法を合理化するための次のユーティリティタスクを提供します。 AppMeasurementユーティリティには、、、 [`Util.cookieRead()`](util-cookieread.md)および [`Util.cookieWrite()`](util-cookiewrite.md)が含まれま [`Util.getQueryParam()`](util-getqueryparam.md)す。
* **関数の登録**:独自の関数を作成し、アドビにトラッキングコールを送信する前または送信した後に、AppMeasurementで自動的に関数を実行することができます。 この変数に該当する変数は、、お [`doPlugins()`](doplugins.md)よびと [`registerPreTrackCallback()`](registerpretrackcallback.md)なります [`registerPostTrackCallback()`](registerposttrackcallback.md)。
