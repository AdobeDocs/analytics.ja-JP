---
title: Adobe Analyticsへのデータオブジェクトフィールドマッピング
description: Experience Platform Edge が Analytics 変数に自動的にマッピングするデータオブジェクトフィールドを表示します。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
TQID: https://experienceleague.adobe.com/FQRTVL9KrCQktNMhpqXo0f2VSrEm2mcCNL6IAmvtrko
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 614
ht-degree: 78%

---

# Adobe Analyticsへのデータオブジェクトフィールドマッピング

次の表は、Adobe Experience Platform Edge NetworkがAdobe Analyticsに自動的にマッピングするデータオブジェクトフィールドを示しています。 これらのデータオブジェクトフィールドパスを使用する場合、Adobe Analytics にデータを送信する追加設定は必要ありません。

今後 Customer Journey Analytics を使用する予定がある場合は、これらのフィールドの使用をお勧めします。 この実装方法により、組織は XDM スキーマに準拠せずに Web SDK を使用してデータをアドビに送信できます。 組織が Adobe Experience Platform にデータを送信する準備が整ったら、[データストリームマッピング](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/data-prep#mapping)を使用して、データオブジェクトフィールドをそれぞれの XDM フィールドに指定できます。

## 値の優先度

このテーブルのほとんどのデータオブジェクトフィールドは、[&#x200B; マッピングされたXDM フィールド &#x200B;](xdm-var-mapping.md)に対応します。 Adobe Analyticsの取り込み中、値はまずXDMからAnalytics変数にマッピングされます。 認識されたデータオブジェクトフィールドは、同じAnalytics変数にマッピングするときに、以前に設定した値をマッピングして上書きします。 例えば、`data.__adobe.analytics.events`が存在する場合、XDMから派生する一連のイベント全体が置き換えられます。イベントは両方のソースで結合されません。 データ オブジェクト フィールド内の空の文字列（`""`）は、対応するXDM フィールドに値が含まれている場合でも、マッピングされたAnalytics変数をヒット用に空白にします。

一部のデータオブジェクトフィールドでは、これに対応する[クエリパラメーター値](../validate/query-parameters.md)を短縮値としてサポートすることもできます。 標準データオブジェクトフィールドと短縮データオブジェクトフィールドは、それぞれが一意の変数用である限り、互換的に使用できます。 標準データオブジェクトフィールドとこれに対応する短縮データオブジェクトフィールドの両方を同時に設定することは回避します。 アドビでは、どのフィールドが優先されるかを保証できません。

## データオブジェクトフィールドのマッピング

このテーブルの以前の更新は、このページの [GitHub のコミット履歴](https://github.com/AdobeDocs/analytics.ja-JP/commits/main/help/implement/aep-edge/data-var-mapping.md)で確認できます。 AppMeasurement 変数と同様に、すべてのデータオブジェクトフィールドでは大文字と小文字が区別されます。

| データオブジェクトフィールドのパス | Analytics の変数と説明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | 「[ブラウザーの高さ](../../components/dimensions/browser-height.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.bh` もサポートされています。 |
| `data.__adobe.analytics.browserWidth` | 「[ブラウザーの幅](../../components/dimensions/browser-width.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.bw` もサポートされています。 |
| `data.__adobe.analytics.campaign` | 「[トラッキングコード](../../components/dimensions/tracking-code.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.v0` もサポートされています。 |
| `data.__adobe.analytics.channel` | 「[サイトセクション](../../components/dimensions/site-section.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.ch` もサポートされています。 |
| `data.__adobe.analytics.colorDepth` | 「[色深度](../../components/dimensions/color-depth.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.c` もサポートされています。 |
| `data.__adobe.analytics.connectionType` | 「[接続タイプ](../../components/dimensions/connection-type.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.ct` もサポートされています。 |
| `data.__adobe.analytics.contextData` | [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | 「[cookie サポート](../../components/dimensions/cookie-support.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.k` もサポートされています。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md) 実装変数。 短縮フィールド `data.__adobe.analytics.cc` もサポートされています。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 実装変数。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | 「[eVar](../../components/dimensions/evar.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` もサポートされています。 |
| `data.__adobe.analytics.events` | [カスタムイベント](../../components/metrics/custom-events.md)。 このフィールドの形式を [`events`](../vars/page-vars/events/events-overview.md) 実装変数と同様にします。 |
| `data.__adobe.analytics.javaEnabled` | 「[Java 対応](../../components/dimensions/java-enabled.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.v` もサポートされています。 |
| `data.__adobe.analytics.latitude` | 「[場所](../../components/dimensions/lifecycle-dimensions.md)」モバイルライフサイクルディメンションの設定に役立ちます。 短縮フィールド `data.__adobe.analytics.lat` もサポートされています。 |
| `data.__adobe.analytics.linkName` | 「[カスタムリンク](../../components/dimensions/custom-link.md)」、「[ダウンロードリンク](../../components/dimensions/download-link.md)」、または「[離脱リンク](../../components/dimensions/exit-link.md)」ディメンション（`data.__adobe.analytics.linkType` の値によって異なります）。 短縮フィールド `data.__adobe.analytics.pev2` もサポートされています。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md) 実装変数。 短縮フィールド `data.__adobe.analytics.pev1` もサポートされています。 |
| `data.__adobe.analytics.linkType` | クリックされたリンクのタイプを判断します。 有効な値は `o`（カスタムリンク）、`d`（ダウンロードリンク）、`e`（離脱リンク）です。 短縮フィールド `data.__adobe.analytics.pe` もサポートされています。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 実装変数。 短縮フィールド `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` もサポートされています。 |
| `data.__adobe.analytics.longitude` | 「[場所](../../components/dimensions/lifecycle-dimensions.md)」モバイルライフサイクルディメンションの設定に役立ちます。 短縮フィールド `data.__adobe.analytics.lon` もサポートされています。 |
| `data.__adobe.analytics.pageName` | 「[ページ](/help/components/dimensions/page.md)」ディメンション。 |
| `data.__adobe.analytics.pageURL` | 「[ページ URL](/help/components/dimensions/page-url.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.g` もサポートされています。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md) 実装変数。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | 「[Prop](../../components/dimensions/prop.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` もサポートされています。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) 実装変数。 |
| `data.__adobe.analytics.products` | 類似の形式に従った [`products`](../vars/page-vars/products.md) 実装変数。 |
| `data.__adobe.analytics.referrer` | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| `data.__adobe.analytics.resolution` | 「[画面の解像度](../../components/dimensions/monitor-resolution.md)」ディメンション。 短縮フィールド `data.__adobe.analytics.s` もサポートされています。 |
| `data.__adobe.analytics.server` | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md) 実装変数。 短縮フィールド `data.__adobe.analytics.xact` もサポートされています。 |
| `data.__adobe.analytics.zip` | 「[郵便番号](../../components/dimensions/zip-code.md)」ディメンション。 |

{style="table-layout:auto"}
