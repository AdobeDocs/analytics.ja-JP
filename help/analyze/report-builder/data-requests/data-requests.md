---
description: 'null'
title: データリクエスト - リクエストウィザード：ステップ 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# データリクエスト - リクエストウィザード：ステップ 1

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート：]**&#x200B;ログイン中のユーザーが権限を持つレポートスイートのリストです。[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **発行リストの上書きを許可**：レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。発行リストは **[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**&#x200B;で設定しておく必要があります。リクエストで指定されたレポートスイートは、発行リストの各受信者に割り当てられるレポートスイート ID に置き換えられます。[発行リストの上書きの許可](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を参照してください。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。レポートタイプの指標およびディメンションは、「[!UICONTROL リクエストウィザード：ステップ 2]」インターフェイスに表示されます。[レポートタイプの選択](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)を参照してください。

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。[レポートの日付の設定](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。[精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)を参照してください。

>[!MORELIKETHIS]
>
>* [データリクエストの作成](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

