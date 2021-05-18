---
description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
title: Analytics の Activity Map レポート
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 95%

---

# Analytics の Activity Map レポート

Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。

## 権限の設定 {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

ユーザーが Activity Map ディメンションを使用してレポートを作成できるようにするには、管理者が次の設定をおこなう必要があります。

* [Activity Map アクセスグループにユーザーを追加します](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* このグループによるアクセスを許可するレポートスイートを追加します。**[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL ユーザー管理]** > **[!UICONTROL グループ]** > **[!UICONTROL Activity Mapアクセス]** > **[!UICONTROL 編集]**&#x200B;に移動します。
* ディメンションに対するユーザーのアクセス権をカスタマイズします。次の節を参照してください。

## Analytics Activity Map ディメンション {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

[ディメンションに対するユーザーのアクセス権のカスタマイズ](https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)は、詳細なレベルでおこなえます。Analytics で使用可能な Activity Map ディメンションは次のとおりです。

| ディメンション | 説明 |
|---|---|
| Activity Map ページ | リンクがクリックされたページのリストを表示します。 |
| Activity Map 地域 | Web サイト全体で収集されたすべてのリンク領域のリストを表示します。1 つの領域が複数のページに表示される場合は、そのすべてのページにまたがって指標が集計されます。 |
| Activity Map リンク | Web サイト全体で収集されたすべてのリンクのリストを表示します。 |
| Activity Map リンクと地域 | Web サイト全体で収集されたすべてのリンクのリストを、その領域と共に表示します。 |
| Activity Map XY | 未使用 |

* Analytics の実装で[Activity Map が有効](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)になっている場合、これらのディメンションは、Analysis Workspace、Reports &amp; Analytics、Report Builder で使用できます。
* Reports &amp; Analytics で、**[!UICONTROL すべてのレポートを表示]**／**[!UICONTROL Activity Map]** を選択します。

* 特定のページのリンクおよび領域を見るには、目的の Activity Map ページから Activity Map リンクおよび地域への分類を作成します。
