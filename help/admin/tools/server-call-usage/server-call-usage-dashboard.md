---
description: Adobe Analytics での現在のサーバーコールの使用状況を表示する方法。
title: 現在のサーバーコールの使用状況の表示
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
TQID: 'https://experienceleague.adobe.com/5DgWR4QWklOEMK1Ato17-lcpMdnRgaIrMfds9ATXUpE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c9d85838-8d05-4bc7-9f18-30ec779251bc
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 32%

---

# 現在のサーバーコールの使用状況の表示

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL サーバーコールの使用状況]**／**[!UICONTROL 現在の使用状況]**

>[!IMPORTANT]
>
>表示されるすべての使用数およびコミットメント数は、すべてのログイン会社とレポートスイートにわたって累積したものです。

現在の使用状況ダッシュボード

* サーバーコールタイプごとに、サーバーコールの使用数とコミットメントの分類を表示します。 このビューは、顧客ごとに異なる可能性があり、契約に含まれる内容と一致しています。 例えば、Web用とプライマリ用の4種類のサーバーコール、プライマリとセカンダリ、モバイル用のセカンダリにサインアップしている場合があります。 この場合、このビューは4つのタブで構成され、各タイプに1つずつ表示されます。 各タブ内で、現在の使用期間の消費量を表示できます。
* 現在の使用状況（緑の線）と契約上の使用制限（赤の線）を比較します。

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* 現在の期間の使用状況と昨年の使用状況を比較します（青い線）。 明らかに、青い線は、会社が前年度のサーバーコール使用状況データを持っている場合にのみ表示されます。

  >[!NOTE]
  >
  >前の期間の使用状況を表示する場合は、「[レポートスイートの使用状況](/help/admin/tools/server-call-usage/report-suite-usage.md)」タブに移動し、前の期間の使用状況データをダウンロードする必要があります。

* 使用された呼び出しの割合（パーセンテージと生データ）と、使用された使用期間の割合（パーセンテージと生データ）が一覧表示されます。
* デフォルトでは、は毎日アップデートされ、5日間の処理待ちがあります。
* すべてのレポートレットを折りたたんで展開できます。

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

| UI 用語 | 定義 |
| --- | --- |
| 当期使用状況（緑） | 現在の期間は、[使用期間](/help/admin/tools/server-call-usage/overage-overview.md)に基づいています。 |
| 前期の使用状況（青） | 前期は、現在の使用期間から1年を差し引いた期間として定義されます。 |
| 使用制限（赤） | この使用期間の契約上の使用制限。 |
