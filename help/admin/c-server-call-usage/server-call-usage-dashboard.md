---
description: 'null'
seo-description: 'null'
seo-title: 現在のサーバーコールの使用状況の表示
title: 現在のサーバーコールの使用状況の表示
uuid: 1a42a45f-4bbc-4b5a-9706- c8937265de2b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 現在のサーバーコールの使用状況の表示

**[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL サーバー呼び出しの使用]** 状況/ **[!UICONTROL 現在の使用状況]**

>[!IMPORTANT]
>
>表示される使用状況およびコミットメント数は、すべてのログイン会社とレポートスイートに累積されます。

現在の使用状況ダッシュボードは、以下のように動作します。

* サーバーコールタイプごとに、サーバーコールの使用数とコミットメントの内訳を表示します。この表示は顧客ごとに異なる可能性があり、契約内容に一致します。例えば、4 つの異なるタイプのサーバーコール（Web の場合のプライマリとセカンダリ、モバイルの場合のプライマリとセカンダリ）を契約したとします。この場合、表示は 4 つのタブ（タイプごとに 1 つずつ）で構成されます。各タブでは、現在の使用期間の使用数を表示できます。
* 現在の使用状況（緑の線）と契約上の使用限度（赤の線）を比較します。

   ![](assets/current_period.png)

* 現在の期間の使用状況と前年の使用状況（青の線）を比較します。言うまでもなく、青の線が表示されるのは、前年のサーバーコール使用状況データが会社にある場合だけです。

   >[!NOTE]
   >
   >If you want to view usage for a previous time period, you have to go to the [Report Suite Usage](../../admin/c-server-call-usage/report-suite-usage.md#concept_E50FA5BD93404EB8B2FE954F658FDAFD) tab and download the usage data for a previous period.

* 使用された呼び出しの数（全体に占める割合と生データ）と経過した使用期間（全体に占める割合と生データ）を一覧表示します。
* デフォルトでは、5 日遅れで毎日更新されます。
* すべてのレポートレットの折りたたみと展開が可能です。

![](assets/server_call_dashboard.png)

| UI 上の用語 | 定義 |
|---|---|
| 当期の使用状況（緑） | 当期の使用状況は[使用期間](../../admin/c-server-call-usage/overage-overview.md#section_CBA348A039F34563B097CD8890AB358D)に基づいています。 |
| 前期の使用状況（青） | 前期は、現在の使用期間の 1 年前と定義されます。 |
| 使用限度（赤） | この使用期間に設定されている契約上の使用限度です。 |

