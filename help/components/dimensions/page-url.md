---
title: ページ URL
description: ページの URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 52%
---
# ページ URL

「ページ URL」 [&#x200B; ディメンション &#x200B;](overview.md)には、サイト上のURLが一覧表示されます。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。 他の Analytics ソリューションで URL ディメンションを使用する場合は、ヒットごとに [eVar](evar.md) に値をコピーすることを検討してください。

## このディメンションへのデータ入力

AppMeasurementは、各[&#x200B; ページビュー呼び出し（`t()`） &#x200B;](/help/implement/vars/functions/t-method.md)でページ URLを自動的に収集します。 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用して、収集された値を上書きできます。 URLが255 バイトを超える場合、オーバーフローは`-g` クエリ文字列パラメーターに保存されます。 URLにプロトコル文字列とクエリ文字列が含まれています。 [&#x200B; リンク トラッキング呼び出し（`tl()`） &#x200B;](/help/implement/vars/functions/tl-method.md)は、URL値が存在する場合でも、常にこのディメンションを削除します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Web SDK / XDM フィールド** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/data-types/webpage-details) |
| **クエリパラメーター** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 255 バイト（オーバーフローで制限なし） |
| **永続性** | ヒット |

## URL を使用して eVar を設定する

eVar を連結された文字列 `window.location.hostname + window.location.pathname` に設定することをお勧めします。 この文字列は、プロトコル、クエリ文字列、アンカータグを省略するので、通常、`window.location.href` 文字列よりも適切に動作します。

eVar を Data Warehouse の「ページ URL」ディメンションと完全に一致させる場合は、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、各ヒットに対して eVar を `D=g` に設定できます。

## ディメンション項目

ディメンション項目には、サイトのページの URL が含まれます。
