---
title: eVar
description: レポートで使用できるカスタムディメンション。
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 5%

---


# eVar

*このヘルプページでは、eVarがディメンションとして機能する方法を説明します。 eVarの実装方法について詳しくは、『実装ユーザーガイド[](/help/implement/vars/page-vars/evar.md)』のeVarを参照してください。*

eVar は、好きなだけ使用できるカスタム変数です。ソリューションデザインの [ドキュメントがある場合](/help/implement/prepare/solution-design.md)、組織に固有のほとんどのディメンションはeVarになります。 デフォルトでは、eVarは設定されたヒットの後も保持されます。 レポートスイート設定の「 [コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 」で、その有効期限と配分をカスタマイズできます。

使用可能なeVarの数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大250個のeVarを利用できます。

## eVarにデータを入力する

各eVarは、イメージリクエストの [`v1` - `v250` クエリ文字列](/help/implement/validate/query-parameters.md) からデータを収集します。 例えば、 `v1` クエリ文字列パラメーターでeVar1のデータを収集し、 `v222` クエリ文字列パラメーターでeVar222のデータを収集します。

JavaScript変数をデータ収集用のイメージリクエストにコンパイルするAppMeasurementでは、変数 `eVar1` — を使用 `eVar250`します。 導入のガイドラインについては、『導入ユーザガイド [](/help/implement/vars/page-vars/evar.md) 』のeVarを参照してください。

## 分析コード値

eVarは実装内にカスタム文字列を含むので、各eVarのディメンション値は組織によって決定されます。 各eVarの目的と一般的なディメンション値を必ず [ソリューションデザインドキュメントに記録してください](/help/implement/prepare/solution-design.md)。

## eVarの仕組み

Adobe Analyticsにデータを送信すると、データ収集サーバーでは、ヒットが1行のデータ（数百列）に変換されます。 各eVarには2つの列が割り当てられています。 1つは直接データ収集用、もう1つは永続値用です。

* 標準列には、イメージリクエストからアドビに送信されるデータが含まれます。
* 「post」列には永続的なデータが含まれます。これはeVarの有効期限と配分に依存します。

ほとんどすべての状況で、この `post_evar` 列はレポートで使用されます。

### eVarと指標の関連付け

成功イベントとeVarは、様々なイメージリクエストで頻繁に定義されます。 この `post_evar` 列では、eVar値をイベントに結び付け、レポート内のデータを表示できます。 例えば、次のような訪問を行います。

1. 訪問者がホームページ上のサイトに到達します。
2. サイト内検索で「cats」を検索します。 導入では、内部検索にeVar1を使用します。
3. ユーザーは製品を表示し、チェックアウトプロセスを実行します。

生データの簡略化版は、次のようになります。

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* この `visitor_id` 列は、ヒットを同じ訪問者に結び付けます。 実際の生データでは、訪問者IDを連結した値 `visid_high` で `visid_low` 決定します。
* この `pagename` 列は、ページディメンションを設定します。
* この `evar` 列は、eVar1が明示的に設定された場合のヒットを決定します。
* は、レポートスイート設定で設定された変数の配分と有効期限に応じて、以前の値を `post_evar1` 含みます。
* この `event_list` 列には、すべての指標データが含まれます。 この例では、 `event1` は「検索」で、他のイベントは標準買い物かご指標です。 実際の生データでは、数値のコンマ区切り `event_list` のセットが含まれます。このセットには、ルックアップテーブルが含まれ、これらの数値と指標が結び付けられます。

### データ収集からレポートへの変換

Adobe Analyticsのツール(分析ワークスペースなど)は、収集されたデータとは異なります。 例えば、eVar1をディメンションとして使用し、注文を指標としてレポートを取得すると、次のようなレポートが表示されます。

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

分析ワークスペースは、次のロジックを使用してこのレポートを取り込みます。

* すべての値を調べ、値を含むすべてのヒットを選択 `event_list``purchase` します。
* これらのヒットの中で、 `post_evar1` 値を表示します。

### 配分と有効期限の重要性

配分と有効期限は持続的な値を決定するので、Analyticsの実装から最も大きな価値を引き出すのに不可欠です。 各eVarの複数の値の処理方法（配分）や、eVarが永続的なデータ（有効期限）を停止した場合について、社内で話し合うことを強くお勧めします。

* デフォルトでは、eVarは最後の配分を使用します。 新しい値を指定すると、持続的な値が上書きされます。
* デフォルトでは、eVarは訪問の有効期限を使用します。 訪問が終了すると、値は列の行間でコピーされなくなり `post_evar` ます。

eVarの配分と有効期限は、レポートスイート設定の「 [コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 」で変更できます。

## propに対するeVarの値

アドビでは、次のサポート対象となるほとんどの場合にeVarの使用をお勧めします。

* eVarは、レポートで255バイトの制限があります。 propには100バイトの制限があります。
* デフォルトでは、prop は設定されたヒットの後は保持されません。eVar にはカスタムの有効期限があり、eVar がその後のイベントのクレジットを受け取らなくなった時期を判断できます。ただし、 [レポートの時間処理を使用する場合](/help/components/vrs/vrs-report-time-processing.md)、propとeVarの両方でカスタムアトリビューションモデルを使用できます。
* アドビでは、最大250個のeVarをサポートし、propは75個のみサポートします。

prop [とeVarの比較について詳しくは、](prop.md) propを参照してください。
