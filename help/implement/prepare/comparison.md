---
title: 実装方法の比較
description: Adobe Analytics にデータを送信する各方法の利点を確認します。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: 61264d9f4ff2f1e961a613b81461efa826bc3d23
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 46%

---

# 実装方法の比較

Adobe Analytics の各実装方法について、比較して説明します。これらのテーブルを使用して、組織がAdobeにデータを送信する最も理想的な方法を判断するのに役立ちます。 各列をクリックすると、詳細情報が表示されます。

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics 拡張機能](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK 拡張機能](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| 実装要件 | 各ページの `AppMeasurement.js` を参照し、変数を定義して、`s.t()` を使用してデータを送信する Adobe Analyticsへ | 各ページの参照タグローダー。データ収集 UI を使用して変数を定義し、Adobe Analyticsにデータを送信します | 参照 `Alloy.js` 各ページで、 `alloy("sendEvent",{})` :XDM オブジェクトを作成し、Edge Network を使用してAdobe Analyticsに目的のデータを送信する | 各ページの参照タグローダー。データ収集 UI を使用して XDM オブジェクトを作成し、Edge Network を使用してAdobe Analyticsに必要なデータを送信します |
| データ宛先 | Adobe Analytics に直接送信 | Adobe Analytics に直接送信 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトのコードを 1 回変更してローダータグをインストールします。その後の実装の更新はすべて、データ収集 UI でおこなうことができます。 | 実装の変更ごとに web サイトコードへのアクセスが必要 | Web サイトのコードを 1 回変更してローダータグをインストールします。その後の実装の更新はすべて、データ収集 UI でおこなうことができます。 |
| A4T の処理方法 | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、アドビに送信されたヒットに含まれる | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | `s.contextData`.を使用します。 | 用途 `s.contextData` カスタムコードブロック内 | マッピングされていないフィールドはすべて、 `a.x.*` コンテキストデータ変数。 | マッピングされていないフィールドはすべて、 `a.x.*` コンテキストデータ変数。 |

{style="table-layout:auto"}

## モバイルおよびその他

>[!CAUTION]
>
>バージョン 4 の Mobile SDK のサポートは 2021年8月31日（PT）に終了しました。詳しくは、[バージョン 4 モバイル SDK サポート終了に関する FAQ](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)（英語）を参照してください。


| | [モバイル SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [サーバー API](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| 実装要件 | アプリ内でタグローダーを参照し、データ収集 UI で直接 API 呼び出しまたはルールを使用して XDM オブジェクトを作成し、Edge Network を使用してAdobe Analyticsに目的のデータを送信します。 | Edge Network Server API を使用して XDM オブジェクトを作成し、Edge Network を使用してAdobe Analyticsに目的のデータを送信する |
| データ宛先 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 | Adobe Experience Platform Edge に送信し、それが Adobe Analytics にデータを転送 |
| 実装の調整が困難 | 直接 API 呼び出しがおこなわれるアプリコードを変更するか、データ収集 UI で変更を加えます。 | 実装が変更されるたびに、アプリコードへのアクセスが必要です |
| A4T の処理方法 | A4T 呼び出しは、別のヒットとして送信される | A4T 呼び出しは、別のヒットとして送信される |
| コンテキストデータ | マッピングされていないフィールドはすべて、 `a.x.*` コンテキストデータ変数。 | マッピングされていないフィールドはすべて、 `a.x.*` コンテキストデータ変数 |

{style="table-layout:auto"}
