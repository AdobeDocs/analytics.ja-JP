---
title: 実装方法の比較
description: Adobe Analytics にデータを送信する各方法の利点を確認します。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 76%

---

# 実装方法の比較

Adobe Analytics の各実装方法について、比較して説明します。この表を使用すると、アドビにデータを送信する最も理想的な方法を組織が決定するのに役立ちます。

| | AppMeasurement | Adobe Analytics 拡張機能 | Web SDK | Web SDK 拡張機能 |
| --- | --- | --- | --- | --- |
| 実装要件 | 各ページの `AppMeasurement.js` を参照し、変数を定義して、`s.t()` を使用してデータを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して変数を定義し、アドビにデータを送信する | 各ページの `Alloy.js` を参照し、`alloy("sendEvent",{})` を使用して目的のデータを含む JSON オブジェクトを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して、データを送信するための JSON オブジェクトを確立する |
| データ宛先 | Adobe Analytics に直接送信 | Adobe Analytics に直接送信 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトコードを 1 回変更して、ローダタグをインストールする。その他のすべての実装の更新は、データ収集 UI でおこなうことができます | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトコードを 1 回変更して、ローダタグをインストールする。その他のすべての実装の更新は、データ収集 UI でおこなうことができます |
| A4T の処理方法 | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | `s.contextData`.を使用します。 | 用途 `s.contextData` カスタムコードブロック内 | マッピングされていないフィールドは、 `a.x.*` コンテキストデータ変数。 | マッピングされていないフィールドは、 `a.x.*` コンテキストデータ変数。 |

{style="table-layout:auto"}
