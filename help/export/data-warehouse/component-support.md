---
title: Data Warehouseのコンポーネントサポート
description: Data Warehouse リクエストを作成するときに使用できるディメンションと指標、使用できないディメンションと指標、異なる動作について説明します。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Data Warehouse でのコンポーネントのサポート

このページでは、Data Warehouse リクエストを作成する際に使用できるディメンションと指標について説明します。 セクションには、使用可能なコンポーネント、使用できないコンポーネント、他のAdobe Analytics ツールとは異なる動作が含まれます。

## Data Warehouse専用のディメンション

次のディメンションはData Warehouseで使用できますが、他のAdobe Analytics機能では使用できません。

* [[!UICONTROL Experience Cloud訪問者ID]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL IP アドレス ]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL ページ URL]](/help/components/dimensions/page-url.md)
* [[!UICONTROL 購入ID]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL 訪問者 ID]](/help/components/dimensions/visitor-id.md)

## サポートされていないディメンション

次のディメンションは、Data Warehouse レポートまたはセグメントでは使用できません。

* [[!UICONTROL 午前／午後]](/help/components/dimensions/am-pm.md)
* [[!UICONTROL 入口ページ ]](/help/components/dimensions/entry-dimensions.md)および[[!UICONTROL 入口ページ元]](/help/components/dimensions/entry-dimensions.md)を除くすべての入口ディメンション（許可されている）
* [[!UICONTROL 終了ページ ]](/help/components/dimensions/exit-dimensions.md)および[[!UICONTROL 終了リンク ]](/help/components/dimensions/exit-link.md)を除くすべての終了ディメンション（許可されている）
* [[!UICONTROL  ヒット深度]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL 再来訪頻度]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL イベント前の時間]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL  ページ滞在時間 – バケット化]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL 訪問当たりの滞在時間 – バケット化]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL すべての検索ページのランク ]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL 階層]](/help/components/dimensions/overview.md#retired-dimensions)変数
* [[!UICONTROL ヒットタイプ]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL 有料検索]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL 直帰数]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL  オプトアウトのトラッキング理由]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL 米国]](/help/components/dimensions/us-states.md)

一部のディメンションはData Warehouse リクエストで使用できますが、セグメント内では使用できません。 詳しくは、[Data Warehouse セグメントの互換性](segment-compatibility.md)を参照してください。

## 非標準の日付書式設定を含むディメンション

次の時間ベースのディメンションはData Warehouse レポートでサポートされていますが、出力では非標準のフォーマットが使用されています。

* [[!UICONTROL 年]](/help/components/dimensions/year.md)
* [[!UICONTROL 四半期]](/help/components/dimensions/quarter.md)
* [[!UICONTROL 月]](/help/components/dimensions/month.md)
* [[!UICONTROL 週]](/help/components/dimensions/week.md)
* [[!UICONTROL 日]](/help/components/dimensions/day.md)
* [[!UICONTROL 時間]](/help/components/dimensions/hour.md)
* [[!UICONTROL 分]](/help/components/dimensions/minute.md)

日付の値は次の形式で出力されます：`1YYMMDDHHMM`

* **年（YY）**: 1900でオフセットされました。 最初の3桁に`1900`を追加します。 例えば、`125` =年&#x200B;**2025**&#x200B;とします。
* **月**: ゼロ ベース。 1月= `00`、2月= `01`、...、12月= `11`。

例えば、「日付範囲週」フィールドに`1260901`が表示されている場合、年は1900 + 126 = **2026**、月は09 = **10月**&#x200B;です。

## Data Warehouseでの指標の定義の違い

* **[[!UICONTROL 訪問回数]](/help/components/metrics/visits.md)**：他のAdobe Analytics ツールの訪問指標とは異なり、永続的でないCookie訪問回数を除外します。
* **[[!UICONTROL 訪問回数 – すべての訪問者]](/help/components/metrics/visits.md)**：永続的ではないCookieを持つ訪問者を含むすべての訪問者をカウントし、Adobe Analyticsの他の場所で使用されている標準の[!UICONTROL 訪問回数]指標に近い値にします。

## サポートされない指標

次の指標は、Data Warehouseでは使用できません。

* [[!UICONTROL  バウンス ]](/help/components/metrics/bounces.md)
* [[!UICONTROL 入口]](/help/components/metrics/entries.md)
* [[!UICONTROL 出口]](/help/components/metrics/exits.md)
* [[!UICONTROL リロード回数]](/help/components/metrics/reloads.md)
* [[!UICONTROL 単一アクセス ]](/help/components/metrics/single-access.md)
* 任意の[[!UICONTROL 滞在時間]](/help/components/metrics/time-spent.md)指標
* [参加](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md) アトリビューションモデルを使用するすべての指標
