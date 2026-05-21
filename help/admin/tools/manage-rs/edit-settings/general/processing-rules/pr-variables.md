---
description: 処理ルールを使用して読み取りおよび書き込みできる、使用可能なディメンションと指標。
subtopic: Processing rules
title: 処理ルールで使用できるディメンションと指標
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
TQID: https://experienceleague.adobe.com/FFwTZQBj3LWLQdASF91ZwMis12EuOP5a1VhHyxUqXm0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 15%

---

# 処理ルールで使用できるディメンションと指標

処理ルールを使用して読み取りおよび書き込みできる、使用可能なディメンションと指標。

## カスタム値とコンテキストデータ

| 値 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **カスタム値** | 読み取り専用 | 処理ルールのアクションで直接入力されるカスタムテキストまたは値。 |
| **連結された値** | 読み取り専用 | 2つの値を組み合わせて作成される値。 例えば、チャネル名とページ名を組み合わせてサブカテゴリを作成できます。 |

## ヒット属性

| 属性 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **ページ URL** | 読み取り+書き込み | 「[ページ URL](/help/components/dimensions/page-url.md)」ディメンション。 リンクトラッキングは、処理ルールに達する前にこのディメンションをストリップします。 処理ルールを使用してページ URL値を再挿入すると、ヒットは[ ページイベント ](/help/components/metrics/page-events.md)ではなく[ ページビュー](/help/components/metrics/page-views.md)と見なされます。 Adobeでは、ページディメンションの値を変更する前に確認することをお勧めします。 |
| **ページ名** | 読み取り+書き込み | 「[ページ](/help/components/dimensions/page.md)」ディメンション。 リンクトラッキングは、処理ルールに達する前にこのディメンションをストリップします。 処理ルールを使用してページ値を再挿入すると、ヒットは[ ページイベント ](/help/components/metrics/page-events.md)ではなく[ ページビュー](/help/components/metrics/page-views.md)と見なされます。 Adobeでは、ページディメンションの値を変更する前に確認することをお勧めします。 |
| **レポートスイート ID** | 読み取り専用 | 処理ルールが実行されるレポートスイート。 このレポートスイートは、VISTA ルールを使用する場合など、AppMeasurementを通じて最初に送信されたレポートスイートとは異なる場合があります。 |
| **AppMeasurement コード バージョン** | 読み取り専用 | イメージリクエストの生成に使用されるAppMeasurement ライブラリバージョン。 |
| **IP アドレス** | 読み取り専用 | 訪問者のIP アドレス。 |
| **ユーザーエージェント** | 読み取り専用 | 訪問者のユーザーエージェント。 |
| **リファラー** | 読み取り専用 | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| **クエリー文字列パラメーター** | 読み取り専用 | 現在のURLで指定されたクエリ文字列パラメーターの値。 |
| **クエリ文字列パラメーター**&#x200B;を参照しています | 読み取り専用 | 参照URLに指定されたクエリ文字列パラメーターの値、または存在しない場合は空の文字列。 |
| **参照元ドメイン** | 読み取り専用 | 参照URLのページドメイン （サブドメインを含む）。 |
| **ルートドメインを参照しています** | 読み取り専用 | 参照URLのページドメイン （サブドメインを除く）。 |
| **ページクエリ文字列** | 読み取り専用 | 現在のURL内のすべてのクエリ文字列パラメーターとその値。 |
| **クエリ文字列を参照しています** | 読み取り専用 | 参照URLのすべてのクエリ文字列パラメーターとその値。 |
| **ページパス** | 読み取り専用 | 現在のURLのページパス。 ページパスには、プロトコル、ドメイン、クエリ文字列のパラメーターが含まれていません。 |
| **ページドメイン** | 読み取り専用 | サブドメインを含む、現在のURLのページドメイン。 ページドメインには、ページパスやクエリ文字列のパラメーターが含まれていません。 |
| **ページのルートドメイン** | 読み取り専用 | サブドメインを除く、現在のURLのページドメイン。 |
| **顧客の視点** | 読み取り+書き込み | ヒットがモバイルのバックグラウンドヒットかどうかを判断するフラグ。 |

## コンバージョン変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **eVar 1-250** | 読み取り+書き込み | 「[eVar](/help/components/dimensions/evar.md)」ディメンション。 |
| **Campaign** | 読み取り+書き込み | 「[トラッキングコード](/help/components/dimensions/tracking-code.md)」ディメンション。 |
| **購入ID** | 読み取り+書き込み | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 実装変数。 |
| **都道府県** | 読み取り+書き込み | （廃止）実装変数[`state`](/help/implement/vars/page-vars/state.md)です。 |
| **郵便番号** | 読み取り+書き込み | 「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンション。 |
| **通貨コード** | 読み取り+書き込み | [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 実装変数。 重要：この変数を無効な値に設定すると、ヒットは破棄されます。 |
| **トランザクション ID** | 読み取り+書き込み | [`transactionID`](/help/import/data-sources/transactionid.md) 実装変数。 |

>[!NOTE]
>Adobeでは、処理ルールを使用して[`products`](/help/implement/vars/page-vars/products.md)実装変数を設定することはできません。

## トラフィック変数

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **プロップ 1-75** | 読み取り+書き込み | 「[Prop](/help/components/dimensions/prop.md)」ディメンション。 |
| **階層1-5** | 読み取り+書き込み | （廃止） [階層](/help/components/dimensions/hierarchy.md) ディメンション。 |
| **サーバー** | 読み取り+書き込み | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| **チャネル** | 読み取り+書き込み | 「[サイトセクション](/help/components/dimensions/site-section.md)」ディメンション。 |

## コンテキスト変数

このレポートスイートが過去30日間に確認したすべての[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)。 使用例については、[処理ルールの使用例](pr-use-cases.md)を参照してください。

>[!IMPORTANT]
>
>処理ルールが特定のコンテキストデータ変数を別の変数（propやeVarなど）にマッピングしない場合、コンテキストデータ変数内の値は永続的に失われます。

## 成功イベント

処理ルールはイベントを設定できますが、条件として読み取ることはできません。 ルールアクション ドロップダウンを&#x200B;**[!UICONTROL イベントを設定]**&#x200B;に設定すると、増分可能な指標を確認できます。

| 変数 | 読み取り/書き込みステータス | 説明 |
| --- | --- | --- |
| **注文件数** | 書き込み専用 | [注文](/help/components/metrics/orders.md)指標。 |
| **買い物かご** | 書き込み専用 | [買い物かご](/help/components/metrics/carts.md)指標 |
| **買い物かご表示** | 書き込み専用 | [買い物かご表示](/help/components/metrics/cart-views.md)指標。 |
| **チェックアウト** | 書き込み専用 | [ チェックアウト ](/help/components/metrics/checkouts.md)指標。 |
| **買い物かごへの追加** | 書き込み専用 | [買い物かごの追加](/help/components/metrics/cart-additions.md)指標。 |
| **買い物かごからの削除** | 書き込み専用 | [買い物かごからの削除](/help/components/metrics/cart-removals.md)指標。 |
| **イベント 1-1000** | 書き込み専用 | [カスタムイベント](/help/components/metrics/custom-events.md)。 |
| **製品表示** | 書き込み専用 | [製品ビュー](/help/components/metrics/product-views.md)指標。 |
