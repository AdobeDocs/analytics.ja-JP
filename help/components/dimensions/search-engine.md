---
title: 検索エンジン
description: 訪問者がサイトに到達するのに使用した検索エンジン。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 93%

---

# 検索エンジン

「検索エンジン」 [ ディメンション ](overview.md) は、訪問者がサイトへの到達に使用した検索エンジンをレポートします。 リファラーは、検索エンジンとして分類するために、次の両方と一致する必要があります。

* 参照ドメインは、アドビによって有効な検索エンジンとして認識されます。
* 参照 URL にキーワードクエリ文字列パラメーターが存在する。クエリ文字列パラメーターは空白にすることができます（プライバシーに関する慣行が原因で、複数の検索エンジンで使用される場合と同様です）。

有料検索と自然検索を区別したい場合は、[有料検索検知](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)が必要です。検索エンジンには、複数のディメンションを使用できます。

* **検索エンジン**：有料か自然かに関係なく、サイトに到達するために使用する検索エンジン。
* **検索エンジン — 有料**：サイトに到達するのに使用した検索エンジンで、有料検索検知と一致するもの。
* **検索エンジン — 自然**：サイトの訪問に使用した検索エンジンで、有料検索検知と一致しなかった。

## このディメンションへのデータ入力

このディメンションは、アドビ内部の複数のルックアップテーブルを参照します。各値は、ヒットの[リファラー](referrer.md)（[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)に依存）に基づきます。リファラーディメンションと内部 URL フィルターが正しく設定されていることを確認します。

## ディメンション項目

ディメンション項目には、サイトに到達するために使用される検索エンジンが含まれます。例えば、`"Google"`、`"Microsoft Bing"`、`"DuckDuckGo"` などの値があります。`"Unspecified"` ディメンション項目は、すべて検索以外のトラフィックです。
