---
title: 完全な処理データソースの提供終了
description: フル処理データソースの提供終了のお知らせについて詳しくは、こちらを参照してください。
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/3NSbjRWl0GsomjsEXo8XczQ1RWOPGpqW4OM2YeUo3Wk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 8%

---

# 完全な処理データソースの提供終了

フル処理データソースは、従来、企業がAdobe Analyticsにヒットレベルのデータを送信することを可能にしてきました。 このデータは、AppMeasurementなどの従来のデータ収集手段を通じて収集されたデータと同様に処理されました。 2020年、Adobeは[Bulk Data insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)をリリースしました。これは、フル処理データソースと同じ機能を実行しますが、追加機能も備えています。 このページでは、一括データ挿入APIが提供する追加機能の詳細と、ファイル形式の違いの概要を説明します。

2021年3月25日、Adobeは新しいフル処理データソース接続の作成を禁止しました。 2022年1月31日、すべてのフル処理データサービスが無効になりました。

## フル処理データソースとBulk Data insertion APIの主な違い

* バルクデータ挿入を使用すると、並列処理のために複数のファイルを送信できます。 訪問者グループは、訪問者の継続性とeVarのアトリビューションを確保します。
* 一括データ挿入には、データ検証とエラー処理機能があり、ヒットデータを送信する管理作業の一部が削除されます。
* バルクデータ挿入では、複数の訪問者ID識別方法をサポートしています。
* 一括データ挿入には、訪問者識別列、`pageName` （またはリンクに相当）、`reportSuiteID`、`timestamp`、および`userAgent`の追加の必須フィールドがあります。
* 訪問者の連続性とアトリビューションを確保するために、ファイル内の行を時系列で並べ替える必要があります。 ファイル全体での訪問者アクティビティの順序については、 [訪問者グループ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) を参照してください。
* バルクデータの挿入には、ファイルを.gzip形式で.csv圧縮する必要があります。
* BDIAでは、`date`ではなく`timestamp`を使用しています。

## BDIAとフル処理データソースの変数比較

以下の変数が一括データ挿入に導入されました。以前は完全な処理データソースでは使用できませんでした。

* **`aamlh`**: Adobe Audience Managerの場所ヒント。
* **`contextData.key`**: [&#x200B; コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)。
* **`customerID`**: Experience Cloud ID サービス変数。 `id`、`authState` および `isMCSeed` が含まれます。
* **`hints`**: [&#x200B; クライアントヒント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=ja)変数。 `bitness`、`brands`、`mobile`、`model`、`platform`、`platformversion`および`wow64`が含まれます。
* **`ipaddress`**：訪問者のIP アドレス。
* **`language`**: [言語](/help/components/dimensions/language.md) ディメンション。
* **`list1`** - **`list3`**: [変数のリスト &#x200B;](/help/implement/vars/page-vars/list.md)。
* **`marketingCloudVisitorID`**：訪問者のExperience Cloud ID。
* **`tnta`**: Target [&#128279;](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=ja)統合のAnalyticsで使用されるTarget データペイロード。
* **`trackingServer`**: [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)変数。
* **`transactionID`**: [`transactionID`](/help/implement/vars/page-vars/transactionid.md)変数。
* **`userAgent`**: デバイスのユーザーエージェント文字列。

次の変数は、一括データ挿入ではサポートされていません。

* **`charSet`**: [`charSet`](/help/implement/vars/config-vars/charset.md)変数。 バルクデータ挿入はUTF-8のみをサポートします。
* **`timezone`**：訪問者のタイムゾーンがGMTから時間単位でオフセットされました。
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Activity Map データ コレクションで使用される変数。
