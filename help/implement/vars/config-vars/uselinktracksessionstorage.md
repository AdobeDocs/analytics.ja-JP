---
title: useLinkTrackSessionStorage
description: リンクトラッキングデータは、cookieではなくセッションストレージに格納します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

組織でリンクトラッキングを使用している場合、AppMeasurementはcookieを使用し `s_sq` てヒット間で情報を渡します。 一部のWebサイト設定は、このCookieと競合します。 リンクトラッキングにブラウザーセッションストレージを使用し、cookieの代わりにアクティビティマップデータを使用する場合は、この変数を有効にします。

リンクトラッキングにブラウザーのセッションストレージを使用する場合、いくつかの制限があります。

* セッションストレージはプロトコル間では機能しません。 例えば、1つのページがHTTP経由で提供され、次のページがHTTPS経由で提供されるとします。 プロトコルの違いが原因で、AppMeasurementはセッションストレージのリンクトラッキングデータにアクセスできません。
* セッションストレージは、サブドメイン間では機能しません。 例えば、訪問者が移動し、 `store.example.com`次に移動したとしま `toys.example.com`す。 サブドメインが異なるため、AppMeasurementはセッションストレージのリンクトラッキングデータにアクセスできません。

>[!TIP] リンクトラッキングにセッションストレージを使用した最も信頼性の高い実装は、1つのサブドメインでHTTPS経由ですべてのコンテンツを提供します。

AppMeasurementは、ヒットをアドビに送信した後に、ストレージセッションのリンクトラッキングデータを削除します。 また、ブラウザーのタブが閉じると、自動的に期限切れになります。

## Adobe Experience Platform Launchでリンク追跡セッションストレージを使用する

Launch には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムのコードエディターを使用します。

## AppMeasurementのs.useLinkTrackSessionStorageとカスタムコードエディターの起動

この変数 `s.useLinkTrackSessionStorage` は、AppMeasurementがcookieの代わりにセッションストレージを使用してリンクトラッキングデータを使用するかどうかを決定するブール値 `s_sq` です。 デフォルト値は `false` です。AppMeasurementでリンクトラッキ `true` ングとアクティビティマップにcookieの代わりにセッションストレージを使用する場合は、 `s_sq` この変数をに設定します。

```js
s.useLinkTrackSessionStorage = true;
```
