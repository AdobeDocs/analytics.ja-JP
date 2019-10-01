---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics用Kampyle Data Connector
solution: Analytics
title: Adobe Analytics用Kampyle Data Connector
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Kampyle Data Connector for Adobe Analytics{#kampyle-data-connector-for-adobe-analytics}

Kampyle Data Connector for Adobe Analyticsは、Kampyleの統合フィードバックシステムとAdobe Analytics®の行動レポートを組み合わせて、組織にとって強力な分析と最適化の機会を作り出します。

オンラインマーケターは、ブランド構築とビジネス成果の促進における顧客のフィードバックの関連性をますます認識し始めています。 Kampyle Data Connector for Adobe Analytics®は、訪問者のフィードバック指標およびディメンションをAdobe Analyticsに追加します。 これにより、訪問者の態度や意見に関する訪問者の行動を分析できます。 これにより、フィードバックに基づいて最適化し、コンバージョン率を向上させることができます。

## 統合の前提条件{#integration-prerequisites}

Data Connectorをアクティブ化する前に考慮する必要がある前提条件です。

### アドビのお客様向けの前提条件： {#section-d9c2e266931249e596de5f4406b5b6f0}

* Adobe Analyticsの現在のお客様である必要があります。
* 管理者ユーザーである必要があります。
* レポートスイート内でeVar変数を1つ使用し、有効にする必要があります。
* レポートスイート内に3つのカスタムイベントが使用可能で有効になっている必要があります(タイプ：カウンター)。

### Kampyle顧客の前提条件： {#section-4bbbca50e74d4f218414ae0cc535b8e9}

* Kampyle for webサイトの現在の顧客である必要があります。
* Data Connectorsを有効にする権限を持つAdobe Experience cloud管理者ユーザーである必要があります。
* Kampyle Feedback form管理UIからKampyle秘密鍵を取得できる必要があります。

## Kampyle秘密鍵の取得{#retrieve-the-kampyle-private-key}

Kampyleインターフェイス内でキーを取得する手順です。

1. https://www.kampyle.com/loginでKampyleアカウントにログインし [ます](https://www.kampyle.com/login)。
1. 左側のナビゲーションで、Feedback Form **[!UICONTROL /]** Feedback Form Customizationに移動します ****。

   ![](assets/retrieve_key1.png)

1. メインコンテンツペインの下部に表示されている秘密鍵を探します。

   ![](assets/retrieve_key2.png)
