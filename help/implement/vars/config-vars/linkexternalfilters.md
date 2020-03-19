---
title: linkExternalFilters
description: 離脱リンクの自動追跡に役立つように、linkExternalFilters変数を使用します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkExternalFilters

AppMeasurementは、サイト外を指すリンクを自動的に追跡する機能を提供します。 を有効 [`trackExternalLinks`](trackexternallinks.md) にすると、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。 変数と変 `linkExternalFilters` 数は、 [`linkInternalFilters`](linkinternalfilters.md) どのリンクが内部/外部と見なされるかを決定します。

この変数に値が含まれる場合、離脱リンクの自動追跡はホワイトリストのような動作をします。 リンクのクリックがどの値とも一致しな `linkExternalFilters` い場合、離脱リンクとは見なされません。 URL全体がこの変数に対して調べられます。 が有効 [`linkLeaveQueryString`](linkleavequerystring.md) な場合、クエリ文字列も調べられます。

> [!TIP] この変数は、離脱リンクと見なすドメインが正確にわかっている場合にのみ使用します。 多くの組織では、を使用するだけで `linkInternalFilters` 離脱リンクトラッキングのニーズを満たすことができ、を使用しないと考えていま `linkExternalFilters`す。

両方を同時に使用する場合 `linkInternalFilters` 、クリックさ `linkExternalFilters` れたリンクは一致する必要があり `linkExternalFilters` 、一致しないリンクは離脱リ ****`linkInternalFilters` ンクと見なされる必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクのタイプが優先されます。

## アウトバウンドリンク — Adobe Experience Platform Launchで追跡

「追跡」フィールドは、Adobe Analyticsの拡張機能を設定する際に、アコーディオンの下に表示されるフ [!UICONTROL Link Tracking] ィルター（通常はドメイン）のコンマ区切りリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Outbound Links - Track] されます。

常に外部と見なすフィルターをこのフィールドに配置します。 複数のドメインは、コンマで区切ります。スペースは使用しません。

## AppMeasurementのs.linkExternalFiltersとカスタムコードエディターの起動

この変 `s.linkExternalFilters` 数は、離脱リンクと見なすフィルター（ドメインなど）を含む文字列です。 複数のドメインは、コンマで区切ります。スペースは使用しません。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

次の実装例を、オンの場合と同様に考えてみま `adobe.com`す。

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
