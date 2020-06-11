---
title: ページ URL
description: ページのURL。
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# ページ URL

「ページURL」ディメンションは、サイト上のURLをリストします。

>[!IMPORTANT] このディメンションは、Data Warehouseでのみ使用できます。 他のAnalyticsソリューションでURLディメンションを使用する場合は、eVarを使用し [ます](evar.md)。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`g` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、この [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用してこのデータを収集します。

## eVarにURLを入力する

eVarを連結された文字列に設定することをお勧め `window.location.hostname + window.location.pathname`します。 この文字列は、プロトコル、クエリ文字列 `window.location.href` およびアンカータグを省略するので、通常、この文字列よりも適切に動作します。

eVarをData Warehouseの「ページURL」ディメンションと完全に一致させる場合は、 [動的変数を使用して](/help/implement/vars/page-vars/dynamic-variables.md) 、各ヒットでeVarを `D=g` 設定できます。 すべての [`tl()`](/help/implement/vars/functions/tl-method.md) 呼び出しでページURLが削除されるので、このメソッドは、カスタムリンクヒットに対しては動作しません。

## 分析コード値

ディメンション値には、サイトのページのURLが含まれます。
