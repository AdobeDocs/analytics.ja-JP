---
description: 'null'
seo-description: 'null'
seo-title: データリクエスト - リクエストウィザード：ステップ 1
title: データリクエスト - リクエストウィザード：ステップ 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# データリクエスト - リクエストウィザード：ステップ 1

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート：]**&#x200B;ログイン中のユーザーが権限を持つレポートスイートのリストです。「レポート [スイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)」を参照。

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。詳しくは、 [レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **発行リストの上書きを許可**：レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。Publishing lists are set up in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin tools]**. リクエストで指定されたレポートスイートは、発行リストの各受信者に割り当てられるレポートスイート ID に置き換えられます。詳しくは、[発行リストの上書きの許可](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を参照してください。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。レポートタイプの指標およびディメンションは、「[!UICONTROL リクエストウィザード：ステップ 2]」インターフェイスに表示されます。詳しくは、 「レポ [ートタイプ](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)」

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。レポート [日の設定を参照](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **精度の適用**：日付範囲を分割する単位を指定します。詳しくは、 [精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

>[!MORELIKETHIS]
>
>* [データリクエストの作成](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

