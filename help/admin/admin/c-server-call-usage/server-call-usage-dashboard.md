---
description: Adobe Analytics での現在のサーバーコールの使用状況を表示する方法。
title: 現在のサーバーコールの使用状況の表示
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---

# 現在のサーバーコールの使用状況の表示

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL サーバーコールの使用状況]**／**[!UICONTROL 現在の使用状況]**

>[!IMPORTANT]
>
>表示されるすべての使用数およびコミットメント数は、すべてのログイン会社とレポートスイートにわたって累積したものです。

現在の使用状況ダッシュボードは、以下のように動作します。

* サーバーコールタイプごとに、サーバーコールの使用数とコミットメントの分類を表示します。この表示は顧客ごとに異なる可能性があり、契約内容に一致します。例えば、4 つの異なるタイプのサーバーコール（Web の場合のプライマリとセカンダリ、モバイルの場合のプライマリとセカンダリ）を契約したとします。この場合、表示は 4 つのタブ（タイプごとに 1 つずつ）で構成されます。各タブでは、現在の使用期間の使用数を表示できます。
* 現在の使用状況（緑の線）と契約上の使用限度（赤の線）を比較します。

  ![](/help/admin/admin/c-server-call-usage/assets/current_period.png)

* 現在の期間の使用状況と前年の使用状況（青の線）を比較します。言うまでもなく、青の線が表示されるのは、前年のサーバーコール使用状況データが会社にある場合だけです。

  >[!NOTE]
  >
  >前の期間の使用状況を表示する場合は、「[レポートスイートの使用状況](/help/admin/admin/c-server-call-usage/report-suite-usage.md)」タブに移動し、前の期間の使用状況データをダウンロードする必要があります。

* 使用された呼び出しの数（全体に占める割合と生データ）と経過した使用期間（全体に占める割合と生データ）を一覧表示します。
* デフォルトでは、5 日遅れで毎日更新されます。
* すべてのレポートレットの折りたたみと展開が可能です。

![](/help/admin/admin/c-server-call-usage/assets/server_call_dashboard.png)

| UI 用語 | 定義 |
| --- | --- |
| 当期の使用状況（緑） | 当期の使用状況は[使用期間](/help/admin/admin/c-server-call-usage/overage-overview.md)に基づいています。 |
| 前期の使用状況（青） | 前期は、現在の使用期間の 1 年前と定義されます。 |
| 使用限度（赤） | この使用期間に設定されている契約上の使用限度です。 |
