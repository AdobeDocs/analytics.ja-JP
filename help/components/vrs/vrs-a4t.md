---
description: A4T と Adobe Analytics の仮想レポートスイートを使用する際の特別な考慮事項
title: 仮想レポートスイートと Analytics for Target（A4T）
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---

# 仮想レポートスイートと Analytics for Target（A4T）

Adobe Target のコンテキストで仮想レポートスイートを使用する場合は、次の点に注意してください。

* Target から仮想レポートスイートに直接データを送信することはできず、実際のレポートスイートにのみ送信できます。
* 仮想レポートスイート内の A4T アクティビティをレポートできます。 ただし、A4T データは、仮想レポートスイートセグメント（および適用された他のセグメント）に一致する行に制限されます。 例えば、EMEA の顧客向けに仮想レポートスイートを作成した場合、その仮想レポートスイートの A4T データには、EMEA の顧客向けの Target データのみが反映されます。
* アクティブ化のために仮想レポートスイートから Target にセグメントを公開することはできません。
