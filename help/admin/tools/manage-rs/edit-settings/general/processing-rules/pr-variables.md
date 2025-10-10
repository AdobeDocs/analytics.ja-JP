---
description: 処理ルールを使用して読み取りおよび書き込みが可能な、使用可能なディメンションおよび指標。
subtopic: Processing rules
title: 処理ルールで使用可能なディメンションと指標
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# 処理ルールで使用可能なディメンションと指標

処理ルールを使用して読み取りおよび書き込みが可能な、使用可能なディメンションおよび指標。

## カスタム値とコンテキストデータ

| 値 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **カスタム値** | 読み取り専用 | 処理ルールのアクションに直接入力されたカスタムテキストまたは値。 |
| **連結された値** | 読み取り専用 | 2 つの値を組み合わせて作成される値。 例えば、チャネルとページ名を組み合わせて、サブカテゴリを作成できます。 |

## ヒット属性

| 属性 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **ページ URL** | 読み取り+書き込み | 「[&#x200B; ページ URL](/help/components/dimensions/page-url.md)」ディメンション。 リンクトラッキングヒットは、処理ルールに到達する前にこのディメンションを削除します。 処理ルールを使用してページ URL の値を再挿入した場合、このヒットは [&#x200B; ページイベント &#x200B;](/help/components/metrics/page-views.md) ではなく [&#x200B; ページビュー &#x200B;](/help/components/metrics/page-events.md) と見なされます。 Adobeでは、ページディメンションを変更する前に、そのディメンションの値を確認することをお勧めします。 |
| **ページ名** | 読み取り+書き込み | 「[&#x200B; ページ &#x200B;](/help/components/dimensions/page.md)」ディメンション。 リンクトラッキングヒットは、処理ルールに到達する前にこのディメンションを削除します。 処理ルールを使用してページの値を再挿入した場合、このヒットは [&#x200B; ページイベント &#x200B;](/help/components/metrics/page-views.md) ではなく [&#x200B; ページビュー &#x200B;](/help/components/metrics/page-events.md) と見なされます。 Adobeでは、ページディメンションを変更する前に、そのディメンションの値を確認することをお勧めします。 |
| **レポートスイート ID** | 読み取り専用 | 処理ルールが実行されるレポートスイート。 VISTA ルールを使用する場合など、AppMeasurementを通じて最初に送信されたレポートスイートとは異なる場合があります。 |
| **AppMeasurement コードのバージョン** | 読み取り専用 | イメージリクエストの生成に使用されるAppMeasurement ライブラリのバージョン。 |
| **IP アドレス** | 読み取り専用 | 訪問者の IP アドレス。 |
| **ユーザーエージェント** | 読み取り専用 | 訪問者のユーザーエージェント。 |
| **リファラー** | 読み取り専用 | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| **クエリ文字列パラメーター** | 読み取り専用 | 現在の URL で指定されたクエリ文字列パラメーターの値。 |
| **参照クエリ文字列パラメーター** | 読み取り専用 | 参照 URL で指定したクエリ文字列パラメーターの値。存在しない場合は空の文字列。 |
| **参照元ドメイン** | 読み取り専用 | サブドメインを含む、参照 URL のページドメイン。 |
| **参照ルートドメイン** | 読み取り専用 | サブドメインを除く、参照 URL のページドメイン。 |
| **ページクエリ文字列** | 読み取り専用 | 現在の URL のすべてのクエリ文字列パラメーターとその値。 |
| **参照クエリ文字列** | 読み取り専用 | 参照 URL のすべてのクエリ文字列パラメーターとその値。 |
| **ページパス** | 読み取り専用 | 現在の URL のページパス。 ページパスには、プロトコル、ドメイン、クエリ文字列パラメーターは含まれません。 |
| **ページドメイン** | 読み取り専用 | サブドメインを含む、現在の URL のページドメイン。 ページドメインには、ページパスやクエリ文字列パラメーターは含まれません。 |
| **ページルートドメイン** | 読み取り専用 | 現在の URL のページドメイン（サブドメインを除く）。 |
| **顧客の観点** | 読み取り+書き込み | ヒットがモバイルのバックグラウンドヒットかどうかを判断するフラグ。 |

## コンバージョン変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **eVar 1-250** | 読み取り+書き込み | [eVar](/help/components/dimensions/evar.md) ディメンション。 |
| **Campaign** | 読み取り+書き込み | 「[&#x200B; トラッキングコード &#x200B;](/help/components/dimensions/tracking-code.md)」ディメンション。 |
| **購入 ID** | 読み取り+書き込み | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 実装変数。 |
| **都道府県** | 読み取り+書き込み | （廃止） [`state`](/help/implement/vars/page-vars/state.md) 実装変数。 |
| **郵便番号** | 読み取り+書き込み | 「[&#x200B; 郵便番号 &#x200B;](/help/components/dimensions/zip-code.md)」ディメンション。 |
| **通貨コード** | 読み取り+書き込み | [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 実装変数。 重要：この変数を無効な値に設定すると、ヒットは破棄されます。 |
| **トランザクション ID** | 読み取り+書き込み | [`transactionID`](/help/import/data-sources/transactionid.md) 実装変数。 |

>[!NOTE]
>Adobeでは、処理ルールを使用した [`products`](/help/implement/vars/page-vars/products.md) 実装変数の設定はサポートしていません。

## トラフィック変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **Prop 1-75** | 読み取り+書き込み | [Prop](/help/components/dimensions/prop.md) ディメンション。 |
| **階層 1～5** | 読み取り+書き込み | （廃止） [&#x200B; 階層 &#x200B;](/help/components/dimensions/hierarchy.md) ディメンション。 |
| **サーバー** | 読み取り+書き込み | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| **チャネル** | 読み取り+書き込み | [&#x200B; サイトセクション &#x200B;](/help/components/dimensions/site-section.md) ディメンション。 |

## コンテキスト変数

このレポートスイートが過去 30 日間に表示したすべての [&#x200B; コンテキストデータ変数 &#x200B;](/help/implement/vars/page-vars/contextdata.md)。 使用例については、[&#x200B; 処理ルールの使用例 &#x200B;](pr-use-cases.md) を参照してください。

>[!IMPORTANT]
>
>処理ルールによって特定のコンテキストデータ変数が別の変数（prop やeVarなど）にマッピングされない場合、コンテキストデータ変数の値は恒久的に失われます。

## 成功イベント

処理ルールではイベントを設定できますが、条件として読み取ることはできません。 ルールアクションドロップダウンを **[!UICONTROL イベントを設定]** に設定して、増分可能な指標を確認します。

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **注文件数** | 書き込みのみ | [&#x200B; 注文 &#x200B;](/help/components/metrics/orders.md) 指標。 |
| **買い物かご** | 書き込みのみ | [&#x200B; 買い物かご &#x200B;](/help/components/metrics/carts.md) 指標。 |
| **買い物かご表示** | 書き込みのみ | [&#x200B; 買い物かご表示 &#x200B;](/help/components/metrics/cart-views.md) 指標。 |
| **チェックアウト** | 書き込みのみ | 「[&#x200B; チェックアウト &#x200B;](/help/components/metrics/checkouts.md)」指標。 |
| **買い物かごへの追加** | 書き込みのみ | [&#x200B; 買い物かごへの追加 &#x200B;](/help/components/metrics/cart-additions.md) 指標。 |
| **買い物かごからの削除** | 書き込みのみ | 「[&#x200B; 買い物かごからの削除 &#x200B;](/help/components/metrics/cart-removals.md) 指標。 |
| **イベント 1～1000** | 書き込みのみ | [&#x200B; カスタムイベント &#x200B;](/help/components/metrics/custom-events.md)。 |
| **製品表示** | 書き込みのみ | [&#x200B; 製品表示 &#x200B;](/help/components/metrics/product-views.md) 指標。 |
