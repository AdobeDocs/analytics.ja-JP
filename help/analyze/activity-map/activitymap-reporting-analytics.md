---
description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
seo-description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
seo-title: '[!DNL Activity Map]レポート(Analytics)'
solution: Analytics
title: '[!DNL Activity Map]レポート(Analytics)'
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] analyticsでのレポート

Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [[!DNL Activity Map]アクセスグループにユーザーを追加します](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* このグループによるアクセスを許可するレポートスイートを追加します。Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* ディメンションに対するユーザーのアクセス権をカスタマイズします。次の節を参照してください。

## Analyticsディメンシ [!DNL Activity Map] ョン {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

[ディメンションに対するユーザーのアクセス権のカスタマイズ](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html)は、詳細なレベルでおこなえます。Here are the [!DNL Activity Map] dimensions available in Analytics:

| ディメンション | 説明 |
|---|---|
| [!DNL Activity Map] ページ | リンクがクリックされたページのリストを表示します。 |
| [!DNL Activity Map] 地域 | Web サイト全体で収集されたすべてのリンク領域のリストを表示します。1 つの領域が複数のページに表示される場合は、そのすべてのページにまたがって指標が集計されます。 |
| [!DNL Activity Map] リンク | Web サイト全体で収集されたすべてのリンクのリストを表示します。 |
| [!DNL Activity Map] リンクと地域 | Web サイト全体で収集されたすべてのリンクのリストを、その領域と共に表示します。 |
| [!DNL Activity Map] XY | 未使用 |

* Analytics の実装で  [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

