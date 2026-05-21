---
title: 実装方法の比較
description: Adobe Analytics にデータを送信する各方法の利点を確認します。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Tx3YIRJv4Qztv-Bsa9XJFMFVE0PW9SnvgrYeMmrULiA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 500
ht-degree: 41%

---

# 実装方法の比較

Adobe Analytics の各実装方法について、比較して説明します。 これらのテーブルを使用すると、組織がAdobeにデータを送信する最も理想的な方法を決定するのに役立ちます。 それぞれの列をクリックすると、詳細が表示されます。

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics 拡張機能](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK 拡張機能](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| 実装要件 | 各ページの`AppMeasurement.js`を参照し、変数を定義し、`s.t()`を使用してデータをAdobe Analyticsに送信します | 各ページでタグローダーを参照します。データ収集UIを使用して変数を定義し、Adobe Analyticsにデータを送信します | 各ページの`Alloy.js`を参照し、`alloy("sendEvent",{})`を使用してXDM オブジェクトを作成し、Edge Networkを使用して目的のデータをAdobe Analyticsに送信します | 各ページでタグローダーを参照し、Data Collection UIを使用してXDM オブジェクトを構成し、Edge Networkを使用して目的のデータをAdobe Analyticsに送信します |
| データ宛先 | Adobe Analytics に直接送信 | Adobe Analytics に直接送信 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトのコードを1回変更してローダータグをインストールします。それ以降のすべての実装の更新は、データ収集UIで行うことができます | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトのコードを1回変更してローダータグをインストールします。それ以降のすべての実装の更新は、データ収集UIで行うことができます |
| A4T の処理方法 | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | `s.contextData`.を使用します。 | カスタムコードブロックで`s.contextData`を使用 | マッピングされていないすべてのフィールドは、自動的に`a.x.*`個のコンテキストデータ変数として送信されます。 | マッピングされていないすべてのフィールドは、自動的に`a.x.*`個のコンテキストデータ変数として送信されます。 |

{style="table-layout:auto"}

## モバイル+その他

>[!CAUTION]
>
>バージョン 4 の Mobile SDK のサポートは 2021年8月31日（PT）に終了しました。 詳しくは、[Adobe Mobile Servicesの提供終了に関するFAQ](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=ja)を参照してください。


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [Edge Network API](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| 実装要件 | アプリでタグローダーを参照し、ダイレクト API呼び出しまたはData Collection UIのルールを使用してXDM オブジェクトを作成し、Edge Networkを使用して目的のデータをAdobe Analyticsに送信します | Edge Network APIを使用してXDM オブジェクトを作成し、Edge Networkを使用して目的のデータをAdobe Analyticsに送信します |
| データ宛先 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 直接API呼び出しが行われるアプリコードの変更またはデータ収集UIの変更 | 実装が変更されるたびにアプリコードにアクセスする必要があります |
| A4T の処理方法 | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | マッピングされていないすべてのフィールドは、自動的に`a.x.*`個のコンテキストデータ変数として送信されます。 | マッピングされていないすべてのフィールドは、`a.x.*`個のコンテキストデータ変数として自動的に送信されます |

{style="table-layout:auto"}
