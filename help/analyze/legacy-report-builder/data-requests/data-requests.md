---
description: Report Builder でリクエストを作成する際の最初の手順。
title: データリクエスト - リクエストウィザード：ステップ 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
TQID: https://experienceleague.adobe.com/87MzdxBePRZKBttF3P6XhuDq5hR6XpEWaLdrYDMu-5Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 52%

---

# データリクエスト - リクエストウィザード：ステップ 1

{{legacy-arb}}

リクエストウィザード：ステップ 1 のフォームでは、レポートスイート、レポートタイプ、セグメントおよび設定日を選択します。

リクエストウィザードを示す![ スクリーンショット：ステップ 1 フォーム。](assets/rw1_overview.png)

1. **[!UICONTROL レポートスイート]**: ログイン資格情報に基づいて使用可能なレポートスイートのリスト。 [ レポートスイートの選択](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **範囲セレクター**: Excelのセルからレポートスイート IDを選択できます。 [ レポートスイートの選択](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を参照してください。

1. **セグメント**：データのカスタムサブセット、または作成した規則でフィルターされたデータです。 セグメントは、ヒット数、訪問数、訪問者にもとづいています。 セグメントについて詳しくは、[Analytics セグメント化ガイド ](/help/components/segmentation/seg-home.md)を参照してください。

   例えば、[!UICONTROL ページレポート]を実行し、初回訪問件数セグメントを適用できます。

1. **公開リストの上書きを許可**：公開リストはReports &amp; Analyticsの機能であり、[有効期限](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?)が切れています。

1. **レポートタイプ**: データリクエストで実行する基本レポートを指定します。 リクエストごとに1つのレポートを実行すると、そのレポートには1対多のディメンションと1対多の指標を含めることができます。 レポートタイプの指標とディメンションは、[!UICONTROL  リクエストウィザード、ステップ 2] インターフェイスに表示されます。 [ レポートタイプの選択](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)を参照してください。

1. **日付範囲**: リクエストでカバーされる期間を定義します。 プリセット、固定、ローリングなど、いくつかのタイプのリクエスト期間を利用できます。 最大回数は366回です。 セルで指定された日付範囲を選択し、後で使用するために日付範囲をテンプレートとして保存することもできます。  [レポートの日付の設定](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照してください。

1. **精度の適用**：日付範囲を分割する単位を指定します。 [精度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)を参照してください。

## トラブルシューティング

モニターの設定間を移動するユーザーに対しては特に、リクエストウィザードが画面外に表示されることがあります。 例えば、職場ではドッキングステーションを、自宅ではノートパソコンの画面を使用するとします。 リクエストウィザードが既に開いている間に「作成」を再度クリックすると、

「新しいリクエストウィザードを開始する前に、まずリクエストウィザードの処理を完了する必要があります。」というエラーが表示されます。

この問題は、リクエストウィザードを画面に戻すと解決します。

1. Microsoft Excel を開き、Report Builder にログインします。
2. 「[!UICONTROL 作成]」をクリックすると、リクエストウィザードが画面外に表示されます。
3. `[Alt]` + `[Space]` を押します。
4. `[M]` を押します。.
5. いずれかの矢印キーを押します。
6. マウスを移動します。これにより、リクエストウィザードがカーソルに接続されます。
7. マウスをクリックして、リクエストウィザードを画面上で離します。
