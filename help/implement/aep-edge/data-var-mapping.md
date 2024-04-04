---
title: Adobe Analyticsへのデータオブジェクト変数のマッピング
description: Edge が Analytics 変数に自動的にマッピングするExperience Platformオブジェクトフィールドを表示します。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 3a530e3e47ac9d6cf2b711cecd07f2c33765d63c
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# Adobe Analyticsへのデータオブジェクト変数のマッピング

次の表に、Adobe Experience Platform Edge Network が自動的にAdobe Analyticsにマッピングするデータオブジェクト変数を示します。 これらのデータオブジェクトフィールドパスを使用する場合、Adobe Analyticsにデータを送信するための追加の設定は必要ありません。

将来Customer Journey Analyticsを使用する場合は、これらのフィールドを使用することをお勧めします。 この実装方法を使用すると、XDM スキーマに準拠していなくても、Web SDK を使用してAdobeにデータを送信できます。 組織でAdobe Experience Platformにデータを送信する準備が整ったら、 [データストリームマッピング](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) を使用して、データオブジェクトフィールドをそれぞれの XDM フィールドに指定します。

## 優先度の価値

このテーブルのデータオブジェクトフィールドは、 [マッピングされた XDM フィールド](xdm-var-mapping.md). 両方の `data` オブジェクトフィールドとそれぞれの XDM フィールド、データオブジェクトフィールドが優先されます。 XDM オブジェクトフィールドとデータオブジェクトフィールドの両方を使用する場合、Adobeでは、データオブジェクトフィールドを使用してカスタムイベントを設定することをお勧めします。 フィールドが `data.__adobe.analytics.events` が存在する場合は、コマースおよびカスタムイベントに関連するすべての XDM オブジェクトフィールドを上書きします。

一部のデータオブジェクトフィールドは、それぞれの [クエリパラメーター値](../validate/query-parameters.md) 略記法の値として。 それぞれが一意の変数を持つ限り、標準データオブジェクトフィールドと短縮形データオブジェクトフィールドを同じ意味で使用できます。 標準データオブジェクトフィールドと、それぞれの短縮形のデータオブジェクトフィールドの両方を同時に設定しないでください。 Adobeは、どのフィールドが優先されるかを保証できません。

## データオブジェクトフィールドのマッピング

このテーブルの以前の更新は、このページの [GitHub のコミット履歴](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md)で確認できます。

| データオブジェクトフィールドのパス | Analytics 変数と説明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | The [ブラウザーの高さ](../../components/dimensions/browser-height.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.bh` はサポートされています。 |
| `data.__adobe.analytics.browserWidth` | The [ブラウザーの幅](../../components/dimensions/browser-width.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.bw` はサポートされています。 |
| `data.__adobe.analytics.campaign` | The [トラッキングコード](../../components/dimensions/tracking-code.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.v0` はサポートされています。 |
| `data.__adobe.analytics.channel` | The [サイトセクション](../../components/dimensions/site-section.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.ch` はサポートされています。 |
| `data.__adobe.analytics.colorDepth` | The [色深度](../../components/dimensions/color-depth.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.c` はサポートされています。 |
| `data.__adobe.analytics.connectionType` | The [接続タイプ](../../components/dimensions/connection-type.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.ct` はサポートされています。 |
| `data.__adobe.analytics.contextData` | [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | The [cookie サポート](../../components/dimensions/cookie-support.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.k` はサポートされています。 |
| `data.__adobe.analytics.currencyCode` | The [`currencyCode`](../vars/config-vars/currencycode.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.cc` はサポートされています。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | The [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 実装変数。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` はサポートされています。 |
| `data.__adobe.analytics.events` | [カスタムイベント](../../components/metrics/custom-events.md). このフィールドの書式を [`events`](../vars/page-vars/events/events-overview.md) 実装変数。 |
| `data.__adobe.analytics.javaEnabled` | The [Java 有効](../../components/dimensions/java-enabled.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.v` はサポートされています。 |
| `data.__adobe.analytics.latitude` | 設定に役立つ [場所](../../components/dimensions/lifecycle-dimensions.md) モバイルのライフサイクルディメンション。 短縮形のフィールド `data.__adobe.analytics.lat` はサポートされています。 |
| `data.__adobe.analytics.linkName` | The [カスタムリンク](../../components/dimensions/custom-link.md), [ダウンロードリンク](../../components/dimensions/download-link.md)または [出口リンク](../../components/dimensions/exit-link.md) ディメンション ( `data.__adobe.analytics.linkType`. 短縮形のフィールド `data.__adobe.analytics.pev2` はサポートされています。 |
| `data.__adobe.analytics.linkURL` | The [`linkURL`](../vars/config-vars/linkurl.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.pev1` はサポートされています。 |
| `data.__adobe.analytics.linkType` | クリックされたリンクのタイプを判断します。有効な値は次のとおりです。 `o` （カスタムリンク） `d` （ダウンロードリンク）、 `e` （出口リンク）。 短縮形のフィールド `data.__adobe.analytics.pe` はサポートされています。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` はサポートされています。 |
| `data.__adobe.analytics.longitude` | ヘルプセット [場所](../../components/dimensions/lifecycle-dimensions.md) モバイルのライフサイクルディメンション。 短縮形のフィールド `data.__adobe.analytics.lon` はサポートされています。 |
| `data.__adobe.analytics.pageName` | 「[ページ](/help/components/dimensions/page.md)」ディメンション。 |
| `data.__adobe.analytics.pageURL` | The [ページ URL](/help/components/dimensions/page-url.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.g` はサポートされています。 |
| `data.__adobe.analytics.pageType` | The [`pageType`](../vars/page-vars/pagetype.md) 実装変数。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` はサポートされています。 |
| `data.__adobe.analytics.purchaseID` | The [`purchaseID`](../vars/page-vars/purchaseid.md) 実装変数。 |
| `data.__adobe.analytics.products` | The [`products`](../vars/page-vars/products.md) 実装変数に書き込みます。 |
| `data.__adobe.analytics.referrer` | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| `data.__adobe.analytics.resolution` | The [画面の解像度](../../components/dimensions/monitor-resolution.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.s` はサポートされています。 |
| `data.__adobe.analytics.server` | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| `data.__adobe.analytics.tnta` | A4T 統合で使用されます。 |
| `data.__adobe.analytics.transactionID` | The [`transactionID`](../vars/page-vars/transactionid.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.xact` はサポートされています。 |
| `data.__adobe.analytics.zip` | The [郵便番号](../../components/dimensions/zip-code.md) ディメンション。 |

{style="table-layout:auto"}
