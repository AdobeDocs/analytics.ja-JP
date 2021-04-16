---
description: この統合により、Qualtrics Research Suite の顧客調査機能と Adobe Analytics 内で収集する豊富なデータを組み合わせ、組織にとって強力な分析と最適化の機会が生まれます。
subtopic: Qualtrics
title: Adobe Analytics 用 Qualtrics Data Connector
feature: Data Connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
exl-id: 5c1234b1-bca8-4e7a-981e-1379e88821b8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 96%

---

# Adobe Analytics 用 Qualtrics Data Connector {#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>2021年8月1日に、Adobeデータコネクタ技術の提供終了を予定しています。 [詳細情報...](/help/import/data-connectors/data-connectors-eol.md)

この統合により、Qualtrics Research Suite の顧客調査機能と Adobe Analytics 内で収集する豊富なデータを組み合わせ、組織にとって強力な分析と最適化の機会が生まれます。

この双方向の統合では、まず Qualtrics の調査への回答データと、訪問者のクリックストリームデータを結び付けます。その後、関連する行動アクションと属性を、Adobe Analytics から Qualtrics 調査レポートに再度挿入します。

## 主なメリットと機能 {#key-benefits-and-features}

* 特定の調査質問に対するユーザーの回答に基づいて、ユーザーセグメントを作成します。
* 調査、質問、回答レベルの詳細に基づくトラフィックとコンバージョンのレポート。
* ListVar 1 つ、eVar 1 つ、イベント 1 つのみを使用して、無制限の Qualtrics 調査を統合します。
* 最大 5 つのカスタムコンバージョンディメンション、5 つのカスタムトラフィックディメンション、5 つのカスタム成功イベント、および Adobe Analytics で追跡されるその他 20 以上の標準指標とディメンションを使用して、Qualtrics のレポートを強化します。
* Adobe Analytics 内の統合調査データは、調査が送信されると「ライブ」に送られます。Qualtrics への書き出しは毎日おこなわれます。

## このコネクタをアクティブ化する前に {#before-you-activate-this-connector}

### アドビの前提条件 {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Adobe Analytics を現在ご利用中のお客様である。
* 管理者ユーザーである。
* レポートスイート内に、使用可能で有効化されているリスト変数が 1 つある。
* レポートスイート内に、使用可能で有効化されている eVar（または prop）変数が 1 つある。
* レポートスイート内に使用可能なカスタムイベントが 1 つある。

### Qualtrics の前提条件 {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Qualtrics Research Suite を現在利用中のお客様である。
* Adobe Analytics 統合を有効にする権限を付与されたユーザーである。
* Research Suite の **[!UICONTROL Qualtrics ID]** 領域内で Adobe Analytics トークンを生成できる。
