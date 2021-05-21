---
title: linkInternalFilters
description: linkInternalFilters 変数の使用は出口リンクの自動トラッキングに役立ちます。
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# linkInternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。[`trackExternalLinks`](trackexternallinks.md) が有効になっている場合、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。[`linkExternalFilters`](linkexternalfilters.md) 変数と `linkInternalFilters` 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、出口リンクの自動トラッキングはブロックリストのように動作します。リンククリックがどの `linkInternalFilters` 値とも一致しない場合は、そのリンクは出口リンクと見なされます。この変数に対して URL 全体が調べられます。[`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリー文字列も調べられます。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが出口リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

Activity Map では、この変数を使用して、サイト内部のリンクを特定します。 アドビでは、Activity Map を使用する実装でこの変数を設定することをお勧めします。

>[!NOTE]
>
>`linkInternalFilters` および [内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md)は、別々の目的を満たす個別の機能です。`linkInternalFilters` 変数は、出口リンクの追跡に特別に機能します。内部 URL フィルターは、参照ドメインなどのトラフィックソースディメンションの操作に役立つ管理者設定です。

## Adobe Experience Platform Launch の「アウトバウンドリンク - 追跡しない」

「追跡しない」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡しない]」フィールドが表示されます。

出口リンクとして追跡しないフィルターをこのフィールドに配置します。複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Launch カスタムコードエディターの s.linkInternalFilters

`s.linkInternalFilters` 変数は、サイト内部と見なすフィルター（ドメインなど）を含む文字列です。複数のフィルターは、スペースなしのコンマで区切ります。

```js
s.linkInternalFilters = "example.com,example.net";
```

次の実装例を `adobe.com` にあるとして考えます。

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
