---
title: useLinkTrackSessionStorage
description: リンクトラッキングデータを、cookie ではなくセッションストレージに格納します。
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: https://experienceleague.adobe.com/n2TiWJuwct2fSZ3gz8UOhX9w--yXZ35yLrxQItVOXfk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

---

# useLinkTrackSessionStorage

組織がリンクトラッキングを使用している場合、AppMeasurement は `s_sq` cookie を使用してヒット間で情報を渡します。 一部の Web サイト設定は、この Cookie と競合します。 リンクトラッキングと Activity Map のデータに cookie ではなくブラウザーセッションストレージを使用する場合は、この変数を有効にします。

ブラウザーのセッションストレージをリンクトラッキングに使用する場合、いくつかの制限があります。

* プロトコル間ではセッションストレージは機能しません。 例えば、あるページが HTTP 経由で提供され、次のページが HTTPS 経由で提供されるとします。 プロトコルが異なるため、AppMeasurement はセッションストレージのリンクトラッキングデータにアクセスできません。
* セッションストレージは、サブドメイン間では機能しません。 例えば、訪問者が `store.example.com` に移動してから、`toys.example.com` に移動したとします。 サブドメインが異なるため、AppMeasurement はセッションストレージのリンクトラッキングデータにアクセスできません。

>[!TIP]
>
>リンクトラッキングにセッションストレージを使用した、最も信頼性の高い実装では、1 つのサブドメインで HTTPS を介してすべてのコンテンツを提供します。

AppMeasurement は、ヒットをアドビに送信した後で、セッションストレージのリンクトラッキングデータを削除します。 また、ブラウザータブを閉じると自動的に期限切れになります。

## Web SDKを使用したリンクトラックセッションストレージの使用

Web SDKはこの機能をサポートしていません。

## Adobe Analytics拡張機能を使用したリンクトラックセッションストレージの使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.useLinkTrackSessionStorageとAnalytics拡張機能のカスタムコードエディター

この `s.useLinkTrackSessionStorage` 変数は、AppMeasurement が、セッションストレージを `s_sq` cookie ではなく、リンクトラッキングデータに使用するかどうかを決定するブール値です。 デフォルト値は `false` です。 AppMeasurement でリンクトラッキングと Activity Map に、`s_sq` cookie の代わりにセッションストレージを使用する場合は、この変数を `true` に設定します。

```js
s.useLinkTrackSessionStorage = true;
```
