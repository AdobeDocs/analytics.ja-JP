---
title: データソースの概要
description: 外部ファイルを使用してAdobe Analyticsにデータを読み込みます。
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# データソースの概要

Adobe Analyticsのデータソースを使用すると、追加のオンラインデータまたはオフラインデータをレポート用にインポートできます。 これらは、web サイト外のビジネスのファセットと、それらがサイトとどのようにやり取りしているかを理解するのに役立ちます。 データソースを使用する一般的なワークフローは、次の手順で構成されます。

1. 組織は、他のソースからデータを収集します。 例としては、事前クリックデータ、コールセンターデータ、サイト外で発生したトランザクションに関する情報などがあります。
1. データは、タブ区切りのテキストファイルを使用してAdobe Analyticsが認識できる形式に書式設定されています。
1. テキストファイルは、Adobeが提供する FTP サイトに、付属の `.fin` ファイルと共にアップロードします。
1. Adobeでは、テキストファイルを取り込み、そのデータをサイトで収集したディメンションや指標と共に表示します。

Adobeが提供するデータソースには、一般的に次の 2 種類があります。 すべてのデータソーステンプレートは、次の 2 つのタイプのいずれかに基づいています。

* **概要データソース**:Adobe Analyticsに概要レベルのデータを簡単に読み込む方法を提供します。 タイムスタンプ、変数値および関連する指標を指定します。 各ディメンション項目のこれらの指標は、それに応じて増加します。 オフラインとオンラインのデータを並べて表示する場合に役立ちます。 ただし、オンラインデータとオフラインデータはリンクされません。
* **トランザクション ID データソース**:AppMeasurementとデータソース行によって送信されたヒットに一致するトランザクション ID が含まれている場合、データソースのディメンションと指標の値はそのヒットに追加されます。

**フル処理データソース** は、2021 年 3 月 25 日（PT）現在、データソースタイプとして提供されなくなりました。 詳しくは、[ 提供終了のお知らせ ](full-processing-eol.md) を参照してください。

Adobeでは、製品 UI や FTP の場所を使用せずにデータソースを作成し、データをアップロードできる [ データソース API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/) も提供しています。

## 次の手順

[ データソース使用の手引き ](getting-started.md)：シンプルなデータソースを開発レポートスイートにアップロードします。
