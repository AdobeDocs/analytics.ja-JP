---
title: useLinkTrackSessionStorage
description: リンクトラッキングデータは、cookieではなくセッションストレージに保存します。
translation-type: tm+mt
source-git-commit: e1a08ecd3d5eb41bce7ca91027249871c3b5b22f

---


# useLinkTrackSessionStorage

組織でリンクトラッキングを使用している場合、AppMeasurementはcookieを使用し `s_sq` てヒット間で情報を渡します。 一部のWebサイト設定は、このCookieと競合します。 リンクトラッキングとActivity mapデータに対して、cookieの代わりにブラウザーセッションストレージを使用する場合は、この変数を有効にします。

リンクトラッキングにブラウザーのセッションストレージを使用する場合、いくつかの制限があります。

* プロトコル間でセッションストレージが機能しない。 例えば、1つのページがHTTP経由で提供され、次のページがHTTPS経由で提供されるとします。 プロトコルの違いが原因で、AppMeasurementはセッションストレージのリンクトラッキングデータにアクセスできません。
* セッションストレージはサブドメイン間では機能しません。 例えば、訪問者が移動し、そ `store.example.com`の後に移動したとしま `toys.example.com`す。 サブドメインが異なるため、AppMeasurementはセッションストレージのリンクトラッキングデータにアクセスできません。

> [!TIP] リンクトラッキングにセッションストレージを使用する最も信頼性の高い実装は、1つのサブドメインでHTTPSを介してすべてのコンテンツを提供します。
AppMeasurementは、アドビにヒットを送信した後に、セッションストレージのリンクトラッキングデータを削除します。 また、ブラウザータブが閉じると自動的に期限切れになります。

## Adobe Experience Platform Launchでのリンクトラックセッションストレージの使用

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.useLinkTrackSessionStorageとカスタムコードエディターの起動

この変 `s.useLinkTrackSessionStorage` 数は、AppMeasurementがcookieの代わりにセッションストレージをリンクトラッキングデータに使用するかどうかを決定するブール値 `s_sq` です。 Its default value is `false`. AppMeasurementでリンクトラッキ `true` ングとActivity mapに対してcookieの代わりにセッションストレージを `s_sq` 使用する場合は、この変数をに設定します。

```js
s.useLinkTrackSessionStorage = true;
```
