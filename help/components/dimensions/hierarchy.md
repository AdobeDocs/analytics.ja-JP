---
title: 階層
description: （廃止）レポートで使用できるカスタムディメンション。
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# 階層

>[!IMPORTANT]
>
>このディメンションは廃止され、Analysis Workspaceで使用できる[&#x200B; ディメンション &#x200B;](overview.md)ではありません。 アドビでは、代わりに [eVar](evar.md) と分類を使用することをお勧めします。

階層は、好きなように使用できるカスタム変数です。 設定されたヒットの後は保持されません。 アドビとの契約でサポートされている場合は、最大 5 個の階層を使用できます。

## 階層へのデータの入力

各階層は、イメージリクエストの [`h1` - `h5` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。 例えば、`h1` クエリ文字列パラメーターで階層 1 のデータを収集し、`h4` クエリ文字列パラメーターで階層 4 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `hier1`～`hier5` を使用します。 実装のガイドラインについては、実装ユーザーガイドの [hier](/help/implement/vars/page-vars/hier.md) を参照してください。

## ディメンション項目

階層には実装のカスタム文字列が含まれるので、組織で各階層のディメンション項目を決定します。 必ず、各階層の目的と一般的なディメンション項目を[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録してください。
