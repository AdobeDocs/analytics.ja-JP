---
title: データソースファイル形式
description: データソースで使用するファイルを正しく生成します。
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/aOyIlKV8OwvmigJ7RFcNQsrsBiHbrC0a-IPN4xR0OZc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 546
ht-degree: 7%

---

# データソースファイル形式

データソースファイルには、次のプロパティがあります。

* ファイルは`.txt`形式です。
* コメント行は&#39;`#`&#39;で始まり、オプションです。
* 最初のコメントなし行には、ファイルのヘッダーが含まれています。
* 各行の最初の値は日付で、形式は`MM/DD/YYYY`または`MM/DD/YYYY/HH/mm/SS`を使用します。
* ヘッダーを含むすべての行の値はタブ区切りです。
* すべての行には、少なくとも1つのディメンションと1つの指標が必要です。

## コメント

&#39;`#`&#39;で始まるすべての行はコメントです。 データソーステンプレートファイルをダウンロードする場合、最初の2行はコメントです。

* 最初のコメントは、データソース用に設定したテンプレートのタイプ、データソースを作成したバックエンドユーザーID、データソース IDを示します。
* 2つ目のコメントは、テンプレートファイルに含まれる各ヘッダーのわかりやすい名前を提供します。

ファイルの処理時に、すべてのコメント行がAdobeによって無視されるので、テンプレートコメントを削除したり、ファイル全体に独自のコメントを追加したりできます。 コメントできるのは完全な行のみです。個々のフィールドや行の一部をコメントすることはできません。

## ヘッダー

データソースファイルをアップロードする場合は、列ヘッダーが必要です。 これらの列ヘッダーでは大文字と小文字が区別されませんが、必須スペースが必要です（例：`eVar1`は無効なヘッダーで、`EVAR 1`は有効です）。 列ヘッダーはすべてのレポートスイートに適用されます。 次の表を使用して、データソースファイルの各ヘッダーが正しく設定されていることを確認します。

>[!TIP]
>
>データソースファイルに正しいヘッダーを含める場合は、データソースファイルをゼロから作成できます。 1つのファイルに含めることができるヘッダーの数に制限はありませんが、各行には最大4096 バイトしか含めることができません。

| ディメンション | データソースヘッダー |
| --- | --- |
| [カテゴリ](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [ マーケティングチャネル ](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [ マーケティングチャネルの詳細](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [製品](/help/components/dimensions/product.md) | `Product` |
| [トラッキングコード](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [トランザクション ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [郵便番号](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

ディメンションと指標は同じヘッダー行に配置されます。

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

Adobeは、他のディメンションや指標のデータソースをサポートしていません。 上記の表に記載されている以外の変数が必要な場合は、代わりに[Bulk Data insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)を使用することを検討してください。

## 日付

すべての行&#x200B;**の最初の値は日付である必要があります。**&#x200B;日付形式は、次のいずれかの形式である必要があります。

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

時間/分/秒を省略すると、その日のタイムスタンプは自動的に午後12時に設定されます。

1つのデータソースファイルでサポートされるユニーク日数は最大90日です。 アップロードに90日以上のユニークな日を含める場合は、データを複数のファイルに分割します。

## Dimensionと指標

各行の日付の後の値には、アップロードするデータが含まれます。 すべての行は、それぞれのタイムスタンプに対応します。 すべての行に同じ数のタブが存在することを確認してください。 列は任意の順序で指定できます。各行のデータが上部のヘッダーと一致していることを確認してください。 1つの行に含めることができるデータの最大量は4096 バイトです。

Dimension データにセミコロン （`;`）を含めることはできません。 セミコロンを含む行はスキップされます。

## 次の手順

[ ファイルのアップロード ](file-upload.md): Adobeで取り込むデータソースファイルをアップロードするプロセスについて説明します。
