---
description: 'null'
title: データリクエスト - リクエストウィザード：ステップ 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 72%

---


# データリクエスト - リクエストウィザード：ステップ 1

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート：]**&#x200B;ログイン中のユーザーが権限を持つレポートスイートのリストです。詳しくは、[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。詳しくは、[レポートスイートの選択](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **発行リストの上書きを許可**：レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。発行リストは **[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**&#x200B;で設定しておく必要があります。リクエストで指定されたレポートスイートは、発行リストの各受信者に割り当てられるレポートスイート ID に置き換えられます。詳しくは、[発行リストの上書きの許可](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を参照してください。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。レポートタイプの指標およびディメンションは、「[!UICONTROL リクエストウィザード：ステップ 2]」インターフェイスに表示されます。詳しくは、[レポートタイプの選択](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)を参照してください。

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。[レポートの日付の設定](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。「 [精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)」を参照してください。

## トラブルシューティング

要求ウィザードが画面外に表示されることがあります。特に、モニターの設定間を移動するユーザーに対しては、このウィザードが表示されます。 例えば、職場ではドッキングステーションを、自宅ではノートパソコンの画面を使用します。 要求ウィザードが既に開いている間に[作成]を再度クリックすると、次のエラーが表示されます。

&quot;新しい要求ウィザードを開始する前に、まず要求ウィザードの処理を完了する必要があります。&quot;

この問題は、リクエストウィザードを画面に戻すと解決します。

1. Microsoft Excelを開き、Report Builderにログインします。
2. 「 [!UICONTROL 作成]」をクリックすると、リクエストウィザードが画面に表示されません。
3. 押す `[Alt]` + `[Space]`.
4. 押す `[M]`.
5. いずれかの矢印キーを押します。
6. マウスを移動します。これにより、リクエストウィザードがカーソルに接続されます。
7. マウスをクリックして、要求ウィザードを画面上で離します。
