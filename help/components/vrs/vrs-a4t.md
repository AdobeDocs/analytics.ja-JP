---
description: A4T と Adobe Analytics の仮想レポートスイートを使用する際の特別な考慮事項
title: 仮想レポートスイートと Analytics for Target（A4T）
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: 'https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%
---
# 仮想レポートスイートと Analytics for Target（A4T）

Adobe Target のコンテキストで仮想レポートスイートを使用する場合は、次の点に注意してください。

* Target から仮想レポートスイートに直接データを送信することはできず、実際のレポートスイートにのみデータを送信できます。
* 仮想レポートスイート内の A4T アクティビティについてレポートを作成できます。 ただし、A4T データは、仮想レポートスイートセグメント（および適用された他のセグメント）に一致する行に制限されます。 例えば、EMEA の顧客向けに仮想レポートスイートを作成した場合、その仮想レポートスイートの A4T データには、EMEA の顧客向けの Target データのみが反映されます。
* アクティブ化のために仮想レポートスイートから Target にセグメントを公開することはできません。
