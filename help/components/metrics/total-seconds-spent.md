---
title: 合計滞在時間（秒）
description: ディメンション項目に費やした合計秒数。
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 90%

---

# 合計滞在時間（秒）

「合計使用秒数」の[指標](overview.md)は、特定のディメンション項目に訪問者が費やした合計秒数を示します。 この指標は、特定のディメンション項目に費やした生の時間を求め、他の滞在時間指標のオファーのような平均を求めない場合に役立ちます。

Report Builder では、この指標は「合計滞在時間」という名前です。

## この指標の計算方法

この指標では、次の手順を使用して計算を測定します。

1. 特定のヒットについて、タイムスタンプを確認します。
2. このヒットを、訪問の次のヒットのタイムスタンプと比較します。 ページビューとリンクトラッキングのヒット数の両方。
3. 2 つのヒットの間隔を経過する秒数が、ディメンション項目に影響します。

[eVars](../dimensions/evar.md) などの持続的な変数は、合計滞在時間（秒）にカウントされます。 トラフィック変数（[prop など](../dimensions/prop.md)）には、後続のリンクトラッキングコールで費やされた秒数が含まれます。

>[!TIP]
>
>その後のイメージリクエストでは経過時間を測定しないので訪問の最後のヒット時には滞在時間は測定されません。 この概念は、単一のヒット（バウンス）から成る訪問にも適用されます。

滞在時間の一般情報について詳しくは、[滞在時間の概要](time-spent.md)を参照してください。
