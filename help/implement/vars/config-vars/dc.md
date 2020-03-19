---
title: dc
description: 使用するデータセンターを決定できる廃止された変数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# dc

> [!IMPORTANT] この変数は廃止されます。 代わりに、を [`trackingServer`](trackingserver.md) 使用します。

以前のバージョンのAdobe Analyticsでは、データの送信先のデータセンターを指定する必要がありました。 ヒットを誤ったデータセンターに送信すると、データが失われていました。

アドビでは、任意の実装でのヒットの送信先となるので、このエクスペリエンスを改善しま `sc.omtrdc.net`した。 データセンターの指定は不要になりました。
