---
title: トラッキングコード
description: トラッキングコードまたはキャンペーンの名前。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 3%

---


# トラッキングコード

「トラッキングコード」ディメンションは、サイト上のトラッキングコードの名前をリストします。 このディメンションは、通常、クエリ文字列パラメーターを使用して収集されます。 異なるクエリ文字列パラメータ値を持つリンクは、インターネット上の異なる場所に配置できます。 このディメンションは、どのリンクがサイトへのトラフィックの増加に最も成功したかをレポートします。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`v0` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、この [`campaign`](/help/implement/vars/page-vars/campaign.md) 変数を使用してこのデータを収集します。

## 分析コード値

ディメンション値には、サイト上のトラッキングコードの名前が含まれます。 組織は、使用する特定のディメンション値を決定します。
