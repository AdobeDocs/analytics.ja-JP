---
title: dc
description: 使用するデータセンターを決定できる古い変数。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# dc

> [!IMPORTANT] この変数は廃止されます。 代わりに、を `trackingServer` 使用します。

以前のバージョンのAdobe Analyticsでは、データの送信先のデータセンターを指定する必要がありました。 ヒットを誤ったデータセンターに送信すると、データが失われていました。

アドビは、任意の実装でのヒットの送信を許可することで、このエクスペリエンスを向上させま `sc.omtrdc.net`した。 データセンターの指定は不要になりました。
