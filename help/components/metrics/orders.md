---
title: 注文件数
description: おこなわれた購入の数。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
TQID: https://experienceleague.adobe.com/jRd-oUTfcJXACj-mkEyzRm8k-rxcVCxe7U3lROIy7DQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 90
ht-degree: 65%

---

# 注文件数

「注文」 [指標](overview.md)は、サイトで実行された購入イベントの合計数を示します。 この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。 この指標を任意のディメンションと組み合わせると、どのディメンション項目が注文に貢献したかを確認できます。 例えば、（[追跡コード](../dimensions/tracking-code.md)ディメンションを使用して）トップキャンペーンまたは（[eVar](../dimensions/evar.md) を使用して）購入に貢献したトップ内部検索語を確認できます。

## この指標の計算方法

この指標は、`purchase` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒット数をカウントします。
