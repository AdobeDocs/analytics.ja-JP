---
title: linkInternalFilters
description: linkInternalFilters 変数の使用は離脱リンクの自動トラッキングに役立ちます。
feature: Variables
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 68%

---

# linkInternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。If [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) または [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) を有効にすると、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがAdobeに直接送信されます。 [`linkExternalFilters`](linkexternalfilters.md) 変数と `linkInternalFilters` 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、出口リンクの自動トラッキングはブロックリストのように動作します。 リンククリックがどの `linkInternalFilters` 値とも一致しない場合は、そのリンクは離脱リンクと見なされます。この変数に対して URL 全体が調べられます。[`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリ文字列も調べられます。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが離脱リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

Activity Map では、この変数を使用して、サイト内部のリンクを特定します。アドビでは、Activity Map を使用する実装でこの変数を設定することをお勧めします。

>[!NOTE]
>
>`linkInternalFilters` および [内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)は、別々の目的を満たす個別の機能です。`linkInternalFilters` 変数は、離脱リンクの追跡に特別に機能します。内部 URL フィルターは、参照ドメインなどのトラフィックソースディメンションの操作に役立つ管理者設定です。

## Web SDK の出口リンク

リンクのターゲットドメインが現在のドメインと異なる場合、リンクは自動的に出口リンクと見なされます `window.location.hostname`. Web SDK には、出口リンクの自動検出を変更する設定変数は用意されていません。 出口リンクと見なされるドメインをカスタマイズする必要がある場合は、 `onBeforeEventSend` コールバック。

詳しくは、 [自動リンクトラッキング](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したアウトバウンドリンク — 追跡しない

「追跡しない」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform データ収集](https://experience.adobe.com/data-collection)にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡しない]」フィールドが表示されます。

離脱リンクとして追跡しないフィルターをこのフィールドに配置します。複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.linkInternalFilters

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
