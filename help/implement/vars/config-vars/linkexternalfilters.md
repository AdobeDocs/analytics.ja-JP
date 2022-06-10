---
title: linkExternalFilters
description: linkExternalFilters 変数の使用は離脱リンクの自動トラッキングに役立ちます。
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 62%

---

# linkExternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。If [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) または [`clickCollectionEnabled`](trackexternallinks.md) (Web SDK) を有効にすると、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがAdobeに直接送信されます。 `linkExternalFilters` 変数と [`linkInternalFilters`](linkinternalfilters.md) 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、出口リンクの自動トラッキングは許可リストのように動作します。 リンククリックがどの `linkExternalFilters` 値とも一致しない場合、そのリンクは離脱リンクと見なされません。この変数に対して URL 全体が調べられます。[`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリ文字列も調べられます。

>[!TIP]
>
> この変数は、離脱リンクと見なすドメインが正確にわかっている場合にのみ使用します。多くの組織では、離脱リンクのトラッキングのニーズを満たすには `linkInternalFilters` を使用すれば十分であると考え、`linkExternalFilters`を使用しません。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが離脱リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Web SDK の出口リンク

リンクのターゲットドメインが現在のドメインと異なる場合、リンクは自動的に出口リンクと見なされます `window.location.hostname`. Web SDK には、出口リンクの自動検出を変更する設定変数は用意されていません。 出口リンクと見なされるドメインをカスタマイズする必要がある場合は、 `onBeforeEventSend` コールバック。

詳しくは、 [自動リンクトラッキング](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) （ Web SDK ドキュメント）を参照してください。

## アウトバウンドリンク — Adobe Analytics拡張機能を使用した追跡

「追跡」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡]」フィールドが表示されます。

常に外部と見なすフィルターをこのフィールドに配置します。複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.linkExternalFilters

`s.linkExternalFilters` 変数は、離脱リンクと見なすフィルター（ドメインなど）を含む文字列です。複数のドメインは、スペースなしのコンマで区切ります。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

次の実装例を `adobe.com` にあるとして考えます。

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
