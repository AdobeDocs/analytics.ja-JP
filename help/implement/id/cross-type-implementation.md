---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 64%

---

# 異なる実装タイプでのトラッキング

Adobe Analytics 実装のコアアーキテクチャは、すべての実装タイプで一貫しています。このプロセスには、変数を定義し、Adobe のデータ収集サーバーに送信されるイメージリクエストにコンパイルすることが含まれます。この概念では、同じサイトの異なるページ間で、Adobe Experience Platform データ収集の AppMeasurement、Web SDK およびそれぞれの拡張機能をシームレスに切り替えることができます。

アドビでは、すべてのページで同じ実装タイプを使用して、サイトの実装全体で一貫性を維持することをお勧めします。ただし、サイトの一部に異なる要件がある場合は、このページを使用して、訪問者がページ間で一貫して追跡されるようにすることができます。

複数のタイプの実装（AppMeasurementやハードコーディングされたイメージリクエストなど）を使用する場合は、次の変数が正しく設定され、互いに一致していることを確認します。

>[!NOTE]
>
>すべての実装タイプで同じ訪問者識別タイプ（従来の Analytics ID または訪問者 ID サービス）を使用する必要があります。 Adobeでは、可能な限り、すべての実装で訪問者 ID サービスを使用することをお勧めします。

| 変数 | AppMeasurement | Analytics 拡張機能 | Web SDK（Alloy） | Web SDK タグ拡張機能 | ハードコーディングされたイメージリクエスト |
| --- | --- | --- | --- | --- | --- |
| レポートスイート ID | [`s_gi`](../vars/functions/s-gi.md) の文字列引数 | [拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja)時の「[!UICONTROL ライブラリ管理]」セクションの[!UICONTROL レポートスイート] | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja)時に Adobe Analytics をサービスとして追加 | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja)時に Adobe Analytics をサービスとして追加 | URL `pathname` の一部（`/b/ss/` の後） |
| Experience Cloud ID サービス | 実装方法 [`VisitorAPI.js`](appmeasurement.md) | [Experience Cloud ID サービス拡張機能の使用 ](analytics-extension.md) | [ ネイティブで含まれる ](alloy.md) | [ ネイティブで含まれる ](web-sdk-extension.md) | [ID サービスへの個別の呼び出し ](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=ja) を実行して、目的の ID を取得し、`mid` をクエリ文字列に含めます |
| Edge ドメイン | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 変数 | [!UICONTROL  拡張機能の設定 ] 時の [!UICONTROL  一般 ] セクションの [SSL トラッキングサーバー ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja) | [Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)時の `edgeDomain` プロパティ | [!UICONTROL  拡張機能の設定 ] 時の [0}Edge ドメイン } フィールド](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) | イメージリクエスト URL の `hostname` |

これらの変数のいずれかが各実装タイプで一貫していない場合、アドビは個別の訪問者と見なします。サイトの実装タイプ間で訪問者がシームレスに追跡されない場合、最も一般的な理由は、ID サービスの設定が正しくないことです。各実装タイプが、サイト全体で同じExperience Cloud ID （`mid`）を正しく取得していることを確認します。
