---
title: Adobe Analyticsへのデータオブジェクト変数のマッピング
description: Experience PlatformEdge が Analytics 変数に自動的にマッピングするデータオブジェクトフィールドを表示します。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Adobe Analyticsへのデータオブジェクト変数のマッピング

次の表に、Adobe Experience PlatformEdge NetworkがAdobe Analyticsに自動的にマッピングするデータオブジェクト変数を示します。 これらのデータオブジェクトフィールドのパスを使用する場合、データをAdobe Analyticsに送信するために追加の設定は必要ありません。

今後Customer Journey Analyticsを使用する予定がある場合は、これらのフィールドを使用することをお勧めします。 この実装方法を使用すると、XDM スキーマに準拠せずに、web SDK を使用してAdobeにデータを送信できます。 Adobe Experience Platformにデータを送信する準備が整ったら、 [データストリームマッピング](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep#mapping) でデータオブジェクトフィールドをそれぞれの XDM フィールドに指定します。

## 値の優先度

このテーブル内のほとんどのデータオブジェクトフィールドは、 [マッピングされた XDM フィールド](xdm-var-mapping.md). 特定のデータオブジェクトフィールドとそれぞれの XDM フィールドの両方を設定した場合、データオブジェクトフィールドが優先されます。 例えば、フィールドが `data.__adobe.analytics.events` が存在する場合、イベント関連のすべての XDM オブジェクトフィールドを上書きします。

一部のデータオブジェクトフィールドも、それぞれのサポートを提供しています [クエリパラメーター値](../validate/query-parameters.md) 略記法の値。 標準のデータオブジェクトフィールドと短縮形のデータオブジェクトフィールドは、一意の変数に対してそれぞれが存在する限り、区別なく使用することができます。 標準データオブジェクトフィールドと、それぞれの短縮形データオブジェクトフィールドの両方を同時に設定しないでください。 Adobeでは、どのフィールドが優先されるかを保証することはできません。

## データオブジェクトフィールドのマッピング

このテーブルに対する以前の更新は、このページので確認できます [github のコミット履歴](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md). AppMeasurement変数と同様に、すべてのデータオブジェクトフィールドでは大文字と小文字が区別されます。

| データオブジェクトフィールドのパス | Analytics の変数と説明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | この [ブラウザーの高さ](../../components/dimensions/browser-height.md) ディメンション。 略記法フィールド `data.__adobe.analytics.bh` もサポートされています。 |
| `data.__adobe.analytics.browserWidth` | この [ブラウザーの幅](../../components/dimensions/browser-width.md) ディメンション。 略記法フィールド `data.__adobe.analytics.bw` もサポートされています。 |
| `data.__adobe.analytics.campaign` | この [トラッキングコード](../../components/dimensions/tracking-code.md) ディメンション。 略記法フィールド `data.__adobe.analytics.v0` もサポートされています。 |
| `data.__adobe.analytics.channel` | この [サイトセクション](../../components/dimensions/site-section.md) ディメンション。 略記法フィールド `data.__adobe.analytics.ch` もサポートされています。 |
| `data.__adobe.analytics.colorDepth` | この [色深度](../../components/dimensions/color-depth.md) ディメンション。 略記法フィールド `data.__adobe.analytics.c` もサポートされています。 |
| `data.__adobe.analytics.connectionType` | この [接続タイプ](../../components/dimensions/connection-type.md) ディメンション。 略記法フィールド `data.__adobe.analytics.ct` もサポートされています。 |
| `data.__adobe.analytics.contextData` | [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | この [Cookie サポート](../../components/dimensions/cookie-support.md) ディメンション。 略記法フィールド `data.__adobe.analytics.k` もサポートされています。 |
| `data.__adobe.analytics.currencyCode` | この [`currencyCode`](../vars/config-vars/currencycode.md) 実装変数。 略記法フィールド `data.__adobe.analytics.cc` もサポートされています。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | この [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 実装変数。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` もサポートされています。 |
| `data.__adobe.analytics.events` | [カスタムイベント](../../components/metrics/custom-events.md). このフィールドの形式を「」と同様にします [`events`](../vars/page-vars/events/events-overview.md) 実装変数。 |
| `data.__adobe.analytics.javaEnabled` | この [Java 有効](../../components/dimensions/java-enabled.md) ディメンション。 略記法フィールド `data.__adobe.analytics.v` もサポートされています。 |
| `data.__adobe.analytics.latitude` | を設定するのに役立ちます [場所](../../components/dimensions/lifecycle-dimensions.md) モバイルライフサイクルディメンション。 略記法フィールド `data.__adobe.analytics.lat` もサポートされています。 |
| `data.__adobe.analytics.linkName` | この [カスタムリンク](../../components/dimensions/custom-link.md), [ダウンロードリンク](../../components/dimensions/download-link.md)、または [離脱リンク](../../components/dimensions/exit-link.md) ディメンション （の値によって異なる） `data.__adobe.analytics.linkType`. 略記法フィールド `data.__adobe.analytics.pev2` もサポートされています。 |
| `data.__adobe.analytics.linkURL` | この [`linkURL`](../vars/config-vars/linkurl.md) 実装変数。 略記法フィールド `data.__adobe.analytics.pev1` もサポートされています。 |
| `data.__adobe.analytics.linkType` | クリックされたリンクのタイプを判断します。有効な値は次のとおりです `o` （カスタムリンク）、 `d` （ダウンロードリンク）、 `e` （離脱リンク）。 略記法フィールド `data.__adobe.analytics.pe` もサポートされています。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` もサポートされています。 |
| `data.__adobe.analytics.longitude` | を設定するヘルプ [場所](../../components/dimensions/lifecycle-dimensions.md) モバイルライフサイクルディメンション。 略記法フィールド `data.__adobe.analytics.lon` もサポートされています。 |
| `data.__adobe.analytics.pageName` | [ページ](/help/components/dimensions/page.md)ディメンション。 |
| `data.__adobe.analytics.pageURL` | この [ページ URL](/help/components/dimensions/page-url.md) ディメンション。 略記法フィールド `data.__adobe.analytics.g` もサポートされています。 |
| `data.__adobe.analytics.pageType` | この [`pageType`](../vars/page-vars/pagetype.md) 実装変数。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` もサポートされています。 |
| `data.__adobe.analytics.purchaseID` | この [`purchaseID`](../vars/page-vars/purchaseid.md) 実装変数。 |
| `data.__adobe.analytics.products` | この [`products`](../vars/page-vars/products.md) 実装変数。同様の形式を使用します。 |
| `data.__adobe.analytics.referrer` | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| `data.__adobe.analytics.resolution` | この [画面の解像度](../../components/dimensions/monitor-resolution.md) ディメンション。 略記法フィールド `data.__adobe.analytics.s` もサポートされています。 |
| `data.__adobe.analytics.server` | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| `data.__adobe.analytics.transactionID` | この [`transactionID`](../vars/page-vars/transactionid.md) 実装変数。 略記法フィールド `data.__adobe.analytics.xact` もサポートされています。 |
| `data.__adobe.analytics.zip` | この [郵便番号](../../components/dimensions/zip-code.md) ディメンション。 |

{style="table-layout:auto"}
