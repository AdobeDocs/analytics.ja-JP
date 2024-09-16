---
description: 処理ルールを使用して読み取りおよび書き込みが可能な、使用可能なディメンションおよび指標。
subtopic: Processing rules
title: 処理ルールで使用可能なディメンション
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 02fea12d1286fdf2b8cd075c8bcccca0d196cad2
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 14%

---

# 処理ルールで使用可能なDimensionと指標

処理ルールを使用して読み取りおよび書き込みが可能な、使用可能なディメンションおよび指標。

## カスタム値とコンテキストデータ

| 値 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| カスタム値 | 読み取り専用 | 処理ルールのアクションに直接入力されたカスタムテキストまたは値。 |
| 連結された値 | 読み取り専用 | 2 つの値を組み合わせて作成される値。 例えば、チャネルとページ名を組み合わせて、サブカテゴリを作成できます。 |

## ヒット属性

| 属性 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| ページ URL | 読み取り+書き込み | 「[ ページ URL](/help/components/dimensions/page-url.md)」ディメンション。 リンクトラッキングヒットは、処理ルールに到達する前にこのディメンションを削除します。 処理ルールを使用してページ URL の値を再挿入した場合、このヒットは [ ページイベント ](/help/components/metrics/page-views.md) ではなく [ ページビュー ](/help/components/metrics/page-events.md) と見なされます。 Adobeは、ページディメンションを変更する前に、そのディメンションの値を確認することをお勧めします。 |
| ページ名 | 読み取り+書き込み | 「[ ページ ](/help/components/dimensions/page.md)」ディメンション。 リンクトラッキングヒットは、処理ルールに到達する前にこのディメンションを削除します。 処理ルールを使用してページの値を再挿入した場合、このヒットは [ ページイベント ](/help/components/metrics/page-views.md) ではなく [ ページビュー ](/help/components/metrics/page-events.md) と見なされます。 Adobeは、ページディメンションを変更する前に、そのディメンションの値を確認することをお勧めします。 |
| レポートスイート ID | 読み取り専用 | 処理ルールが実行されるレポートスイート。 このレポートスイートは、VISTA ルールを使用する場合など、AppMeasurementを通じて最初に送信されたレポートスイートとは異なる場合があります。 |
| AppMeasurementコードのバージョン | 読み取り専用 | イメージリクエストの生成に使用されるAppMeasurementライブラリのバージョン。 |
| IP アドレス | 読み取り専用 | 訪問者の IP アドレス。 |
| ユーザーエージェント | 読み取り専用 | 訪問者のユーザーエージェント。 |
| リファラー | 読み取り専用 | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| クエリ文字列パラメーター | 読み取り専用 | 現在の URL で指定されたクエリ文字列パラメーターの値。 |
| 参照クエリ文字列パラメーター | 読み取り専用 | 参照 URL で指定したクエリ文字列パラメーターの値。存在しない場合は空の文字列。 |
| 参照ドメイン | 読み取り専用 | サブドメインを含む、参照 URL のページドメイン。 |
| 参照ルートドメイン | 読み取り専用 | サブドメインを除く、参照 URL のページドメイン。 |
| ページクエリ文字列 | 読み取り専用 | 現在の URL のすべてのクエリ文字列パラメーターとその値。 |
| 参照クエリ文字列 | 読み取り専用 | 参照 URL のすべてのクエリ文字列パラメーターとその値。 |
| ページパス | 読み取り専用 | 現在の URL のページパス。 ページパスには、プロトコル、ドメイン、クエリ文字列パラメーターは含まれません。 |
| ページドメイン | 読み取り専用 | サブドメインを含む、現在の URL のページドメイン。 ページドメインには、ページパスやクエリ文字列パラメーターは含まれません。 |
| ページルートドメイン | 読み取り専用 | 現在の URL のページドメイン（サブドメインを除く）。 |
| 顧客の観点 | 読み取り+書き込み | ヒットがモバイルのバックグラウンドヒットかどうかを判断するフラグ。 |

## コンバージョン変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| eVar 1 ～ 250 | 読み取り+書き込み | [eVar](/help/components/dimensions/evar.md) ディメンション。 |
| キャンペーン | 読み取り+書き込み | 「[ トラッキングコード ](/help/components/dimensions/tracking-code.md)」ディメンション。 |
| 購入 ID | 読み取り+書き込み | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 実装変数。 |
| 都道府県 | 読み取り+書き込み | [`state`](/help/implement/vars/page-vars/state.md) 実装変数は廃止されました。 |
| 郵便番号 | 読み取り+書き込み | 「[ 郵便番号 ](/help/components/dimensions/zip-code.md)」ディメンション。 |
| 通貨コード | 読み取り+書き込み | [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 実装変数。 重要：この変数を無効な値に設定すると、ヒットは破棄されます。 |
| トランザクション ID | 読み取り+書き込み | [`transactionID`](/help/import/data-sources/transactionid.md) 実装変数。 |

>[!NOTE]
>Adobeでは、処理ルールを使用した [`products`](/help/implement/vars/page-vars/products.md) 実装変数の設定はサポートしていません。

## トラフィック変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| Prop 1 ～ 75 | 読み取り+書き込み | [Prop](/help/components/dimensions/prop.md) ディメンション。 |
| 階層 1 ～ 5 | 読み取り+書き込み | [ 階層 ](/help/components/dimensions/hierarchy.md) ディメンション。 |
| サーバー | 読み取り+書き込み | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| チャネル | 読み取り+書き込み | [ サイトセクション ](/help/components/dimensions/site-section.md) ディメンション。 |

## コンテキスト変数

このレポートスイートが以前のイメージリクエストで見たすべての [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)。 処理ルールによってコンテキストデータが別の変数に配置されない場合、そのデータは恒久的に失われます。 使用例については、[ コンテキストデータ変数のeVarへのコピー ](processing-rules-examples/processing-rules-copy-context-data.md) および [ コンテキストデータ変数を使用したイベントの設定 ](processing-rules-examples/processing-rules-copy-context-data-event.md) を参照してください。

## 成功イベント

処理ルールではイベントを設定できますが、条件として読み取ることはできません。 ルールアクションドロップダウンを **[!UICONTROL イベントを設定]** に設定して、増分する使用可能な指標を確認します。

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| 注文件数 | 書き込みのみ | [ 注文 ](/help/components/metrics/orders.md) 指標。 |
| 買い物かご | 書き込みのみ | [ 買い物かご ](/help/components/metrics/carts.md) 指標。 |
| 買い物かご表示 | 書き込みのみ | [ 買い物かご表示 ](/help/components/metrics/cart-views.md) 指標。 |
| チェックアウト | 書き込みのみ | 「[ チェックアウト ](/help/components/metrics/checkouts.md)」指標。 |
| 買い物かごへの追加 | 書き込みのみ | [ 買い物かごへの追加 ](/help/components/metrics/cart-additions.md) 指標。 |
| 買い物かごからの削除 | 書き込みのみ | 「[ 買い物かごからの削除 ](/help/components/metrics/cart-removals.md) 指標。 |
| イベント 1 ～ 1000 | 書き込みのみ | [ カスタムイベント ](/help/components/metrics/custom-events.md)。 |
| 製品表示 | 書き込みのみ | [ 製品表示 ](/help/components/metrics/product-views.md) 指標。 |

