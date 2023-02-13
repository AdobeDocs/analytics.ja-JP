---
title: 実装方法の比較
description: Adobe Analytics にデータを送信する各方法の利点を確認します。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# 実装方法の比較

Adobe Analytics の各実装方法について、比較して説明します。この表を使用すると、アドビにデータを送信する最も理想的な方法を組織が決定するのに役立ちます。

|  | AppMeasurement | Adobe Analytics 拡張機能 | Web SDK | Web SDK 拡張機能 |
| --- | --- | --- | --- | --- |
| 実装要件 | 各ページの `AppMeasurement.js` を参照し、変数を定義して、`s.t()` を使用してデータを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して変数を定義し、アドビにデータを送信する | 各ページの `Alloy.js` を参照し、`alloy("sendEvent",{})` を使用して目的のデータを含む JSON オブジェクトを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して、データを送信するための JSON オブジェクトを確立する |
| データ宛先 | Adobe Analytics に直接送信 | Adobe Analytics に直接送信 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 実装の変更ごとに web サイトコードへのアクセスが必要 | ローダータグをインストールするために、web サイトコードを 1 回だけ変更する必要があり、それ以外のすべての実装の更新は、データ収集 UI で実行可能 | 実装の変更ごとに web サイトコードへのアクセスが必要 | ローダータグをインストールするために、web サイトコードを 1 回だけ変更する必要があり、それ以外のすべての実装の更新は、データ収集 UI で実行可能 |
| A4T の処理方法 | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| リファラーの処理方法 |