---
title: 階層
description: （廃止）レポートで使用できるカスタムディメンション。
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 86%

---

# 階層

>[!IMPORTANT]
>
>このディメンションは廃止されており、Analysis Workspaceで使用できる [ ディメンション ](overview.md) ではありません。 アドビでは、代わりに [eVar](evar.md) と分類を使用することをお勧めします。

階層は、好きなように使用できるカスタム変数です。設定されたヒットの後は保持されません。アドビとの契約でサポートされている場合は、最大 5 個の階層を使用できます。

## 階層へのデータの入力

各階層は、イメージリクエストの [`h1` - `h5` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。例えば、`h1` クエリ文字列パラメーターで階層 1 のデータを収集し、`h4` クエリ文字列パラメーターで階層 4 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `hier1`～`hier5` を使用します。実装のガイドラインについては、実装ユーザーガイドの [hier](/help/implement/vars/page-vars/hier.md) を参照してください。

## ディメンション項目

階層には実装のカスタム文字列が含まれるので、組織で各階層のディメンション項目を決定します。必ず、各階層の目的と一般的なディメンション項目を[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録してください。
