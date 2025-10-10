---
title: Adobe Analyticsへのデータオブジェクト変数のマッピング
description: Experience Platform Edgeが Analytics 変数に自動的にマッピングするデータオブジェクトフィールドを表示します。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Adobe Analyticsへのデータオブジェクト変数のマッピング

次の表に、Adobe Experience Platform Edge NetworkがAdobe Analyticsに自動的にマッピングするデータオブジェクト変数を示します。 これらのデータオブジェクトフィールドのパスを使用する場合、データをAdobe Analyticsに送信するために追加の設定は必要ありません。

今後Customer Journey Analyticsを使用する予定がある場合は、これらのフィールドの使用をお勧めします。 この実装方法を使用すると、XDM スキーマに準拠せずに、web SDKを使用してAdobeにデータを送信できます。 組織でAdobe Experience Platformにデータを送信する準備が整ったら、[ データストリームマッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep#mapping) を使用して、データオブジェクトフィールドをそれぞれの XDM フィールドに指定できます。

## 値の優先度

このテーブル内のほとんどのデータオブジェクトフィールドは、[ マッピングされた XDM フィールド ](xdm-var-mapping.md) と一致します。 特定のデータオブジェクトフィールドとそれぞれの XDM フィールドの両方を設定した場合、データオブジェクトフィールドが優先されます。 例えば、フィールド `data.__adobe.analytics.events` が存在する場合は、イベント関連のすべての XDM オブジェクトフィールドが上書きされます。

一部のデータオブジェクトフィールドでは、短縮形の値としてそれぞれの [ クエリパラメーター値 ](../validate/query-parameters.md) もサポートしています。 標準のデータオブジェクトフィールドと短縮形のデータオブジェクトフィールドは、一意の変数に対してそれぞれが存在する限り、区別なく使用することができます。 標準データオブジェクトフィールドと、それぞれの短縮形データオブジェクトフィールドの両方を同時に設定しないでください。 Adobeでは、どのフィールドが優先されるかは保証できません。

## データオブジェクトフィールドのマッピング

このテーブルに関する以前の更新については、このページの [GitHub のコミット履歴 ](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) を参照してください。 AppMeasurement変数と同様に、すべてのデータオブジェクトフィールドでは大文字と小文字が区別されます。

| データオブジェクトフィールドのパス | Analytics の変数と説明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | [ ブラウザーの高さ ](../../components/dimensions/browser-height.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.bh` もサポートされています。 |
| `data.__adobe.analytics.browserWidth` | [ ブラウザーの幅 ](../../components/dimensions/browser-width.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.bw` もサポートされています。 |
| `data.__adobe.analytics.campaign` | 「[ トラッキングコード ](../../components/dimensions/tracking-code.md)」ディメンション。 短縮形のフィールド `data.__adobe.analytics.v0` もサポートされています。 |
| `data.__adobe.analytics.channel` | [ サイトセクション ](../../components/dimensions/site-section.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.ch` もサポートされています。 |
| `data.__adobe.analytics.colorDepth` | 「[ 色深度 ](../../components/dimensions/color-depth.md)」ディメンション。 短縮形のフィールド `data.__adobe.analytics.c` もサポートされています。 |
| `data.__adobe.analytics.connectionType` | [ 接続タイプ ](../../components/dimensions/connection-type.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.ct` もサポートされています。 |
| `data.__adobe.analytics.contextData` | [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | [Cookie サポート ](../../components/dimensions/cookie-support.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.k` もサポートされています。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.cc` もサポートされています。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 実装変数。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) ディメンション。 略記法のフィールド `data.__adobe.analytics.v1` ～ `data.__adobe.analytics.v250` もサポートされています。 |
| `data.__adobe.analytics.events` | [ カスタムイベント ](../../components/metrics/custom-events.md)。 このフィールドの形式を [`events`](../vars/page-vars/events/events-overview.md) 実装変数と同様にします。 |
| `data.__adobe.analytics.javaEnabled` | 「[Java 対応 ](../../components/dimensions/java-enabled.md)」ディメンション。 短縮形のフィールド `data.__adobe.analytics.v` もサポートされています。 |
| `data.__adobe.analytics.latitude` | [ 場所 ](../../components/dimensions/lifecycle-dimensions.md) モバイルライフサイクルディメンションの設定に役立ちます。 短縮形のフィールド `data.__adobe.analytics.lat` もサポートされています。 |
| `data.__adobe.analytics.linkName` | [ カスタムリンク ](../../components/dimensions/custom-link.md)、[ ダウンロードリンク ](../../components/dimensions/download-link.md)、または [ 離脱リンク ](../../components/dimensions/exit-link.md) ディメンション（`data.__adobe.analytics.linkType` の値によって異なります）。 短縮形のフィールド `data.__adobe.analytics.pev2` もサポートされています。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.pev1` もサポートされています。 |
| `data.__adobe.analytics.linkType` | クリックされたリンクのタイプを判断します。有効な値は `o` （カスタムリンク）、`d` （ダウンロードリンク）、`e` （離脱リンク）です。 短縮形のフィールド `data.__adobe.analytics.pe` もサポートされています。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 実装変数。 略記法のフィールド `data.__adobe.analytics.l1` ～ `data.__adobe.analytics.list3` もサポートされています。 |
| `data.__adobe.analytics.longitude` | [ 場所 ](../../components/dimensions/lifecycle-dimensions.md) モバイルライフサイクルディメンションの設定に役立ちます。 短縮形のフィールド `data.__adobe.analytics.lon` もサポートされています。 |
| `data.__adobe.analytics.pageName` | [ページ](/help/components/dimensions/page.md)ディメンション。 |
| `data.__adobe.analytics.pageURL` | 「[ ページ URL](/help/components/dimensions/page-url.md)」ディメンション。 短縮形のフィールド `data.__adobe.analytics.g` もサポートされています。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md) 実装変数。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) ディメンション。 略記法のフィールド `data.__adobe.analytics.c1` ～ `data.__adobe.analytics.c75` もサポートされています。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) 実装変数。 |
| `data.__adobe.analytics.products` | 同様の形式に従った [`products`](../vars/page-vars/products.md) 実装変数。 |
| `data.__adobe.analytics.referrer` | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| `data.__adobe.analytics.resolution` | [ 画面の解像度 ](../../components/dimensions/monitor-resolution.md) ディメンション。 短縮形のフィールド `data.__adobe.analytics.s` もサポートされています。 |
| `data.__adobe.analytics.server` | 「[サーバー](/help/components/dimensions/server.md)」ディメンション。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md) 実装変数。 短縮形のフィールド `data.__adobe.analytics.xact` もサポートされています。 |
| `data.__adobe.analytics.zip` | 「[ 郵便番号 ](../../components/dimensions/zip-code.md)」ディメンション。 |

{style="table-layout:auto"}
