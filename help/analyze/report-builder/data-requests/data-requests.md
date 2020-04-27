---
description: 'null'
title: データリクエスト - リクエストウィザード：ステップ 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# データリクエスト - リクエストウィザード：ステップ 1

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**:リストは、ログイン資格情報に基づいて利用できるレポートスイートの情報です。 See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。詳しくは、[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/)を参照してください。

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **発行リストの上書きを許可**：レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。Publishing lists are set up in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. リクエストで指定されたレポートスイートは、発行リストの各受信者に割り当てられるレポートスイート ID に置き換えられます。詳しくは、[発行リストの上書きの許可](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を参照してください。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。[レポートの日付の設定](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。「精度」を参 [照してくださ](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)い。

>[!MORELIKETHIS]
>
>* [データリクエストの作成](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

