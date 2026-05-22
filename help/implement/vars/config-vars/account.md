---
title: account
description: （退職済み）データの送信先となるレポートスイートを決定します。
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ICQkj-Eo29jve35GewuZUKOPIr01g-WjhbyztrAO0jI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>この変数は廃止されています。 実装でレポートスイートの宛先を変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) 関数を使用します。

以前のバージョンの Adobe Analytics では、`account` 変数はデータの送信先のレポートスイートを決定しました。 Adobe Analytics にデータを送信するには、レポートスイート ID が必要です。

* Web SDKを使用する場合、レポートスイートは、Web SDKがデータを送信するデータストリーム内のAdobe Analytics サービス設定にあります。
* Adobe Analytics拡張機能を使用する場合は、Adobe Analytics拡張機能を設定する際に、[!UICONTROL Library Management] アコーディオンの下にレポートスイートが存在します。
* [`s_gi()`](../functions/s-gi.md)関数を使用してAnalytics トラッキングオブジェクトをインスタンス化する場合、レポートスイート IDは既に関数の必須の引数として存在します。
