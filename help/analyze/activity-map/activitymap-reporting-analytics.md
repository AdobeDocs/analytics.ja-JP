---
description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
seo-description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
seo-title: AnalyticsのActivity Mapレポート
solution: Analytics
title: AnalyticsのActivity Mapレポート
topic: Activity Map
uuid: 057c6ab2- aa06-4779- ac16- f9b367d9ea43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# AnalyticsのActivity Mapレポート

Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

ユーザーが Activity Map ディメンションを使用してレポートを作成できるようにするには、管理者が次の設定をおこなう必要があります。

* [Activity Map アクセスグループにユーザーを追加します](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* このグループによるアクセスを許可するレポートスイートを追加します。**[!UICONTROL 管理]** 者/ **[!UICONTROL ユーザー管理]** / **[!UICONTROL グループ]** / **[!UICONTROL Activity Mapアクセス]** / **[!UICONTROL 編集に移動]**&#x200B;します。
* ディメンションに対するユーザーのアクセス権をカスタマイズします。次の節を参照してください。

## Analytics Activity Map dimensions {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

[ディメンションに対するユーザーのアクセス権のカスタマイズ](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html)は、詳細なレベルでおこなえます。Analytics で使用可能な Activity Map ディメンションは次のとおりです。

| ディメンション | 説明 |
|---|---|
| Activity Map ページ | リンクがクリックされたページのリストを表示します。 |
| Activity Map 地域 | Web サイト全体で収集されたすべてのリンク領域のリストを表示します。1 つの領域が複数のページに表示される場合は、そのすべてのページにまたがって指標が集計されます。 |
| Activity Map リンク | Web サイト全体で収集されたすべてのリンクのリストを表示します。 |
| Activity Map リンクと地域 | Web サイト全体で収集されたすべてのリンクのリストを、その領域と共に表示します。 |
| Activity Map XY | 未使用 |

* Analytics の実装で [Activity Map が有効](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)になっている場合、これらのディメンションは、Analysis Workspace、Reports &amp; Analytics、Report Builder で使用できます。
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL Activity Map]**.

* 特定のページのリンクおよび領域を見るには、必要な Activity Map ページから Activity Map リンクと地域への内訳を作成します。

