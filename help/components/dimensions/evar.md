---
title: eVar
description: レポートで使用できるカスタムディメンション。
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '788'
ht-degree: 100%

---

# eVar

*このヘルプページでは、eVar がディメンションとして機能するしくみについて説明します。eVar の実装方法について詳しくは、実装ユーザーガイドの [eVar](/help/implement/vars/page-vars/evar.md) を参照してください。*

eVar は、好きなだけ使用できるカスタム変数です。[ソリューションデザインのドキュメント](/help/implement/prepare/solution-design.md)がある場合、組織固有のほとんどのディメンションは eVar になります。デフォルトでは、eVar は設定されたヒットを超えても保持されます。レポートスイート設定の「[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)」で、その有効期限と配分をカスタマイズできます。

使用可能な eVar の数は、アドビとの契約によって異なります。アドビとの契約でサポートされている場合は、最大 250 個の eVar を利用できます。

eVar では大文字と小文字が区別されません。大文字と小文字で同じ値を送信する（`"DOG"` と `"Dog"` など）と、Analysis Workspace はそれらを同じディメンション項目にグループ化します。レポートの月の最初に表示される最初の値の場合が使用されます。Data Warehouse には、リクエスト期間中に最初に発生した値が表示されます。

## eVar にデータを入力する

各 eVar は、イメージリクエストの [`v1` - `v250` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。例えば、`v1` クエリー文字列パラメーターで eVar1 のデータを収集し、`v222` クエリー文字列パラメーターで eVar222 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `eVar1` — `eVar250` を使用します。導入のガイドラインについては、『導入ユーザガイド』の [eVar](/help/implement/vars/page-vars/evar.md) を参照してください。

## ディメンション項目

eVar は実装内にカスタム文字列を含むので、各 eVar のディメンション項目は組織によって決定されます。各 eVar の目的と一般的なディメンション項目を必ず[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録してください。

## eVar のしくみ

Adobe Analytics にデータを送信すると、データ収集サーバーでは、ヒットを 1 行のデータ（数百列）に変換します。各 eVar には 2 つの列が割り当てられています。1 つは直接のデータ収集用、もう 1 つは永続値用です。

* 標準の列には、イメージリクエストから Adobe に送信されるデータが含まれます。
* 「post」列には、eVar の有効期限と配分によって異なる、永続的なデータが含まれます。

ほとんどすべての場合、この `post_evar` 列はレポートで使用されます。

### eVar と指標の関連付け

成功イベントと eVar は、様々なイメージリクエストで頻繁に定義されます。この `post_evar` 列では、eVar 値をイベントに結び付け、レポート内のデータを表示できます。訪問の例：

1. 訪問者が貴社のホームページ上のサイトに到達します。
2. サイト内検索で「cats」を検索します。導入では、内部検索に eVar1 を使用します。
3. ユーザーは製品を表示し、チェックアウトプロセスを進めます。

生データの簡易バージョンは、次のようになります。

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* この `visitor_id` 列は、ヒットを同じ訪問者に結び付けます。実際の生データでは、`visid_high` と `visid_low` の連結値で訪問者 ID を判断します。
* この `pagename` 列には、ページディメンションが入力されます。
* eVar1 を明示的に設定した場合、この `evar` 列はヒットを判断します。
* `post_evar1` は、レポートスイート設定で指定された変数の配分と有効期限に応じて、以前の値を使用します。
* `event_list` 列には、すべての指標データが含まれます。この例では、`event1` は「検索」で、他のイベントは標準の買い物かご指標です。実際の生データでは、`event_list` にはコンマ区切りの数字のセットとルックアップテーブルが含まれ、これらの数値と指標を結び付けます。

### データ収集からレポートへの変換

Adobe Analytics のツール（Analysis Workspace など）の動作は、収集されたデータとは異なります。例えば、ディメンションに eVar1、指標に注文を使用してレポートを取得すると、次のようなレポートが表示されます。

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace は、次のロジックを使用してこのレポートを取り込みます。

* すべての `event_list` 値を調べ、`purchase` 値を含むすべてのヒットを選択します。
* これらのヒットの中から、`post_evar1` 値を表示します。

### 配分と有効期限の重要性

配分と有効期限は永続的な値を決定するので、Analytics の実装から最大限の価値を引き出すのに不可欠です。各 eVar に対する複数の値の処理方法（配分）や、eVar が永続的なデータ（有効期限）を停止した場合について、社内で話し合うことを強くお勧めします。

* デフォルトでは、eVar は最後の配分を使用します。新しい値を指定すると、永続値が上書きされます。
* デフォルトでは、eVar は訪問の有効期限を使用します。訪問が終了すると、値は `post_evar` 列の行間でコピーされなくなります。

eVar の配分と有効期限は、レポートスイート設定の「[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)」で変更できます。

## Prop に対する eVar の値

アドビでは、次のサポート対象となるほとんどの場合に eVar の使用をお勧めします。

* レポートでは、eVar に 255 バイトの上限があります。prop の上限は 100 バイトです。
* デフォルトでは、prop は設定されたヒットの後は保持されません。eVar にはカスタムの有効期限があり、eVar がその後のイベントのクレジットを受け取らなくなった時期を判断できます。ただし、[レポートの時間処理](/help/components/vrs/vrs-report-time-processing.md)を使用する場合は、prop と eVar の両方でカスタムアトリビューションモデルを使用できます。
* アドビでは、最大 250 個の eVar をサポートし、prop は 75 個のみサポートします。

Prop と eVar の比較について詳しくは、[prop](prop.md) を参照してください。
