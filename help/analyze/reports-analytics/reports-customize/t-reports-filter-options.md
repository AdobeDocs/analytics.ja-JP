---
description: フィルターを使用すると、フィルターに一致する行項目をレポートに含めたりレポートから除外したりできます。
title: レポートデータのフィルタリング
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# レポートデータをフィルター {#concept_09DC5B986A644738B12204DAC76A90E1}

フィルターを使用すると、フィルターに一致する行項目をレポートに含めたりレポートから除外したりできます。

## シンプルフィルター {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

このシンプルフィルターは大部分のレポートに表示され、特定の行項目をすばやく探し出すために役立ちます。シンプルフィルターでは、特殊文字を使用できません。そのため、`-, ", ', +` およびその他の特殊文字はレポート内のリテラル値に一致します。複数の語句を含む行項目を検索するには、スペースを使用します。

次に例を示します。

```
help search
```

この条件は、次のページに一致します。

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## アドバンスフィルター {#section_E016626C084640E8A066B2FDA5B932BF}

詳細フィルターを使用すると、一連の検索を使用して検索範囲を制御できます。フィルター すべてのオプションまたは任意のフィルターに一致するようにフィルターできます。

![](assets/advanced_filter.png)

**Contains**

行項目の任意の場所に検索語が含まれる場合に一致します。 これは単純なフィルターと同じ働きをします。

>[!NOTE]フィルターではスペースを使用できません。スペースは検索時に区切り文字と見なされます。

**次を含まない**

行項目のどこにも検索語句が見つからない場合に一致します。 「次を含まない」の条件を使用すると、「unspecified」、「none」、「キーワードを使用できません」、およびその他の[特殊な値](https://marketing.adobe.com/resources/help/ja_JP/reference/none-unspecified-unknown-other.html)をレポートから除外できます。

次を含まない。`none`

より正確なフィルターを使用するには、アドバンス（特殊文字）フィルターを使用します。

* アドバンス（特殊文字）。`-^none$`
* アドバンス（特殊文字）。`-"keyword unavailable"`

例えば、次の行項目は「次を含まない」の条件でフィルタされますが、「アドバンス（特殊文字）」の条件ではフィルタされません。

```
help:Rename the None classification key
```

**次のいずれかを含む**

行項目内にスペースで区切られた語句がある場合に一致します。 次のフィルターは、「mens」または「sale」を含むすべてのページを表示します。

次のいずれかを含む: `mens sale`

この条件は、次のページに一致します。

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**次に等しい**

行項目全体（スペースや他の文字を含む）が指定したフレーズと一致する場合に一致します。

次に等しい: `mens:desk & travel`

`Mens:Desk & Travel`

**次の語句で始まる**

行項目（スペースやその他の文字を含む）が指定したフレーズを持つ開始である場合に一致します。

次の語句で始まる。`mens`

この条件は、次のページに一致します。

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**次の語句で終わる**

行項目（スペースやその他の文字を含む）が指定したフレーズで終わる場合に一致します。

次の語句で終わる。`jean`

この条件は、次のページに一致します。

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## アドバンス（特殊文字）{#section_83DA3B6C23EB4C119DB6D74062DB501D}

[詳細]では、ワイルドカード検索やその他の複雑な検索を実行できます。

| アドバンス（特殊文字） | 説明 |
|--- |--- |
| `" "` | 指定したフレーズと正確に等しい場合に一致します。 |
| `*` | ワイルドカード、最長一致の検索ができます。<br>例えば、`r*p` は「Registration Signup」に一致します。 |
| `^` | 次の語句で始まる。<br>この特殊文字と検索フレーズの間にスペースを入れてはなりません。 |
| `$` | 次の語句で終わる。<br>この特殊文字と検索フレーズの間にスペースを入れてはなりません。 |
| `-` | NOT。<br>この特殊文字と検索フレーズの間にスペースを入れてはなりません。 |
| `|` | <br>注意：この特殊文字の両脇には必ずスペースを指定し、`" | "` のようにします。 |

## レポート固有のフィルターの作成 {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

レポートのフィルターを作成する手順。

<!-- 

t_reports_filter_specific.xml

 -->

特定のレポートには、そのレポートに固有のフィルターが含まれています。 例えば、を使用してWebペ [!UICONTROL Purchase Conversion Funnel Report] ージでフィルターできます。 「」では、 [!UICONTROL Geosegmentation Report] 地域別にフィルターできます。 その他のレポートには、その他のフィルターが表示されます。

これらの項目にアクセスすると、フィルターで指定された項目のレポート指標をリストできます。

**レポート固有のフィルター**

1. (> > [!UICONTROL Purchase Report] )などのレ **[!UICONTROL Site Metrics]** ポート **[!UICONTROL Purchases]** を生成 **[!UICONTROL Purchase Conversion Funnel]**&#x200B;する。
1. In the report header, click the **[!UICONTROL Filter]** link.
1. ページで、 [!UICONTROL Filter Selector] をクリックし **[!UICONTROL Apply a Filter]**&#x200B;て、フィルターの種類を選択します。
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. クリック **[!UICONTROL OK]**.

## クロス集計フィルターの追加 {#task_065042E384DA4BF3864C58AF2B88D6E2}

クロス集計フィルターを追加する手順を説明します。

<!-- 

t_reports_correlation_filter.xml

 -->

特定のレポートでは、カスタムのクロス集計フィルターを追加できます。 例えば、サイトセクションと女性のページとの相関関係があるレポートスイートのを表示している場合、フィルタールールを作成して、サイトセクション=女性の場合に最も人気の高いページを示すレポートを生成できます。 [!UICONTROL Pages Report]

使用可能な任意のクロス集計を使用して、クロス集計レポートに表示されるデータをフィルタリングできます。 ここに示す例は、検索エンジンのクロス集計フィルタを追加する方法を示しています。

**クロス集計フィルタを追加するには**

1. クロス集計をサポートするレポートを実行します([内訳レポートの実行](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69)を参考。)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. の下で、 [!UICONTROL Filter Rule Creator]項目とクロス集計するカテゴリを選択します。
1. ズーム後に **[!UICONTROL OK.]**
