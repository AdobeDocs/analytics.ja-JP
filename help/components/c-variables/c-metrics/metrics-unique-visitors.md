---
description: バージョン 14 では、実訪問者は、特定の期間内で初めてサイトを訪れた訪問者を指します。例えば、実訪問者が 1 週間に 10 回サイトを訪問する場合がありますが、期間が週の場合、その週で 1 人の実訪問者が 1 回だけカウントされます。その週が過ぎると、その実訪問者は別の期間で再びカウントできます。
seo-description: バージョン 14 では、実訪問者は、特定の期間内で初めてサイトを訪れた訪問者を指します。例えば、実訪問者が 1 週間に 10 回サイトを訪問する場合がありますが、期間が週の場合、その週で 1 人の実訪問者が 1 回だけカウントされます。その週が過ぎると、その実訪問者は別の期間で再びカウントできます。
seo-title: 実訪問者数
solution: Analytics
title: 実訪問者数
topic: 指標
uuid: ae210698-99f9-485e- a640- c7520807adc7
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# 実訪問者数

バージョン 14 では、実訪問者は、特定の期間内で初めてサイトを訪れた訪問者を指します。例えば、実訪問者が 1 週間に 10 回サイトを訪問する場合がありますが、期間が週の場合、その週で 1 人の実訪問者が 1 回だけカウントされます。その週が過ぎると、その実訪問者は別の期間で再びカウントできます。

## バージョン 14 とバージョン 15 の違い

Version 14 does not remove duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics from classifications-based reports. 例えば、2 つのビデオクリップが同じ分類に属する場合、両方のビデオクリップを見た単一の訪問者は分類に基づくレポートで 2 件の[!UICONTROL 訪問回数]および[!UICONTROL 実訪問者数]として表されます。

バージョン 15 では、分類に基づくレポートから重複する[!UICONTROL 訪問回数]および[!UICONTROL 実訪問者数]が削除されます。したがって、[!UICONTROL 訪問回数]および[!UICONTROL 訪問者数]がより正確に測定されますが、分類に基づくレポートでの[!UICONTROL 訪問回数]指標および[!UICONTROL 実訪問者数]指標は、通常アップグレード前に収集されたデータに比べて少なくなります。

| 使用 | 説明 |
|---|---|
| トラフィック | 訪問者とは、Web サイトを訪れた人のことです。持続的 cookie は必要としません。 |
| コンバージョン | 訪問者とは、Web サイトを訪れた人のことです。コンバージョン関連のイベントまたは活動が発生したときにカウントされます。 |
| Ad Hoc Analysis | 訪問者とは、Web サイトを訪れた人のことです。持続的 cookie は必要としません。 |

[実訪問者数レポート-バージョン15およびAd Hoc Analysisを参照](../../../components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md#concept_877141D6D1E743DA9FAB41C72A8121C7)してください。

>[!MORE_LIKE_THIS]
>
>* [日別訪問者数](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

