---
description: 'null'
title: Adobe Analytics 用 Kampyle Data Connector
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 95%

---


# Adobe Analytics 用 Kampyle Data Connector {#kampyle-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>2021年8月1日に、Adobeデータコネクタ技術の提供終了を予定しています。 [詳細情報...](/help/import/data-connectors/data-connectors-eol.md)

Adobe Analytics 用 Kampyle Data Connector は、Kampyle の統合フィードバックシステムと Adobe Analytics® の行動レポートを組み合わせ、組織のための強力な分析と最適化の機会を作り出します。

オンラインマーケティングの担当者は、ブランド構築とビジネス成果の促進における顧客のフィードバックの関連性に対する認識を深めつつあります。Adobe Analytics 用 Kampyle Data Connector では、訪問者のフィードバック指標とディメンションを Adobe Analytics に追加します。これによって、訪問者の行動と、訪問者の姿勢や意見の関係の関係を分析でき、フィードバックに基づいた最適化や、コンバージョン率の向上に役立てることができます。

## 統合の前提条件 {#integration-prerequisites}

Data Connector をアクティブ化する前に考慮する必要がある前提条件です。

### アドビのお客様向けの前提条件： {#section-d9c2e266931249e596de5f4406b5b6f0}

* Adobe Analytics を現在ご利用中のお客様である。
* 管理者ユーザーである。
* レポートスイート内で 1 つの eVar 変数が使用可能かつ有効である。
* レポートスイート内で 3 つのカスタムイベントが使用可能かつ有効である（タイプ：カウンター）。

### Kampyle 顧客の前提条件： {#section-4bbbca50e74d4f218414ae0cc535b8e9}

* Web サイトで Kampyle を現在ご利用中のお客様である。
* Data Connectors を有効にする権限を持つ Adobe Experience Cloud 管理者ユーザーである。
* Kampyle フィードバックフォーム管理 UI から Kampyle 秘密鍵を取得できる。

## Kampyle 秘密鍵の取得 {#retrieve-the-kampyle-private-key}

Kampyle インターフェイス内でキーを取得する手順です。

1. [https://www.kampyle.com/login](https://www.kampyle.com/login) で Kampyle アカウントにログインします。
1. 左側のナビゲーションで、**[!UICONTROL フィードバックフォーム]**／**[!UICONTROL フィードバックフォームのカスタマイズ]**&#x200B;に移動します。

   ![](assets/retrieve_key1.png)

1. メインコンテンツペインの下部に表示されている秘密鍵を探します。

   ![](assets/retrieve_key2.png)
