---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 18%

---

# 異なる実装タイプでのトラッキング

Adobe Analytics実装のコアアーキテクチャは、すべての実装タイプで一貫しています。 このプロセスでは、変数を定義し、変数をコンパイルして、Adobeのデータ収集サーバーに送信されるイメージリクエストにします。 つまり、Adobe Experience Platformデータ収集で、AppMeasurement、Web SDK およびそれぞれの拡張機能を、同じサイトの異なるページ間でシームレスに切り替えることができます。

Adobeでは、すべてのページで同じ実装タイプを使用して、サイトの実装全体で一貫性を維持することをお勧めします。 ただし、サイトの一部に異なる要件がある場合は、このページを使用して、ページ間で訪問者が一貫して追跡されていることを確認できます。

複数のタイプの実装（AppMeasurement やハードコードされたイメージリクエストなど）を使用する場合は、次の変数が正しく設定され、互いに一致していることを確認してください。

| 変数 | AppMeasurement | Analytics 拡張機能 | Web SDK | Web SDK 拡張機能 | ハードコーディングされたイメージリクエスト |
| --- | --- | --- | --- | --- | --- |
| レポートスイート ID | 内の文字列引数 [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL レポートスイート] の下に [!UICONTROL ライブラリ管理] セクション [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | 次の場合にAdobe Analyticsをサービスとして追加 [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja) | 次の場合にAdobe Analyticsをサービスとして追加 [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja) | URL の一部 `pathname` ( `/b/ss/`) |
| Tracking Server | この [`trackingServer`](../vars/config-vars/trackingserver.md) および [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 変数 | [!UICONTROL トラッキングサーバー] および [!UICONTROL SSL Tracking Server] の下に [!UICONTROL 一般] セクション [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | この `edgeDomain` プロパティの条件 [Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) | この [!UICONTROL Edge ドメイン] when [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) | この `hostname` イメージリクエスト URL の |
| Experience Cloud ID サービス | 実装方法 [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ja) | 以下を使用： [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 以下を使用： [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 以下を使用： [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | を作成 [ID サービスサーバーへの個別の呼び出し](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) 目的の ID を取得するには |

{style=&quot;table-layout:auto&quot;}

これらの変数のいずれかが各実装タイプで一貫していない場合、Adobeはそれらを個別の訪問者と見なします。 サイトの実装タイプをまたいで訪問者がシームレスに追跡されない場合、最も一般的な理由は、ID サービスの設定が正しくないことです。 詳しくは、 [実装方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) （ ID サービスユーザーガイド）を参照してください。
