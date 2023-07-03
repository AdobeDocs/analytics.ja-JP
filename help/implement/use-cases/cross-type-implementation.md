---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 100%

---

# 異なる実装タイプでのトラッキング

Adobe Analytics 実装のコアアーキテクチャは、すべての実装タイプで一貫しています。このプロセスには、変数を定義し、Adobe のデータ収集サーバーに送信されるイメージリクエストにコンパイルすることが含まれます。この概念では、同じサイトの異なるページ間で、Adobe Experience Platform データ収集の AppMeasurement、Web SDK およびそれぞれの拡張機能をシームレスに切り替えることができます。

アドビでは、すべてのページで同じ実装タイプを使用して、サイトの実装全体で一貫性を維持することをお勧めします。ただし、サイトの一部に異なる要件がある場合は、このページを使用して、訪問者がページ間で一貫して追跡されるようにすることができます。

複数のタイプの実装（AppMeasurement やハードコーディングされたイメージリクエストなど）を使用する場合は、次の変数が正しく設定され、互いに一致していることを確認します。

| 変数 | AppMeasurement | Analytics 拡張機能 | Web SDK | Web SDK 拡張機能 | ハードコーディングされたイメージリクエスト |
| --- | --- | --- | --- | --- | --- |
| レポートスイート ID | [`s_gi`](../vars/functions/s-gi.md) 内の文字列引数 | [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja)時の「[!UICONTROL ライブラリ管理]」セクションの[!UICONTROL レポートスイート] | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja)時に Adobe Analytics をサービスとして追加 | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja)時に Adobe Analytics をサービスとして追加 | URL `pathname` の一部（`/b/ss/` の後） |
| トラッキングサーバー | [`trackingServer`](../vars/config-vars/trackingserver.md) および [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 変数 | [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja)時の「[!UICONTROL 一般]」セクションの[!UICONTROL トラッキングサーバー]と [!UICONTROL SSL トラッキングサーバー] | [Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)時の `edgeDomain` プロパティ | [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja)時の [!UICONTROL Edge ドメイン] | イメージリクエスト URL の `hostname` |
| Experience Cloud ID サービス | [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ja) の実装 | [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=ja)の使用 | [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=ja)の使用 | [Adobe Experience Cloud ID サービス拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=ja)の使用 | 目的の ID を取得するための [ID サービスサーバーへの個別の呼び出し](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=ja)の実行 |

{style="table-layout:auto"}

これらの変数のいずれかが各実装タイプで一貫していない場合、アドビは個別の訪問者と見なします。サイトの実装タイプ間で訪問者がシームレスに追跡されない場合、最も一般的な理由は、ID サービスの設定が正しくないことです。詳しくは、ID サービスユーザーガイドの[実装方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html?lang=ja)を参照してください。
