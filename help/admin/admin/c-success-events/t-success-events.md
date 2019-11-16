---
description: 成功イベントを設定する方法について手順を説明します。
solution: Analytics
title: 成功イベントの設定
topic: Admin tools
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 成功イベントの設定

成功イベントを設定する方法について手順を説明します。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. レポートスイートの選択.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]**.

   ![手順の結果](assets/success_event_page.png)

1.  「**名前**」列で編集を有効にする各項目の横にあるチェックボックスを選択し、名前を指定します。
1.  「**タイプ**」列でドロップダウンリストを有効にする各項目の横にあるチェックボックスを選択し、タイプを選択します。

   >[!NOTE]
   >
   >イベントタイプを変更する前に、「イベントタイプを変更する」 [を参照してくださ](/help/admin/admin/c-success-events/event-type.md)い。

   ここに挙げた要素について詳しくは、[成功イベントページ - 説明](/help/admin/admin/c-success-events/success-event.md)を参照してください。

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   この設定は、ユーザーインターフェイス内での表示にのみ影響し、指標やイベントのデータ収集には影響しません。[さらに詳しく...](/help/admin/admin/metric-visibility.md)
1. 説明を入力します。
1. イベントを常に記録するかどうかを選択します。
1. パーティシペーション指標を有 [効または無効にしま](/help/components/c-variables/c-metrics/metrics-participation.md)す。

   >[!NOTE]
   >
   >パーティシペーションは、最大100個のカスタムイベントに対して有効にできます。 100 を超える場合は、[計算指標](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html)ビルダーでパーティシペーション指標を作成できます。

1. 「**[!UICONTROL 保存]**」をクリックします。

