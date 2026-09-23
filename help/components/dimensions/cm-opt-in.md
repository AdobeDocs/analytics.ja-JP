---
title: 同意管理のオプトイン
description: 訪問者がオプトインしたプライバシー設定を確認します。
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 78%
---
# 同意管理のオプトイン

「同意管理オプトイン」 [ ディメンション ](overview.md)には、訪問者がオプトインしたプライバシー設定が表示されます。 このディメンションを使用して、プライバシー設定に基づいてデータをフィルタリングしたり、最も一般的なプライバシーオプトインの理由を確認したりできます。

## このディメンションへのデータ入力

このディメンションは、次の[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)からデータを収集します。

* `Y` に設定されている場合は `contextData.['opt.dmp']`。 `opt.dmp` が `N` に等しい場合、代わりに[同意管理のオプトアウト](cm-opt-out.md)ディメンションが設定されます。
* `Y` に設定されている場合は `contextData.['opt.sell']`。 `opt.sell` が `N` に等しい場合、代わりに[同意管理のオプトアウト](cm-opt-out.md)ディメンションが設定されます。

これらのコンテキストデータ変数を実装するためのロジックは、お客様の組織が決定します。 各ページで各コンテキストデータ変数を設定します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（同意シグナルで設定） |
| **Web SDK / XDM フィールド** | なし |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

ディメンション項目には、次の 2 つの値が含まれます。

* **`DMP`**：訪問者がデータ管理プラットフォームへの共有をオプトインした。 このディメンション項目は、コンテキストデータ変数 `opt.dmp` が `Y` に等しい場合に存在します。
* **`SELL`**：訪問者がサードパーティへのデータの共有や販売をオプトインした。 このディメンションは、コンテキストデータ変数 `opt.sell` が `Y` に等しい場合に存在します。
