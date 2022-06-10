---
title: useLinkTrackSessionStorage
description: リンクトラッキングデータを、cookie ではなくセッションストレージに格納します。
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 81%

---

# useLinkTrackSessionStorage

組織がリンクトラッキングを使用している場合、AppMeasurement は `s_sq` cookie を使用してヒット間で情報を渡します。一部の Web サイト設定は、この Cookie と競合します。リンクトラッキングと Activity Map のデータに cookie ではなくブラウザーセッションストレージを使用する場合は、この変数を有効にします。

ブラウザーのセッションストレージをリンクトラッキングに使用する場合、いくつかの制限があります。

* プロトコル間ではセッションストレージは機能しません。例えば、あるページが HTTP 経由で提供され、次のページが HTTPS 経由で提供されるとします。プロトコルが異なるため、AppMeasurement はセッションストレージのリンクトラッキングデータにアクセスできません。
* セッションストレージは、サブドメイン間では機能しません。例えば、訪問者が `store.example.com` に移動してから、`toys.example.com` に移動したとします。サブドメインが異なるため、AppMeasurement はセッションストレージのリンクトラッキングデータにアクセスできません。

>[!TIP]
>
> リンクトラッキングにセッションストレージを使用した、最も信頼性の高い実装では、1 つのサブドメインで HTTPS を介してすべてのコンテンツを提供します。

AppMeasurement は、ヒットをアドビに送信した後で、セッションストレージのリンクトラッキングデータを削除します。また、ブラウザータブを閉じると自動的に期限切れになります。

## Web SDK を使用したリンクトラッキングセッションストレージの使用

Web SDK は、この機能をサポートしていません。

## Adobe Analytics拡張機能を使用して、リンクトラッキングセッションストレージを使用する

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.useLinkTrackSessionStorage

この `s.useLinkTrackSessionStorage` 変数は、AppMeasurement が、セッションストレージを `s_sq` cookie ではなく、リンクトラッキングデータに使用するかどうかを決定するブール値です。デフォルト値は `false` です。AppMeasurement でリンクトラッキングと Activity Map に、`s_sq` cookie の代わりにセッションストレージを使用する場合は、この変数を `true` に設定します。

```js
s.useLinkTrackSessionStorage = true;
```
