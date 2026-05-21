---
description: オフラインモードを使用してプレースホルダーデータを返す方法を説明します。
title: オフラインモードの有効化
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 12%

---

# リクエストを作成および編集するオフラインモード

{{legacy-arb}}

オフラインモードでは、プレースホルダーデータを返し、リクエストの作成および編集のプロセスにかかる時間を短縮します。

新しいリクエストを作成または編集すると、レポート API呼び出しが行われ、応答が取得されます。 このような呼び出しにより、次の手順に進む前にデータが返されるのを待つ必要があるため、リクエスト作成プロセスが遅くなることがあります。 オフラインモードでは、プレースホルダーデータのみが返され、APIは作成されません。

オフラインモードを有効にするには

1. Report Builder メニューの&#x200B;**[!UICONTROL Options]**&#x200B;をクリックします。

   オフラインコードが選択されたオプション画面の![&#x200B; スクリーンショット。](assets/offline_mode.png)

1. 「**[!UICONTROL オフラインモードを有効にしてリクエストを作成および編集する]**」の横にあるチェックボックスをオンにします。
1. **[!UICONTROL 指標データを]**&#x200B;として表示フィールドに、リクエストで返すプレースホルダーデータを入力します。 例えば、「1」と入力します。
1. 「**[!UICONTROL OK]**」をクリックします。
1. リクエストウィザードを使用して、オフラインモードでリクエストを作成して実行します。 次のスクリーンショットは、「1」をプレースホルダーデータとするリクエストの例を示しています。

   ![&#x200B; プレースホルダーとして1を使用したオフラインモードの例を示すスクリーンショット。](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >実際のデータでリクエストを実行する前に、オフラインモードを無効にしていることを確認してください。
