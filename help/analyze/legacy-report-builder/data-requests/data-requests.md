---
description: Report Builder でリクエストを作成する際の最初の手順。
title: データリクエスト - リクエストウィザード：ステップ 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 90%

---

# データリクエスト - リクエストウィザード：ステップ 1

{{legacy-arb}}

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

![&#x200B; リクエストウィザード：ステップ 1 フォームを示すスクリーンショット。](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート：]**&#x200B;ログイン中のユーザーが権限を持つレポートスイートのリストです。[&#x200B; レポートスイートの選択 &#x200B;](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md) を参照してください。

1. **範囲選択アイコン**：レポートスイート ID が記入されたセルを選択します。[&#x200B; レポートスイートの選択 &#x200B;](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md) を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。セグメントはヒット、訪問および訪問者に基づいています。セグメントについて詳しくは、[Analytics セグメントガイド](/help/components/segmentation/seg-home.md)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **公開リストの上書きを許可**：公開リストは、Reports &amp; Analytics の機能で、[&#x200B; 提供が終了 &#x200B;](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?) しました。

1. **レポートタイプ**：データリクエストで取得するベースのレポートを指定します。リクエストごとに 1 つのレポートを指定します。なお、ベースのレポートに対して複数のディメンションと指標を設定できます。レポートタイプの指標およびディメンションは、「[!UICONTROL リクエストウィザード：ステップ 2]」インターフェイスに表示されます。[&#x200B; レポートタイプの選択 &#x200B;](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md) を参照してください。

1. **日付範囲**：リクエストの対象期間を指定します。リクエストの期間には、事前設定、固定、相対など複数のタイプが用意されています。なお、指定できる期間の個数は 366 が最大です。また、セルで指定する日付範囲を選択したり、テンプレートとして日付範囲を保存して再利用したりできます。[レポートの日付の設定](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。[精度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)を参照してください。

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
