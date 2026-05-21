---
title: 関数とメソッド
description: アドビが提供する関数とメソッドを実装で使用する方法について説明します。
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# 関数とメソッド

アドビのオファーは、実装で使用できる複数の機能とメソッドを提供します。 これらの関数やメソッドを参照すると、1 行のコードで一般的なタスクが実行されます。

これらの 1 行のコードは、次のカテゴリに分類されます。

* **トラッキングコール**：最も一般的なメソッドであり、多くの実装で不可欠です。 [`t()`](t-method.md) メソッドおよび [`tl()`](tl-method.md) メソッドが含まれます。
* **AppMeasurement ユーティリティ**：以前のバージョンの AppMeasurement でこれらのタスクを実行するには、独自のコードを作成する必要がありました。 アドビでは、これらの一般的なタスクを合理化する次のユーティリティ方法を提供しています。 AppMeasurement ユーティリティには、[`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) および [`Util.getQueryParam()`](util-getqueryparam.md) が含まれます。
* **関数を登録**：独自の関数を作成し、アドビへのトラッキングコールの送信前または送信後に、AppMeasurement で自動的に関数を実行することができます。 このカテゴリに該当する変数は、[`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) および [`registerPostTrackCallback()`](registerposttrackcallback.md) です。
