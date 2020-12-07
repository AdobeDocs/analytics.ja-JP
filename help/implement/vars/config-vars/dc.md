---
title: dc
description: 使用するデータセンターを決定できる古い変数。
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 100%

---


# dc

>[!IMPORTANT]
>
> この変数は廃止されています。代わりに、[`trackingServer`](trackingserver.md) を使用してください。

以前のバージョンの Adobe Analytics では、データの送信先のデータセンターを指定する必要がありました。ヒットを誤ったデータセンターに送信すると、データが失われていました。

アドビは、任意の実装で `sc.adobedc.net` へのヒットの送信を許可することで、このエクスペリエンスを向上させました。データセンターの指定は不要になりました。
