---
description: Data Warehouseからデータを取得する時間を短縮するためのガイドラインを説明します。
keywords: ベストプラクティス；失敗；タイムアウト；トラブルシューティング
title: Data Warehouseのベストプラクティス
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: 'https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 27%

---

# Data Warehouse のベストプラクティス

Data Warehouse は、カスタムレポートを実行するための柔軟なインターフェイスを備えています。 次のガイドラインを使用して、データの取得にかかる時間を短縮します。

| ガイドライン | 説明 |
|--- |--- |
| 要求しているデータ量を把握する | 大規模なレポートスイートに関する複数年のレポートには、数百億行のデータ行を含めることができます。 このようなデータを処理し評価するには、数日から数週間かかる場合があります。 レポートの使用方法を評価して、複数年データの一部が利用可能かどうか、またはレポートを複数のリクエストに分割できるかどうかを判断します。 |
| レポート期間と精度の一致 | レポートの詳細を確認するには、さらに多くの処理時間が必要です。 年間を通じて月単位で詳細なレポートを作成する場合、月単位でレポートリクエストを送信すると、レポートの処理が大幅に高速化します。 |
| 完了したデータ範囲に関するレポート | Data Warehouse レポートは、リクエストされた日付範囲が完了したときに生成されます。 例えば、現在の週のレポートを水曜日にリクエストした場合、レポートは次の週の日曜日にならないと生成されません。 |
| Data Warehouseでのパスレポートの生成 | パス指標（入口、出口、バウンスなど） はデータウェアハウスでは利用できません。 |
| 仮想レポートスイート | バーチャルレポートスイートのData Warehouse レポートでは、バーチャルレポートスイートで設定された代替タイムゾーンがサポートされます。 |

