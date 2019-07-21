---
description: 'null'
keywords: データフィード;job;visitors;Experience Cloud ID;analytics訪問者ID;識別する
seo-description: 'null'
seo-title: 訪問者の識別
solution: Analytics
title: 訪問者の識別
topic: Reports and Analytics
uuid: 2490b67e- a333-422d-82fa- cb0670ef2e0c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 訪問者の識別

Analytics には、訪問者を特定できる（[訪問者の特定](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)に表示される）メカニズムがいくつかあります。Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**一意の訪問者を特定するには**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5、8、および 9 の行は、データソースを使用してアップロードされる概要行です。7 はトランザクション ID データソースアップロードを表し、これは訪問回数や訪問者数には含めません。詳しくは、 [ヒットソース参照](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combine `post_visid_high` with `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

訪問者 ID 値の判別に使用されたメカニズムを判断したい場合（cookie の受け入れを計算するためなど）は、使用された ID 方式を示す参照キーが `post_visid_type` に格納されています。この参照キーは、[下記のテーブル](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A)に訪問者 ID メカニズムと共に表示されます。

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

Experience Cloud ID は、`mcvisid` という個別の列でレポートされます。この ID は独自の列でレポートされるので、Analytics が訪問者の特定にこの ID を使用しているか、別の ID を使用しているかが明確ではないことがあります。

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. これらのフィールドは、必ずデータフィードのすべての行に値を持つ唯一の訪問者 ID フィールドです。

## Analytics 訪問者 ID {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Analytics で訪問者を特定する方法はいくつかあります（優先順に以下の表に示します）。

| 使用順 | クエリパラメータ（収集方式） | post_visid_type 列の値 | 次の場合に存在 |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid（s.visitorID）](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) | 0 | s.visitorID が設定されている。 |
| ![](assets/step2_icon.png) | [aid（s_vi cookie）](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_analytics) | 3 | 訪問者 ID サービス展開前に既に訪問者に s_vi cookie があった、または訪問者 ID [grace period](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_grace_period) が設定済みである。 |
| ![](assets/step3_icon.png) | [mid（IDサービスによって設定されたAMCV_ cookie）](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | 訪問者のブラウザーがcookie（ファーストパーティ）を受け入れ、IDサービスがデプロイされている。 |
| ![](assets/step4_icon.png) | [fid（H.25.3 以降のフォールバック cookie または JavaScript 用の AppMeasurement）](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 4 | 訪問者のブラウザーが cookie（ファーストパーティ）を受け入れる。 |
| ![](assets/step5_icon.png) | [HTTP モバイル購読者ヘッダー](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_mobile) | 2 | デバイスがモバイルデバイスとして認識されている。 |
| ![](assets/step6_icon.png) | [IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 1 | 訪問者のブラウザーが cookie を受け入れない。 |

多くのシナリオにおいて、1 つの呼び出しで 2 つまたは 3 つの異なる ID が表示されることがありますが、Analytics はそのリストに最初に出現する ID を正式な訪問者 ID として使用し、その値を `post_visid_high` 列と `post_visid_low` 列に分割します。例えば、'vid' クエリパラメーターに格納されるカスタム訪問者 ID を設定している場合は、この ID が、同じヒットで存在する他の ID よりも優先して使用されます。
