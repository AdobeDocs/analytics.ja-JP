---
title: linkExternalFilters
description: linkExternalFilters 変数の使用は出口リンクの自動トラッキングに役立ちます。
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# linkExternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。[`trackExternalLinks`](trackexternallinks.md) が有効になっている場合、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。`linkExternalFilters` 変数と [`linkInternalFilters`](linkinternalfilters.md) 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、自動出口リンクトラッキングは許可リストのように動作します。リンククリックがどの `linkExternalFilters` 値とも一致しない場合、そのリンクは出口リンクと見なされません。この変数に対して URL 全体が調べられます。[`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリー文字列も調べられます。

>[!TIP]
>
> この変数は、出口リンクと見なすドメインが正確にわかっている場合にのみ使用します。多くの組織では、出口リンクのトラッキングのニーズを満たすには `linkInternalFilters` を使用すれば十分であると考え、`linkExternalFilters`を使用しません。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが出口リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Adobe Experience Platform Launch の「アウトバウンドリンク - 追跡」

「追跡」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡]」フィールドが表示されます。

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

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
