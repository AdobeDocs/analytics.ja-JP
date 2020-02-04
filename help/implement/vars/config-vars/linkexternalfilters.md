---
title: linkExternalFilters
description: 離脱リンクの自動追跡に役立つように、linkExternalFilters変数を使用します。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkExternalFilters

AppMeasurementは、サイト外を指すリンクを自動的に追跡する機能を提供します。 の場合、 `trackExternalLinks` 訪問者が `true`リンクをクリックしてサイトを離脱すると、イメージリクエストがアドビに直接送信されます。 変数と `linkTrackExternalFilters` 変数は、 `linkTrackInternalFilters` どのリンクが内部/外部と見なされるかを決定します。

この変数に値が含まれる場合、離脱リンクの自動トラッキングはホワイトリストのような動作をします。 リンクのクリックがどの値とも一致しな `linkExternalFilters` い場合、そのリンクは離脱リンクと見なされません。 この変数に対してURL全体が調べられます。 が含まれ `linkLeaveQueryString` ている場 `true`合は、クエリ文字列も調べられます。

> [!TIP] この変数は、離脱リンクと見なすドメインが正確にわかっている場合にのみ使用します。 多くの組織では、離脱リンクのトラ `linkInternalFilters` ッキングのニーズを満たすにはを使用すれば十分で、を使用しないと考えていま `linkExternalFilters`す。

との両方を同時に使用する場 `linkInternalFilters` 合は、クリックされたリ `linkExternalFilters` ンクが一致し `linkExternalFilters` 、離脱リンクと見なされ ****`linkInternalFilters` ないようにする必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## アウトバウンドリンク — Adobe Experience Platform Launchでの追跡

「追跡」フィールドは、Adobe Analytics拡張機能を設定する際に、「リンクトラッキング  」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッ [!UICONTROL キング] 」アコーディオンを展開すると、「アウトバウンドリン [!UICONTROL ク — 追跡」フィールドが表示されます] 。

常に外部と見なすフィルターをこのフィールドに配置します。 複数のドメインは、コンマで区切ります。スペースは使用できません。

## AppMeasurementのs.linkExternalFiltersとカスタムコードエディターの起動

この変 `s.linkExternalFilters` 数は、離脱リンクと見なすフィルター（ドメインなど）を含む文字列です。 複数のドメインはコンマで区切り、スペースは使用しません。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

次の実装例をオンの場合と同様に考えま `adobe.com`す。

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is not considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
