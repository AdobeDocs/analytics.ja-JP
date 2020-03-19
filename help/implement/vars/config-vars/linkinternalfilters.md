---
title: linkInternalFilters
description: 離脱リンクの自動追跡に役立つように、linkInternalFilters変数を使用します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkInternalFilters

AppMeasurementは、サイト外を指すリンクを自動的に追跡する機能を提供します。 を有効 [`trackExternalLinks`](trackexternallinks.md) にすると、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。 変数と変 [`linkExternalFilters`](linkexternalfilters.md) 数は、 `linkInternalFilters` どのリンクが内部/外部と見なされるかを決定します。

この変数に値が含まれる場合、離脱リンクの自動追跡はブラックリストのような動作をします。 リンクのクリックがどの値とも一致しな `linkInternalFilters` い場合、離脱リンクと見なされます。 URL全体がこの変数に対して調べられます。 が有効 [`linkLeaveQueryString`](linkleavequerystring.md) な場合、クエリ文字列も調べられます。

両方を同時に使用する場合 `linkInternalFilters` 、クリックさ `linkExternalFilters` れたリンクは一致する必要があり `linkExternalFilters` 、一致しないリンクは離脱リ ****`linkInternalFilters` ンクと見なされる必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクのタイプが優先されます。

> [!NOTE] 内部 `linkInternalFilters` URLフィルタ [ーと内部URLフィルターは](/help/admin/admin/internal-url-filter-admin.md) 、別々の目的を満たす個別の機能です。 この変数 `linkInternalFilters` は、離脱リンクの追跡に特別に機能します。 内部URLフィルターは、参照ドメインなどのトラフィックソースディメンションを扱うのに役立つ管理者設定です。

## アウトバウンドリンク — Adobe Experience Platformの起動で追跡しない

「追跡しない」フィールドは、Adobe Analyticsの拡張機能を設定する際に、アコーディオンの下にあるフィルター( [!UICONTROL Link Tracking] 通常はドメイン)のコンマ区切りリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Outbound Links - Never Track] されます。

離脱リンクとして追跡しないフィルターをこのフィールドに配置します。 複数のドメインは、コンマで区切ります。スペースは使用しません。

## AppMeasurementのs.linkInternalFiltersとカスタムコードエディターの起動

この変 `s.linkInternalFilters` 数は、サイト内部のフィルター（ドメインなど）を含む文字列です。 複数のフィルターを指定する場合は、コンマでスペースを使用せずに区切ります。

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

次の実装例を、オンの場合と同様に考えてみま `adobe.com`す。

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
