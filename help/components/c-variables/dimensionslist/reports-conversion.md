---
title: eVar
description: カスタムディメンションをレポートで使用
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*このヘルプページでは、eVarがディメンションとしてどのように機能するかを説明します。 eVarの実装方法について詳しくは、実装ユーザーガ[イドの](/help/implement/vars/page-vars/evar.md)eVarを参照してください。*

eVar は、好きなだけ使用できるカスタム変数です。ソリューションデザイン [ドキュメント](/help/implement/prepare/solution-design.md)、組織に固有のほとんどのディメンションはeVarになります。 デフォルトでは、eVarは設定されたヒットの後も保持されます。 レポートスイートの設定の「コンバージョン変数」で、そ [の有効期限](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) と配分をカスタマイズできます。

## eVarの仕組み

Adobe Analyticsにデータを送信すると、データ収集サーバーは、ヒットを数百列の単一の行のデータに変換します。 各eVarに2つの列が割り当てられます。1つはダイレクトデータ収集用、もう1つは永続値用です。

* 標準の列には、イメージリクエストからアドビに送信されるデータが含まれます。
* 「post」列には永続的なデータが含まれ、eVarの有効期限と配分に依存します。

ほとんどすべての状況で、この列は `post_evar` レポートで使用されます。

### eVarと指標の関連付け

成功イベントとeVarは、異なるイメージリクエストで頻繁に定義されます。 この列で `post_evar` は、eVar値をイベントに結び付け、データをレポートで表示します。 例えば、次のような訪問を行います。

1. 訪問者が貴社のサイトに到達します。ホームページ。
2. サイト内検索を使って「猫」を検索します。 導入では、eVar1が内部検索に設定されます。
3. 彼らは表示を製品にし、チェックアウトプロセスを進めます。

生データの簡略化版は、次のようになります。

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* この列は `visitor_id` ヒットを同じ訪問者に結び付けます。 実際の生データでは、連結された値によって `visid_high` 訪問者ID `visid_low` が決まります。
* この列は、 `pagename` ページディメンションを設定します。
* この列 `evar` は、eVar1が明示的に設定された場合のヒットを決定します。
* は、変 `post_evar1` 数の配分と有効期限の設定に応じて、以前の値を持ちます。
* この列に `event_list` は、すべての指標データが含まれます。 この例では、は「検索」 `event1` で、他のイベントは標準の買い物かご指標です。 実際の生データでは、数 `event_list` 値のコンマ区切りのセットと、それらの数値を指標と結び付ける参照テーブルが含まれます。

### データ収集のレポート

Adobe Analyticsのツール(分析ワークスペースなど)は、収集されたデータを処理します。 例えば、eVar1をディメンションとして使用し、注文件数を指標として使用してレポートを取り込むと、次のようなレポートが表示されます。

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

分析ワークスペースは、次のロジックを使用してこのレポートを取り込みます。

* すべての値を調 `event_list` べ、その値に含まれるすべてのヒットを選 `purchase` 択します。
* これらのヒットのうち、値を表示し `post_evar1` ます。

### 配分と有効期限の重要性

配分と有効期限は持続的な値を決定するので、分析の実装から最も大きな値を得る上で重要です。 各eVarの複数の値の処理方法（配分）と、eVarが永続データ（有効期限）を停止するタイミングについて、社内で話し合うことを強くお勧めします。

* デフォルトでは、eVarは最後の配分を使用します。 新しい値を指定すると、保持された値が上書きされます。
* デフォルトでは、eVarは訪問の有効期限を使用します。 訪問が終了すると、値は列の行間でコピーされなくなり `post_evar` ます。

eVarの配分と有効期限は、レポートスイート設定の「コンバ [ージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 」で変更できます。
