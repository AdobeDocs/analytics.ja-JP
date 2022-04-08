---
title: null
description: null
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 









## 





## 



## 目的のプロパティをクリックします。

「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。

* 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
* 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。

[!UICONTROL eVars] セクションを見つけます。

### eVar を値またはデータ要素に設定できます。別の Analytics 変数から値をコピーすることもできます。

AppMeasurement および カスタムコードエディターの s.eVar1～s.eVar250`post_evar`

1. 各 eVar は、組織に固有のカスタム値を含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。
2. カウンター eVar
3. eVar 値には通常、文字列値が含まれます。ただし、eVar にカウンターを代わりに含めるように設定できます。例えば、購入前におこなわれた内部検索の数をカウントするとします。テキスト値を設定する代わりに、次の構文を使用します。

eVar カウンターで小数点以下が 3 桁以上ある場合は、2 桁に四捨五入されます。eVar カウンターには負の値は設定できません。

| [!IMPORTANT] | カウンター eVar を使用する前に、Admin Console で eVar を「カウンター」に設定する必要があります。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。 | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* The `visitor_id` column ties hits to the same visitor. In actual raw data, the concatenated values of `visid_high` and `visid_low` determine visitor ID.
* The `pagename` column populates the Pages dimension.
* The `evar` column determines the hits when eVar1 was explicitly set.
* The `post_evar1` carries the previous value, dependent on the variable&#39;s allocation and expiration set under report suite settings.
* The `event_list` column contains all metric data. For this example, `event1` is &#39;Searches&#39;, and the other events are standard shopping cart metrics. In actual raw data, `event_list` contains a comma-delimited set of numbers with a lookup table tying those numbers to a metric.

### Translating data collection to reporting

Tools in Adobe Analytics, such as Analysis Workspace, work off of this collected data. For example, if you pulled a report using eVar1 as the dimension and Orders as the metric, you would see a report similar to the following:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace pulls this report using the following logic:

* Look through all `event_list` values, and pick out all the hits with `purchase` in them.
* Out of those hits, display the `post_evar1` value.

### The importance of allocation and expiration

Since allocation and expiration determine what values persist, they are vital in getting the most value out of an analytics implementation. Adobe highly recommends that you discuss within your organization how multiple values for each eVar are handled (allocation) and when eVars stop persisting data (expiration).

* By default, an eVar uses last allocation. New values overwrite persisted values.
* By default, an eVar uses an expiration of visit. Once a visit ends, values stop copying over from row to row in the `post_evar` column.

You can change eVar allocation and expiration under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

## Value of eVars over props

Adobe recommends using eVars in most cases, supported through the following:

* eVars have a 255-byte limit in reports. Props have a 100-byte limit.
* Props by default do not persist beyond the hit they are set. eVars have custom expiration, allowing you to determine when an eVar no longer gets credit for a subsequent event. However, if you use [report time processing](/help/components/vrs/vrs-report-time-processing.md), both props and eVars can use a custom attribution model.
* Adobe supports up to 250 eVars, and only 75 props.

See [prop](prop.md) for more comparisons between props and eVars.
