---
title: フル処理のデータソースの提供終了
description: フル処理のデータソースに関する提供終了のお知らせについて詳しく説明します。
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# フル処理のデータソースの提供終了

フル処理データソースを使用することで、組織はヒットレベルのデータをAdobe Analyticsに送信できました。 このデータは、従来のデータ収集手段 (AppMeasurementなど ) で収集されたデータと同じ方法で処理されました。 2020 年、Adobeは [一括データ挿入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)：フル処理のデータソースと同じ機能を実行しますが、追加機能も実行します。 このページでは、一括データ挿入 API で提供される追加機能の詳細とファイル形式の違いの概要を説明します。

2021 年 3 月 25 日に、Adobeにより、新しいフル処理データソース接続が作成されなくなりました。 2022 年 1 月 31 日に、すべてのフル処理データサービスが無効化されました。

## フル処理データソースと一括データ挿入 API の主な違い

* 一括データ挿入を使用すると、複数のファイルを送信して並列処理できます。 訪問者グループは、訪問者の継続性とeVar属性を確保します。
* 一括データ挿入には、データ検証およびエラー処理機能があり、ヒットデータを送信する際の管理作業の一部を削除します。
* 一括データ挿入は、複数の訪問者 ID 識別方法をサポートします。
* 一括データ挿入には、追加の必須フィールドがいくつかあります。訪問者の識別列、 `pageName` （または同等のリンク） `reportSuiteID`, `timestamp`、および `userAgent`.
* 訪問者の継続性とアトリビューションを確保するために、一括データ挿入では、ファイル内の行を時系列順に並べ替える必要があります。 ファイル全体での訪問者アクティビティの順序については、 [訪問者グループ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) を参照してください。
* 一括データ挿入では、ファイルを.gzip 形式で圧縮した.csv ファイルが必要です。
* BDIA はを使用します `timestamp` の代わりに `date`.

## BDIA とフル処理データソースの変数の比較

以前はフル処理データソースでは使用できなかった、一括データ挿入には次の変数が導入されました。

* **`aamlh`**:Adobe Audience Managerのロケーションのヒント。
* **`contextData.key`**: [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**:Experience CloudID サービス変数。 `id`、`authState` および `isMCSeed` が含まれます。
* **`hints`**: [クライアントのヒント](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) 変数。 次を含む `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`、および `wow64`.
* **`ipaddress`**：訪問者の IP アドレス。
* **`language`**: [言語](/help/components/dimensions/language.md) ディメンション。
* **`list1`** - **`list3`**: [リスト変数](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**：訪問者のExperience CloudID。
* **`tnta`**：で使用される Target データペイロード [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=ja) 統合と呼ばれます。
* **`trackingServer`**: [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 変数を使用します。
* **`transactionID`**: [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 変数を使用します。
* **`userAgent`**：デバイスのユーザーエージェント文字列。

次の変数は、一括データ挿入ではサポートされません。

* **`charSet`**: [`charSet`](/help/implement/vars/config-vars/charset.md) 変数を使用します。 一括データ挿入は、UTF-8 のみをサポートします。
* **`timezone`**：訪問者のタイムゾーンの GMT からのオフセット（時間単位）。
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**：データ収集で使用されるActivity Map。
