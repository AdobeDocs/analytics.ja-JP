---
title: linkExternalFilters
description: linkExternalFilters 変数の使用は出口リンクの自動トラッキングに役立ちます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. `linkExternalFilters` 変数と [`linkInternalFilters`](linkinternalfilters.md) 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、出口リンクの自動トラッキングはホワイトリストのように動作します。リンククリックがどの `linkExternalFilters` 値とも一致しない場合、そのリンクは出口リンクと見なされません。この変数に対して URL 全体が調べられます。If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] この変数は、出口リンクと見なすドメインが正確にわかっている場合にのみ使用します。多くの組織では、出口リンクのトラッキングのニーズを満たすには `linkInternalFilters` を使用すれば十分であると考え、`linkExternalFilters`を使用しません。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが出口リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Adobe Experience Platform Launch の「アウトバウンドリンク - 追跡」

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Outbound Links - Track] されます。

常に外部と見なすフィルターをこのフィールドに配置します。複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Launch カスタムコードエディターの s.linkExternalFilters

`s.linkExternalFilters` 変数は、出口リンクと見なすフィルター（ドメインなど）を含む文字列です。複数のドメインは、スペースなしのコンマで区切ります。

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

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
