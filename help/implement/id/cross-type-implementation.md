---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 47%

---

# 異なる実装タイプでのトラッキング

Adobe Analytics 実装のコアアーキテクチャは、すべての実装タイプで一貫しています。 このプロセスには、変数を定義し、Adobe のデータ収集サーバーに送信されるイメージリクエストにコンパイルすることが含まれます。 この概念では、同じサイトの異なるページ間で、Adobe Experience Platform データ収集の AppMeasurement、Web SDK およびそれぞれの拡張機能をシームレスに切り替えることができます。

アドビでは、すべてのページで同じ実装タイプを使用して、サイトの実装全体で一貫性を維持することをお勧めします。 ただし、サイトの一部に異なる要件がある場合は、このページを使用して、訪問者がページ間で一貫して追跡されるようにすることができます。

複数の種類の実装（AppMeasurementやハードコーディングされたイメージリクエストなど）を使用する場合は、次の変数が正しく設定され、一致していることを確認してください。

>[!NOTE]
>
>すべての実装タイプでは、同じ訪問者ID タイプ（従来のAnalytics ID、訪問者ID サービス、またはExperience Platform ID サービス）を使用する必要があります。 Adobeでは、可能な限り、すべての実装でECIDを使用することをお勧めします。

| 変数 | Web SDK タグ拡張機能 | Web SDK（合金） | Analytics 拡張機能 | AppMeasurement | ハードコーディングされたイメージリクエスト |
|---|---|---|---|---|---|
| レポートスイート ID | [データストリームの設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)時に Adobe Analytics をサービスとして追加 | [データストリームの設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)時に Adobe Analytics をサービスとして追加 | [拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview)時の「[!UICONTROL ライブラリ管理]」セクションの[!UICONTROL レポートスイート] | [`s_gi`](../vars/functions/s-gi.md)の文字列引数 | URL `pathname` の一部（`/b/ss/` の後） |
| 訪問者ID サービス | [Experience Platform ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)がネイティブに含まれます。訪問者ID サービス Cookieを読み取るには[`idMigrationEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/configure/idmigrationenabled)が必要です | [Experience Platform ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)がネイティブに含まれます。VisitorAPIからWeb SDK&rbrack;[&#128279;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity)にECIDを[&#128279;](https://experienceleague.adobe.com/ja/docs/id-service/using/implementation/direct-integration)移行して、Visitor ID サービス Cookieを読み取る必要があります | [&#39;[!UICONTROL Experience Cloud ID サービス &#x200B;]&#39; タグ拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/id-service/overview)を使用します。これは、[訪問者ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home)を実装します | [訪問者ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) （`VisitorAPI.js`）を実装します | 訪問者ID サービス &#x200B;に&lbrack;別の呼び出しを行って、目的のIDを取得し、クエリ文字列に`mid`を含めます |
| Edge ドメイン | [拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)時の[!UICONTROL Edge ドメイン &#x200B;] フィールド | [Web SDK の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/overview)時の `edgeDomain` プロパティ | [拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview)の[!UICONTROL General] セクションの[!UICONTROL SSL トラッキングサーバー] | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md)変数 | イメージリクエスト URL の `hostname` |

>[!NOTE]
>
>AppMeasurement ベースの実装（Analytics タグ拡張機能を含む）は、[Experience Platform Identity Service](https://experienceleague.adobe.com/ja/docs/id-service/using/home)と互換性がありません。 実装タイプ間で同期するには、訪問者IDの最小共通分母フォームを使用する必要があります。これは、通常、[訪問者ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) （`VisitorAPI.js`）です。

これらの変数のいずれかが各実装タイプで一貫性がない場合、Adobeでは、それらを個別の訪問者と見なす可能性があります。 サイトの実装タイプ間で訪問者がシームレスに追跡されない場合、最も一般的な理由は、訪問者の識別が正しく設定されていないことです。 各実装タイプが、サイト全体で同じECID （`mid` [&#x200B; クエリ文字列](/help/implement/validate/query-parameters.md)）を正しく取得していることを確認してください。
