---
description: 成功イベントを設定する方法について手順を説明します。
title: 成功イベントの設定
topic: Admin tools
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# 成功イベントの設定

成功イベントを設定する方法について手順を説明します。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. レポートスイートを選択します。
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![手順の結果](assets/success_event_page.png)

1. In the **[!UICONTROL Name]** column, select the checkbox next each item to enable editing, then specify the desired name.
1. In the **[!UICONTROL Type]** column, select the checkbox next each item to enable the drop-down list, then select the desired type.

   >[!NOTE]
   >
   >イベントタイプを変更する前に、[イベントタイプを変更する](/help/admin/admin/c-success-events/event-type.md)を参照してください。

   ここに挙げた要素について詳しくは、[成功イベントページ - 説明](/help/admin/admin/c-success-events/success-event.md)を参照してください。

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   この設定は、ユーザーインターフェイス内での表示にのみ影響し、指標やイベントのデータ収集には影響しません。[さらに詳しく...](/help/admin/admin/metric-visibility.md)
1. 説明を入力します。
1. イベントを常に記録するかどうかを選択します。
1. [パーティシペーション指標](/help/components/c-variables/c-metrics/metrics-participation.md)を有効または無効にします。

   >[!NOTE]
   >
   >パーティシペーションは、最大 100 個のカスタムイベントに対して有効にすることができます。100 を超える場合は、[計算指標](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/participation-metric.html)ビルダーでパーティシペーション指標を作成できます。

1. クリック **[!UICONTROL Save]**.

