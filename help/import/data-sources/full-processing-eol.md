---
title: フル処理データソースの提供終了
description: フル処理データソースの提供終了のお知らせについて詳しく説明します。
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# フル処理データソースの提供終了

フル処理のデータソースにより、組織はヒットレベルのデータをAdobe Analyticsに送信できるようになりました。 このデータは、AppMeasurementなどの従来のデータ収集手段で収集されたデータと同じ方法で処理されました。 2020 年、Adobeは、フル処理データソースと同じ機能を実行しますが、追加機能も備えた [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) をリリースしました。 このページでは、Bulk Data Insertion API で提供される追加機能の詳細とファイル形式の違いの概要を説明します。

2021 年 3 月 25 日（PT）に、Adobeで新しいフル処理データソース接続が作成できなくなりました。 2022 年 1 月 31 日（PT）に、すべてのフル処理データサービスが無効になりました。

## フル処理データソースと Bulk data insertion API の主な違い

* Bulk data insertion を使用すると、複数のファイルを送信して並列処理できます。 訪問者グループは、訪問者の継続性とeVarアトリビューションを確保します。
* Bulk data insertion には、データ検証機能とエラー処理機能があり、ヒットデータの送信に関する管理作業の一部が削除されます。
* Bulk data insertion は、複数の訪問者 ID 識別方法をサポートします。
* Bulk data insertion には、訪問者 ID 列、`pageName` （または同等のリンク）、`reportSuiteID`、`timestamp`、`userAgent` など、いくつかの追加の必須フィールドがあります。
* 訪問者の継続性とアトリビューションを確保するために、Bulk data insertion では、ファイル内の行を時系列順に並べ替える必要があります。 ファイル全体での訪問者アクティビティの順序については、 [訪問者グループ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) を参照してください。
* Bulk data insertion では、.csv ファイルを.gzip 形式で圧縮する必要があります。
* BDIA では、`date` の代わりに `timestamp` を使用します。

## BDIA とフル処理データソースの変数比較

Bulk データ挿入には、以前はフル処理のデータソースでは使用できなかった次の変数が導入されました。

* **`aamlh`**:Adobe Audience Managerの場所のヒント。
* **`contextData.key`**: [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)。
* **`customerID`**:Experience CloudID サービス変数。 `id`、`authState` および `isMCSeed` が含まれます。
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) 変数。 `bitness`、`brands`、`mobile`、`model`、`platform`、`platformversion` および `wow64` が含まれます。
* **`ipaddress`**：訪問者の IP アドレス。
* **`language`**: [ 言語 ](/help/components/dimensions/language.md) ディメンション。
* **`list1`** - **`list3`**: [ リスト変数 ](/help/implement/vars/page-vars/list.md)。
* **`marketingCloudVisitorID`**：訪問者のExperience Cloud ID。
* **`tnta`**: [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=ja) 統合で使用される Target データペイロード。
* **`trackingServer`**:[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 変数。
* **`transactionID`**:[`transactionID`](/help/implement/vars/page-vars/transactionid.md) 変数。
* **`userAgent`**: デバイスのユーザーエージェント文字列。

次の変数は、一括データ挿入ではサポートされません。

* **`charSet`**:[`charSet`](/help/implement/vars/config-vars/charset.md) 変数。 Bulk data insertion は、UTF-8 のみをサポートします。
* **`timezone`**：訪問者のタイムゾーンオフセット（GMT からの時間単位）。
* **`clickAction`**、**`clickActionType`**、**`clickContext`**、**`clickContextType`**、**`clickSourceID`**、**`clickTag`**:Activity Mapデータ収集で使用される変数。
