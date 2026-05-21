---
description: マクロが有効なワークブックのスケジュール設定について説明します。
title: マクロ対応ワークブックのスケジュール設定について
uuid: 874cfac8-ca63-4dec-b2aa-a3dcd037c5c5
feature: Report Builder
role: User, Admin
exl-id: 34b8ffc7-646a-4472-a99a-4b8876ea7b16
TQID: https://experienceleague.adobe.com/9LFw7NCIWaFALUD5TfCMiv2x3H7VkXf6zB4J8jyt1fk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 33%

---

# マクロが有効なワークブックのスケジュール

{{legacy-arb}}

Adobe Report Builder でマクロが設定された .xlsm 形式のワークブックをスケジュール配信できるようになりました。

これは、マクロ対応ワークブックを安全にスケジュール、処理、受信する必要がある場合に便利です。

>[!IMPORTANT]
>
>Report Builder では、マクロ付きのワークブックをスケジュールできますが、これらのマクロは配信前の更新時には実行されません。 これは、ネイティブのMicrosoft Excel アプリケーション内でブックを開いた場合にのみ実行されます。

マクロを含むスケジュールされたワークブックは、マクロが有効な形式（.xlsm）でのみ配信できます。他のすべてのサポートされている形式（xls、xlsx、pdf、word、csv、txt）では、ワークブックからマクロが削除されるからです。
