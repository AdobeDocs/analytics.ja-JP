---
title: データソースの概要
description: 外部ファイルを使用してAdobe Analyticsにデータを読み込みます。
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/AOl1PUYf4TL0FrYB8eHL-JLiWvz6ixJYKUPpIZEFqj8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 4%

---

# データソースの概要

Adobe Analytics データソースを使用すると、追加のオンラインまたはオフラインデータをレポート用に読み込むことができます。 web サイト外におけるビジネスのファセットや、サイトとどのようにやり取りしているのかを把握するのに役立ちます。 データソースを使用する一般的なワークフローは、次の手順で構成されます。

1. 組織は、ほかのソースからデータを収集しています。 たとえば、プリクリックデータ、コールセンターのデータ、サイト外で発生したトランザクションに関する情報などがあります。
1. データは、タブ区切りのテキストファイルを使用してAdobe Analyticsが理解できる形式で書式設定されます。
1. Adobeが提供するFTP サイトにテキストファイルを、付随する`.fin` ファイルとともにアップロードします。
1. Adobeは、テキストファイルを取り込み、そのデータをサイトで収集されたディメンションと指標と共に表示します。

Adobeには、一般にふたつの種類のデータソースがあります。 すべてのデータソーステンプレートは、次の2種類のいずれかに基づいています。

* **概要データソース**: Adobe Analyticsに概要データを簡単にインポートする方法を提供します。 タイムスタンプ、変数値、および関連する指標を指定します。 ディメンション項目ごとに、これらの指標を増やします。 オフラインデータとオンラインデータを並べて見たい場合に役立ちます。 ただし、オンラインとオフラインのデータをリンクさせることはできません。
* **トランザクション ID データ ソース**: AppMeasurementによって送信されたヒットとデータ ソース行に一致するトランザクション IDが含まれている場合、データ ソース内のディメンションと指標の値はそのヒットに追加されます。

**フル処理データソース**&#x200B;は、2021年3月25日をもってデータソースタイプとして提供されなくなりました。 詳しくは、[提供終了のお知らせ](full-processing-eol.md)を参照してください。

Adobeでは、[&#x200B; データソース API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)も提供しています。これにより、商品UIやFTPの場所を使用せずにデータソースを作成し、データをアップロードできます。

## 次の手順

[&#x200B; データソースの概要](getting-started.md)：開発レポートスイートにシンプルなデータソースをアップロードします。
