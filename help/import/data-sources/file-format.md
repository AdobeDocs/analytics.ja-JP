---
title: データソースファイルの形式
description: データソースで使用するファイルを正しく生成する。
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# データソースファイルの形式

データソースファイルには次のプロパティがあります。

* ファイルは、 `.txt` 形式
* コメント付きの行は「`#`「 」、およびはオプションです。
* 最初のコメントされていない行には、ファイルのヘッダーが含まれます。
* 各行の最初の値は日付で、形式が使用されます `MM/DD/YYYY` または `MM/DD/YYYY/HH/mm/SS`.
* ヘッダーを含むすべての行の値はタブ区切りです。
* 各行には、少なくとも 1 つのディメンションと 1 つの指標が必要です。

## コメント

「`#`&#39;はコメントです。 データソーステンプレートファイルをダウンロードする場合、最初の 2 行はコメントです。

* 最初のコメントは、データソース用に設定したテンプレートのタイプ、データソースを作成したバックエンドユーザー ID、データソース ID を示します。
* 2 つ目のコメントは、テンプレートファイルに含まれる各ヘッダーのわかりやすい名前を提供します。

ファイルの処理時には、すべてのコメント行がAdobeによって無視されるので、テンプレートのコメントを削除したり、ファイル全体に独自のコメントを追加したりできます。 コメントを付けることができるのは全行のみです。個々のフィールドや部分的な行をコメントアウトすることはできません。

## ヘッダー

データソースファイルをアップロードする場合、列ヘッダーが必要です。 これらの列ヘッダーでは大文字と小文字が区別されませんが、必要なスペース ( 例： `eVar1` は無効なヘッダーですが、 `EVAR 1` は有効です )。 列ヘッダーは、すべてのレポートスイートに適用されます。 次の表を使用して、データソースファイルの各ヘッダーが正しく設定されていることを確認します。

>[!TIP]
>
>データソースファイルに正しいヘッダーが含まれている場合は、データソースファイルを最初から作成することができます。 1 つのファイルに含めることができるヘッダーの数に制限はありません。ただし、各行には最大 4096 バイトまでしか指定できません。

| ディメンション | データソースヘッダー |
| --- | --- |
| [カテゴリ](/help/components/dimensions/category.md) | `Category` |
| [eVar1～eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [マーケティングチャネル](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [マーケティングチャネルの詳細](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [製品](/help/components/dimensions/product.md) | `Product` |
| [トラッキングコード](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [トランザクション ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [郵便番号](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimensionと指標は同じヘッダー行に入ります。

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

Adobeは、他のディメンションや指標のデータソースをサポートしていません。 上記の表以外の変数が必要な場合は、 [一括データ挿入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) 代わりに、

## 日付

各行の最初の値 **必須** を日付にします。 日付の形式は、次のいずれかの形式で指定する必要があります。

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

時間/分/秒を省略すると、その日のタイムスタンプが午後 12 時に自動的に設定されます。

1 つのデータソースファイルで、最大 90 日までの一意の日数をサポートします。 90 日を超える一意の日数をアップロードに含める場合は、データを複数のファイルに分割します。

## Dimensionと指標データ

各行の日付以降の値には、アップロードするデータが含まれます。 各行は、それぞれのタイムスタンプに対応します。 各行に同じ数のタブが存在することを確認します。 列は任意の順序で指定できます。各行のデータが上部のヘッダーと揃っていることを確認します。 1 つの行に指定できるデータの最大量は 4096 バイトです。

Dimensionデータにセミコロン (`;`) をクリックします。 セミコロンを含む行はスキップされます。

## 次の手順

[ファイルのアップロード](file-upload.md):取り込むデータソースファイルをAdobeでアップロードするプロセスを説明します。
