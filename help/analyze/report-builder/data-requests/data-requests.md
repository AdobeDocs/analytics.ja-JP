---
description: Report Builderでリクエストを作成する場合の最初の手順。
title: データリクエスト - リクエストウィザード：ステップ 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 96%

---


# データリクエスト - リクエストウィザード：ステップ 1

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート：]**&#x200B;ログイン中のユーザーが権限を持つレポートスイートのリストです。 [レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。詳しくは、[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **発行リストの上書きを許可**：レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。発行リストは **[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**&#x200B;で設定しておく必要があります。リクエストで指定されたレポートスイートは、発行リストの各受信者に割り当てられるレポートスイート ID に置き換えられます。詳しくは、[発行リストの上書きの許可](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を参照してください。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。レポートタイプの指標およびディメンションは、「[!UICONTROL リクエストウィザード：ステップ 2]」インターフェイスに表示されます。詳しくは、[レポートタイプの選択](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)を参照してください。

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。[レポートの日付の設定](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。[精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)を参照してください。

## トラブルシューティング

モニターの設定間を移動するユーザーに対しては特に、リクエストウィザードが画面外に表示されることがあります。例えば、職場ではドッキングステーションを、自宅ではノートパソコンの画面を使用するとします。リクエストウィザードが既に開いている間に「作成」を再度クリックすると、

「新しいリクエストウィザードを開始する前に、まずリクエストウィザードの処理を完了する必要があります。」というエラーが表示されます。

この問題は、リクエストウィザードを画面に戻すと解決します。

1. Microsoft Excel を開き、Report Builder にログインします。
2. 「[!UICONTROL 作成]」をクリックすると、リクエストウィザードが画面外に表示されます。
3. `[Alt]` + `[Space]` を押します。
4. `[M]` を押します。.
5. いずれかの矢印キーを押します。
6. マウスを移動します。これにより、リクエストウィザードがカーソルに接続されます。
7. マウスをクリックして、リクエストウィザードを画面上で離します。
