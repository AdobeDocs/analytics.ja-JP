---
title: JavaScript版
description: 訪問者のブラウザーでサポートされているJavaScript バージョン。
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# JavaScript版

「JavaScript バージョン」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者のブラウザーでサポートされているJavaScript バージョンをレポートします。 AppMeasurement ライブラリのバージョンはレポートされません。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。 他のAnalytics ソリューションでJavaScript バージョンを使用する場合は、ヒットごとに[eVar](evar.md)に値をコピーすることを検討してください。

## このディメンションへのデータ入力

AppMeasurementは、ブラウザー内のJavaScript機能を自動的に検出し、`j` クエリ文字列パラメーターにバージョン値を送信します。 設定する実装変数がありません。 この検出は、従来のJavaScriptのバージョンラベルを使用します。これは、最新のECMAScript機能のサポートを包括的に測定するものではありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **クエリパラメーター** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Bulk Data Insertion API列** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **バイト制限** | 5 バイト |
| **永続性** | ヒット |

## ディメンション項目

Dimension項目には、訪問者のブラウザー（`1.5`や`1.6`など）から収集されたJavaScript バージョン値が含まれます。
