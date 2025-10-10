---
title: データソースファイルの形式
description: データソースで使用するファイルを正しく生成する。
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: cc25fe304d9cab3db3fa2ddd306338ff3bb88a55
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 5%

---

# データソースファイルの形式

データソースファイルには次のプロパティがあります。

* ファイルは `.txt` 形式です。
* コメントされた行は&#39;`#`&#39;で始まり、オプションです。
* コメントなしの最初の行には、ファイルのヘッダーが含まれます。
* 各行の最初の値は日付で、`MM/DD/YYYY` または `MM/DD/YYYY/HH/mm/SS` の形式を使用します。
* ヘッダーを含むすべての行の値は、タブで区切られます。
* 各行には、少なくとも 1 つのディメンションと 1 つの指標が必要です。

## コメント

&#39;`#`&#39;で始まる行はすべてコメントです。 データソーステンプレートファイルをダウンロードする場合、最初の 2 行はコメントです。

* 最初のコメントは、データソースに対して設定したテンプレートのタイプ、データソースを作成したバックエンドユーザー ID およびデータソース ID を示します。
* 2 番目のコメントは、テンプレートファイルに含まれる各ヘッダーのわかりやすい名前を指定します。

Adobeでは、ファイルが処理されるときに、すべてのコメント行が無視されるので、テンプレートのコメントを削除したり、ファイル全体で独自のコメントを追加したりできます。 完全な行のみをコメントできます。個々のフィールドや行の一部をコメントアウトすることはできません。

## ヘッダー

データファイルをアップロードする場合、列ヘッダーが必要です。 これらの列ヘッダーでは大文字と小文字が区別されませんが、必須のスペースが必要です（例えば、`eVar1` は無効なヘッダーですが、`EVAR 1` は有効です）。 列ヘッダーは、すべてのレポートスイートに適用されます。 次の表を使用して、データ ソース ファイルの各ヘッダーが正しく設定されていることを確認してください。

>[!TIP]
>
>データ ソース ファイルに正しいヘッダーが含まれている場合は、ゼロからデータ ソース ファイルを作成できます。 1 つのファイル内に含めることができるヘッダーの数に制限はありません。ただし、各行に含めることができるバイト数は最大 4096 バイトまでです。

| ディメンション | データソースヘッダー |
| --- | --- |
| [カテゴリ](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [&#x200B; マーケティングチャネル &#x200B;](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [&#x200B; マーケティングチャネルの詳細 &#x200B;](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [製品](/help/components/dimensions/product.md) | `Product` |
| [トラッキングコード](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [トランザクション ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [郵便番号](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

ディメンションと指標は、同じヘッダー行に配置されます。

| 指標 | データソースヘッダー |
| --- | --- |
| [買い物かごへの追加](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [買い物かごからの削除](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [買い物かご表示](/help/components/metrics/cart-views.md) | `Cart Views` |
| [買い物かご](/help/components/metrics/carts.md) | `Cart Opens` |
| [チェックアウト](/help/components/metrics/checkouts.md) | `Checkouts` |
| [カスタムイベント](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [注文件数](/help/components/metrics/orders.md) | `Orders` |
| [売上高](/help/components/metrics/revenue.md) | `Price` |
| [単位](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobeは、他のディメンションや指標のデータソースをサポートしていません。 上記の表にリストされている以外の変数が必要な場合は、代わりに [Bulk data insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を使用することを検討してください。

## 日付

各行の最初の値 **必須** は日付です。 日付形式は、次のいずれかの形式にする必要があります。

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

時/分/秒を省略すると、その日のタイムスタンプは自動的に午後 12 時に設定されます。

1 つのデータソースファイルでサポートできる一意の日数は最大 90 日です。 一意のアップロード日数を 90 日を超える場合は、データを複数のファイルに分割します。

## Dimensionと指標データ

各行の日付より後の後続の値には、アップロードするデータが含まれます。 各行は、それぞれのタイムスタンプに対応します。 すべての行に同じ数のタブが存在することを確認します。 列は任意の順序で配置できます。各行のデータが上部のヘッダーに揃っていることを確認してください。 1 行に含めることができるデータの最大量は 4096 バイトです。

Dimension データにセミコロン （`;`）を含めることはできません。 セミコロンを含む行はスキップされます。

## 次の手順

[&#x200B; ファイルのアップロード &#x200B;](file-upload.md):Adobeで取り込むためにデータソースファイルをアップロードするプロセスを説明します。
