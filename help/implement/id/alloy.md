---
title: Web SDK JavaScript ライブラリを使用した訪問者特定
description: Web SDK JavaScript ライブラリを実装する際に、訪問者を正しく識別する。
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: https://experienceleague.adobe.com/R6O--qqR7SzlArrIDFCWunUEAduzmAS2Skm6BKyREnw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 2%

---

# Web SDK JavaScript ライブラリを使用した訪問者特定

Adobe Experience Platform Web SDK JavaScript ライブラリ （`alloy.js`）は、Adobe Analyticsを含むすべてのAdobe CX Enterprise アプリケーションに対して、最新の統合型データ収集アプローチを提供します。 ほとんどのユーザーは通常[Web SDK タグ拡張機能](web-sdk-extension.md)を実装しますが、Web SDK JavaScript ライブラリを単独で使用することも、サードパーティのタグ管理システム内で使用することもできます。 最新バージョンのライブラリをダウンロードするには、GitHubの[Alloy](https://github.com/adobe/alloy)を参照してください。

ID データを拡張して、XDMの`identityMap`を使用してカスタム IDと複数の名前空間をサポートできます。 Adobeでは、Analyticsの主要なIDとしてAdobe Experience Cloud ID サービスを使用し、高度なシナリオには他のID管理オプションを使用することをお勧めします。

Web SDK JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する場合、訪問者の識別には最小限の設定が必要です。 訪問者ID サービスは、ライブラリにネイティブにベイク処理されます。ただし、`configure` コマンドで&#x200B;**[!UICONTROL Edge Domain]**&#x200B;を設定する必要があります。 このフィールドが目的の値に設定されている場合、訪問者の識別は追加の設定なしで機能します。
