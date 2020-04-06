---
title: linkInternalFilters
description: linkInternalFilters 変数の使用は出口リンクの自動トラッキングに役立ちます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkInternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. [`linkExternalFilters`](linkexternalfilters.md) 変数と `linkInternalFilters` 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、出口リンクの自動トラッキングはブラックリストのように動作します。リンククリックがどの `linkInternalFilters` 値とも一致しない場合は、そのリンクは出口リンクと見なされます。この変数に対して URL 全体が調べられます。If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが出口リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

>[!NOTE] および `linkInternalFilters`[](/help/admin/admin/internal-url-filter-admin.md) 内部 URL フィルターは、別々の目的を満たす個別の機能です。`linkInternalFilters` 変数は、出口リンクの追跡に特別に機能します。内部 URL フィルターは、参照ドメインなどのトラフィックソースディメンションの操作に役立つ管理者設定です。

## Adobe Experience Platform Launch の「アウトバウンドリンク - 追跡しない」

The Never Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Outbound Links - Never Track] されます。

出口リンクとして追跡しないフィルターをこのフィールドに配置します。複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Launch カスタムコードエディターの s.linkInternalFilters

`s.linkInternalFilters` 変数は、サイト内部と見なすフィルター（ドメインなど）を含む文字列です。複数のフィルターは、スペースなしのコンマで区切ります。

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

次の実装例を `adobe.com` にあるとして考えます。

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
