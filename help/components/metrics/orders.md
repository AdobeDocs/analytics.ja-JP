---
title: 注文件数
description: おこなわれた購入の数。
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '91'
ht-degree: 100%

---

# 注文件数

「注文件数」指標は、サイトで行われた購入イベントの合計数を示します。この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。この指標を任意のディメンションと組み合わせて、注文に貢献したディメンション項目を確認できます。例えば、（[追跡コード](../dimensions/tracking-code.md)ディメンションを使用して）トップキャンペーンまたは（[eVar](../dimensions/evar.md) を使用して）購入に貢献したトップ内部検索用語を確認できます。

## この指標の計算方法

この指標は、`purchase` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒット数をカウントします。
