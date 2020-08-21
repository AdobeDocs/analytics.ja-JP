---
title: 平均ページの深さ
description: ディメンションが存在するページの平均数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 59%

---


# 平均ページの深さ

「平均ページの深さ」指標は、特定の訪問中にディメンション項目がどの程度あるかを示します。 例えば、通常、ホームページでは平均ページの深さが購入確認ページよりも浅く表示されます。購入確認ページは通常訪問中さらに「深い」場所で表示されます。この指標は、特定のディメンション項目の平均ページ数を把握したい場合に役立ちます。 この情報を使用すると、ページの深さが平均的に浅い場合に、特定のページを最適化して新規訪問者に向けることができます。

>[ヒント]この指標を別の指標（[訪問数](visits.md)など）と同時に使用すると、より優れた洞察を得ることができます。この指標を単独で使用する場合、異常値ページの深さを含むディメンション項目が取得されます。これは通常、有用ではありません。

## この指標の計算方法

訪問の最初のページのページの深さは `0` です。次のページのページの深さは 1 で、各ページビューは訪問の終了まで増加します。この指標は、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）呼び出しに対してのみ増加し、リンクトラッキング（[`tl()`](/help/implement/vars/functions/tl-method.md)）呼び出しには増加しません。

特定のディメンション項目に対して、そのディメンション項目のすべてのページ深さを追加し、訪問数で割ります。 結果の数値は、平均的なページの深さで、最も近い整数に丸められます。Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

例えば、次の訪問例を考えてみましょう。

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>平均ページの深さを小数点以下で表示する場合は、この指標を数式内の唯一の要素として使用して計算指標を作成します。計算指標の小数点以下の桁数を目的の桁数に増やします。

## 100% を超える割合

この指標には、100% を超える割合が頻繁に含まれます。分母は、ディメンション全体の平均ページ深度で、分子はディメンション項目の平均ページ深度です。 ディメンション全体の平均ページの深さが、特定のディメンション項目の平均ページの深さより低い場合、100%を超える割合が表示されます。 この指標でランクレポートを並べ替えると、異常値による平均ページの深さの値が表示されますが、これは通常有用ではありません。ランクレポートでは、[訪問回数](visits.md)など別の指標で並べ替えることをお勧めします。