---
title: 実装方法の比較
description: 各メソッドでAdobe Analyticsにデータを送信するメリットを確認してください。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 3%

---

# 実装方法の比較

Adobe Analyticsの実装の各方法が、互いにどのように比較されるかを確認します。 この表を使用して、組織がAdobeにデータを送信する最も理想的な方法を判断するのに役立ちます。

|  | AppMeasurement | Adobe Analytics 拡張機能 | Web SDK | Web SDK 拡張機能 |
| --- | --- | --- | --- | --- |
| 実装要件 | 参照 `AppMeasurement.js` 各ページで変数を定義し、 `s.t()` | 各ページの参照タグローダー。データ収集 UI を使用して変数を定義し、データをAdobeに送信します | 参照 `Alloy.js` 各ページで、 `alloy("sendEvent",{})` 目的のデータを含む JSON オブジェクトを送信するには | 各ページの参照タグローダー。データ収集 UI を使用して、データを送信する JSON オブジェクトを確立します。 |
| データの宛先 | Adobe Analyticsに直接送信 | Adobe Analyticsに直接送信 | Adobe Experience Platform Edge に送信され、Adobe Analyticsにデータを転送します | Adobe Experience Platform Edge に送信され、Adobe Analyticsにデータを転送します |
| 実装の調整が困難 | 実装が変更されるたびに、Web サイトコードへのアクセスが必要 | Web サイトコードを変更する必要があるのは、ローダータグをインストールする場合、1 回だけです。その他のすべての実装の更新は、データ収集 UI でおこなうことができます | 実装が変更されるたびに、Web サイトコードへのアクセスが必要 | Web サイトコードを変更する必要があるのは、ローダータグをインストールする場合、1 回だけです。その他のすべての実装の更新は、データ収集 UI でおこなうことができます |
| A4T の処理方法 | A4T 呼び出しは、Adobeに送信されるヒットに含まれます | A4T 呼び出しは、Adobeに送信されるヒットに含まれます | A4T 呼び出しは、別々のヒットとして送信されます | A4T 呼び出しは、別々のヒットとして送信されます |
| リファラーの処理方法 |