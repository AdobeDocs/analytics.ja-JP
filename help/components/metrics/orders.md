---
title: 注文件数
description: おこなわれた購入の数。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 65%

---

# 注文件数

「注文件数 [ 指標 ](overview.md) は、サイトで行われた購入イベントの合計数を表示します。 この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。この指標を任意のディメンションと組み合わせると、どのディメンション項目が注文に貢献したかを確認できます。 例えば、（[追跡コード](../dimensions/tracking-code.md)ディメンションを使用して）トップキャンペーンまたは（[eVar](../dimensions/evar.md) を使用して）購入に貢献したトップ内部検索用語を確認できます。

## この指標の計算方法

この指標は、`purchase` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒット数をカウントします。
