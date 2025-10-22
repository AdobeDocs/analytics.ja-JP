---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 58%

---

# 異なる実装タイプでのトラッキング

Adobe Analytics 実装のコアアーキテクチャは、すべての実装タイプで一貫しています。このプロセスには、変数を定義し、Adobe のデータ収集サーバーに送信されるイメージリクエストにコンパイルすることが含まれます。この概念では、同じサイトの異なるページ間で、Adobe Experience Platform データ収集の AppMeasurement、Web SDK およびそれぞれの拡張機能をシームレスに切り替えることができます。

アドビでは、すべてのページで同じ実装タイプを使用して、サイトの実装全体で一貫性を維持することをお勧めします。ただし、サイトの一部に異なる要件がある場合は、このページを使用して、訪問者がページ間で一貫して追跡されるようにすることができます。

複数のタイプの実装（AppMeasurementやハードコーディングされたイメージリクエストなど）を使用する場合は、次の変数が正しく設定され、互いに一致していることを確認します。

>[!NOTE]
>
>すべての実装タイプで同じ訪問者識別タイプ（従来の Analytics ID または訪問者 ID サービス）を使用する必要があります。 Adobeでは、可能な限り、すべての実装で訪問者 ID サービスを使用することをお勧めします。

| 変数 | Web SDK タグ拡張機能 | Web SDK（Alloy） | Analytics 拡張機能 | AppMeasurement | ハードコーディングされたイメージリクエスト |
|---|---|---|---|---|---|
| レポートスイート ID | [データストリームの設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)時に Adobe Analytics をサービスとして追加 | [データストリームの設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)時に Adobe Analytics をサービスとして追加 | [拡張機能の設定](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview)時の「[!UICONTROL ライブラリ管理]」セクションの[!UICONTROL レポートスイート] | [`s_gi`](../vars/functions/s-gi.md) の文字列引数 | URL `pathname` の一部（`/b/ss/` の後） |
| Experience Cloud ID サービス | [&#x200B; ネイティブで含まれる &#x200B;](web-sdk-extension.md) | [&#x200B; ネイティブで含まれる &#x200B;](alloy.md) | [Experience Cloud ID サービス拡張機能の使用 &#x200B;](analytics-extension.md) | 実装方法 [`VisitorAPI.js`](appmeasurement.md) | [ID サービスへの個別の呼び出し &#x200B;](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) を実行して、目的の ID を取得し、`mid` をクエリ文字列に含めます |
| Edge ドメイン | [!UICONTROL &#x200B; 拡張機能の設定 &#x200B;] 時の [0&rbrace;Edge ドメイン &rbrace; フィールド](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | [Web SDK の設定](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)時の `edgeDomain` プロパティ | [!UICONTROL &#x200B; 拡張機能の設定 &#x200B;] 時の [!UICONTROL &#x200B; 一般 &#x200B;] セクションの [SSL トラッキングサーバー &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 変数 | イメージリクエスト URL の `hostname` |

これらの変数のいずれかが各実装タイプで一貫していない場合、Adobeは個別の訪問者と見なす可能性があります。 サイトの実装タイプ間で訪問者がシームレスに追跡されない場合、最も一般的な理由は、ID サービスの設定が正しくないことです。各実装タイプが、サイト全体で同じExperience Cloud ID （`mid`）を正しく取得していることを確認します。
