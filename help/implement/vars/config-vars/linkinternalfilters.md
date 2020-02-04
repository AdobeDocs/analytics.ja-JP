---
title: linkInternalFilters
description: 離脱リンクの自動追跡に役立つように、linkInternalFilters変数を使用します。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

AppMeasurementは、サイト外を指すリンクを自動的に追跡する機能を提供します。 の場合、 `trackExternalLinks` 訪問者が `true`リンクをクリックしてサイトを離脱すると、イメージリクエストがアドビに直接送信されます。 変数と `linkTrackExternalFilters` 変数は、 `linkTrackInternalFilters` どのリンクが内部/外部と見なされるかを決定します。

この変数に値が含まれる場合、離脱リンクの自動トラッキングはブラックリストのような動作をします。 リンクのクリック数がどの値とも一致しな `linkInternalFilters` い場合は、離脱リンクと見なされます。 この変数に対してURL全体が調べられます。 が含まれ `linkLeaveQueryString` ている場 `true`合は、クエリ文字列も調べられます。

との両方を同時に使用する場 `linkInternalFilters` 合は、クリックされたリ `linkExternalFilters` ンクが一致し `linkExternalFilters` 、離脱リンクと見なされ ****`linkInternalFilters` ないようにする必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

> [!NOTE] 内部URL `linkInternalFilters` フィルターは、別々の目的を満たす個別の機能です。 この変数 `linkInternalFilters` は、離脱リンクの追跡に特別に機能します。 内部URLフィルターは、参照ドメインなどのトラフィックソースディメンションの操作に役立つ管理者設定です。 See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## アウトバウンドリンク — Adobe Experience Platformの起動で追跡しない

「追跡しない」フィールドは、Adobe Analytics拡張機能を設定する際に、「リンクトラッキング  」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッ [!UICONTROL キング] 」アコーディオンを展開すると、「アウトバウンドリンク [!UICONTROL — 追跡しない] 」フィールドが表示されます。

離脱リンクとして追跡しないフィルターをこのフィールドに配置します。 複数のドメインは、コンマで区切ります。スペースは使用できません。

## AppMeasurementのs.linkInternalFiltersとカスタムコードエディターの起動

この変 `s.linkInternalFilters` 数は、サイト内部と見なすフィルター（ドメインなど）を含む文字列です。 複数のフィルターを指定する場合は、コンマでスペースを入れずに区切ります。

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

次の実装例をオンの場合と同様に考えま `adobe.com`す。

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
