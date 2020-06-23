---
title: dc
description: 使用するデータセンターを決定できる古い変数。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# dc

>[!IMPORTANT] この変数は廃止されています。代わりに、[`trackingServer`](trackingserver.md) を使用してください。

以前のバージョンの Adobe Analytics では、データの送信先のデータセンターを指定する必要がありました。ヒットを誤ったデータセンターに送信すると、データが失われていました。

アドビは、任意の実装で `sc.omtrdc.net` へのヒットの送信を許可することで、このエクスペリエンスを向上させました。データセンターの指定は不要になりました。
