---
description: Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。
title: Analytics の Activity Map レポート
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 79%

---

# Analytics の Activity Map レポート

Analytics で権限を設定する方法と、Analytics で使用可能なディメンションについて説明します。

## 権限の設定 {#permissions}

ユーザーが Activity Map ディメンションを使用してレポートを作成できるようにするには、管理者が次の設定をおこなう必要があります。

* [製品プロファイルへのActivity Mapアクセスの追加](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* ディメンションに対するユーザーのアクセス権をカスタマイズします。次の節を参照してください。

## AnalyticsActivity Mapディメンション {#dimensions}

[ディメンションに対するユーザーのアクセス権のカスタマイズ](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)は、詳細なレベルでおこなえます。Analytics で使用可能な Activity Map ディメンションは次のとおりです。

| ディメンション | 説明 |
|---|---|
| Activity Map ページ | リンクがクリックされたページのリストを表示します。 |
| Activity Map 地域 | Web サイト全体で収集されたすべてのリンク領域のリストを表示します。1 つの領域が複数のページに表示される場合は、そのすべてのページにまたがって指標が集計されます。 |
| Activity Map リンク | Web サイト全体で収集されたすべてのリンクのリストを表示します。 |
| Activity Map リンクと地域 | Web サイト全体で収集されたすべてのリンクのリストを、その領域と共に表示します。 |
| Activity Map XY | 未使用 |

* Analytics の実装で [有効Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Analysis Workspaceで、Activity Map 関連のディメンションをレポートに取り込みます。
* 特定のページのリンクおよび領域を見るには、目的の Activity Map ページから Activity Map リンクおよび地域への分類を作成します。
