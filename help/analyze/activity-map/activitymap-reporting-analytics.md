---
description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
title: Analytics の Activity Map レポート
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 92%

---

# Analytics の Activity Map レポート

Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。

## 権限の設定 {#permissions}

ユーザーが Activity Map ディメンションを使用してレポートを作成できるようにするには、管理者が次の設定をおこなう必要があります。

* [製品プロファイルへのActivity Mapアクセスの追加](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* ディメンションに対するユーザーのアクセス権をカスタマイズします。次の節を参照してください。

## Analytics Activity Map ディメンション {#dimensions}

[ディメンションに対するユーザーのアクセス権のカスタマイズ](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)は、詳細なレベルでおこなえます。Analytics で使用可能な Activity Map ディメンションは次のとおりです。

| ディメンション | 説明 |
|---|---|
| Activity Map ページ | リンクがクリックされたページのリストを表示します。 |
| Activity Map 地域 | Web サイト全体で収集されたすべてのリンク領域のリストを表示します。1 つの領域が複数のページに表示される場合は、そのすべてのページにまたがって指標が集計されます。 |
| Activity Map リンク | Web サイト全体で収集されたすべてのリンクのリストを表示します。 |
| Activity Map リンクと地域 | Web サイト全体で収集されたすべてのリンクのリストを、その領域と共に表示します。 |
| Activity Map XY | 未使用 |

* Analytics の実装で[Activity Map が有効](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md)になっている場合、これらのディメンションは、Analysis Workspace、Reports &amp; Analytics、Report Builder で使用できます。
* Reports &amp; Analytics で、**[!UICONTROL すべてのレポートを表示]**／**[!UICONTROL Activity Map]** を選択します。
* 特定のページのリンクおよび領域を見るには、目的の Activity Map ページから Activity Map リンクおよび地域への分類を作成します。
