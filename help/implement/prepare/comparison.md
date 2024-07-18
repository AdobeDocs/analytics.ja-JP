---
title: 実装方法の比較
description: Adobe Analytics にデータを送信する各方法の利点を確認します。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c476a1a19ae514f75fce8bd8e6d447d85de67a84
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 41%

---

# 実装方法の比較

Adobe Analytics の各実装方法について、比較して説明します。これらのテーブルを使用すると、Adobeにデータを送信する最も理想的な方法を判断するのに役立ちます。 詳細については、各列をクリックしてください。

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics 拡張機能](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK 拡張機能](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| 実装要件 | 各ページの `AppMeasurement.js` を参照し、変数を定義して、`s.t()` を使用してAdobe Analyticsにデータを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して変数を定義し、データをAdobe Analyticsに送信する | 各ページの `Alloy.js` を参照し、`alloy("sendEvent",{})` を使用して XDM オブジェクトを作成し、Edge Networkを使用してAdobe Analyticsに目的のデータを送信する | 各ページのタグローダーを参照し、データ収集 UI を使用して XDM オブジェクトを作成し、Edge Networkを使用してAdobe Analyticsに目的のデータを送信する |
| データ宛先 | Adobe Analytics に直接送信 | Adobe Analytics に直接送信 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトコードを 1 回変更して、ローダータグをインストールします。それ以外のすべての実装の更新は、データ収集 UI で実行可能です | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトコードを 1 回変更して、ローダータグをインストールします。それ以外のすべての実装の更新は、データ収集 UI で実行可能です |
| A4T の処理方法 | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | `s.contextData`.を使用します。 | カスタムコードブロックでの `s.contextData` の使用 | マッピングされていないフィールドはすべて、`a.x.*` のコンテキストデータ変数として自動的に送信されます。 | マッピングされていないフィールドはすべて、`a.x.*` のコンテキストデータ変数として自動的に送信されます。 |

{style="table-layout:auto"}

## モバイルと他

>[!CAUTION]
>
>バージョン 4 の Mobile SDK のサポートは 2021年8月31日（PT）に終了しました。詳しくは、[AdobeMobile Services の提供終了に関する FAQ](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) を参照してください。


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [ サーバー API](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| 実装要件 | アプリでタグローダーを参照し、データ収集 UI で直接の API 呼び出しまたはルールを使用して XDM オブジェクトを作成し、Edge Networkを使用してAdobe Analyticsに送信します | Edge Networkサーバー API を使用して XDM オブジェクトを作成し、Edge Networkを使用して目的のデータをAdobe Analyticsに送信する |
| データ宛先 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 直接の API 呼び出しが行われるアプリコードを変更するか、データ収集 UI で変更します | 実装の変更ごとにアプリコードへのアクセスが必要 |
| A4T の処理方法 | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | マッピングされていないフィールドはすべて、`a.x.*` のコンテキストデータ変数として自動的に送信されます。 | マッピングされていないフィールドはすべて、`a.x.*` のコンテキストデータ変数として自動的に送信されます |

{style="table-layout:auto"}
