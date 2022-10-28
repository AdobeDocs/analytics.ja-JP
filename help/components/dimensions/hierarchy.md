---
title: 階層
description: レポートで使用できるカスタムディメンション。
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# 階層

>[!IMPORTANT]
>
>このディメンションは廃止され、Analysis Workspaceで使用できるディメンションではありません。 アドビでは、[eVar](evar.md) と分類の使用をお勧めします。

階層は、好きなだけ使用できるカスタム変数です。 prop は、設定されたヒットの後は保持されません。契約でサポートされている場合は、最大 5 つのAdobeを使用できます。

## 階層にデータを入力

各階層で [`h1` - `h5` クエリ文字列](/help/implement/validate/query-parameters.md) （イメージリクエスト内） 例えば、 `h1` クエリ文字列パラメーターは階層 1 のデータを収集し、 `h4` クエリー文字列パラメーターは、階層 4 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `hier1` — `hier5` を使用します。詳しくは、 [hier](/help/implement/vars/page-vars/hier.md) を参照してください。

## ディメンション項目

階層は実装内にカスタム文字列を含むので、組織は各階層のディメンション項目を決定します。 各階層の目的と一般的なディメンション項目を必ず [ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md).
