---
description: 'A4TとAdobe Analyticsの仮想レポートスイートを使用する際の特別な考慮事項 '
title: 仮想レポートスイートとAnalytics for Target(A4T)
source-git-commit: 6a47ebc58cb36079940cfc4e5cdc80cf99c18a50
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# 仮想レポートスイートとAnalytics for Target(A4T)

Adobe Targetのコンテキストで仮想レポートスイートを使用する場合は、次の点に注意してください。

* Targetから仮想レポートスイートに直接データを送信することはできず、実際のレポートスイートにのみ送信できます。
* 仮想レポートスイート内のA4Tアクティビティをレポートできます。 ただし、A4Tデータは、仮想レポートスイートセグメント（および適用された他のセグメント）に一致する行に制限されます。 例えば、EMEAのお客様向けに仮想レポートスイートを作成した場合、その仮想レポートスイートのA4Tデータには、EMEAのお客様向けのTargetデータのみが反映されます。
* アクティブ化のために仮想レポートスイートからTargetにセグメントを公開することはできません。