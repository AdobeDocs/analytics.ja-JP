---
title: linkInternalFilters
description: linkInternalFilters 変数の使用は離脱リンクの自動トラッキングに役立ちます。
feature: Appmeasurement Implementation
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
TQID: https://experienceleague.adobe.com/st-CkocgfEJIAQs1JTiY0DpUNuo2uU-CR-o8togtLGg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 100%

---

# linkInternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。 [`trackExternalLinks`](trackexternallinks.md)（AppMeasurement）または [`clickCollectionEnabled`](trackdownloadlinks.md)（Web SDK）が有効になっている場合、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。 [`linkExternalFilters`](linkexternalfilters.md) 変数と `linkInternalFilters` 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれる場合、離脱リンクの自動トラッキングはブロックリストのように動作します。 リンククリックがどの `linkInternalFilters` 値とも一致しない場合は、そのリンクは離脱リンクと見なされます。 この変数に対して URL 全体が調べられます。 [`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリ文字列も調べられます。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが離脱リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

Activity Map では、この変数を使用して、サイト内部のリンクを特定します。 アドビでは、Activity Map を使用する実装でこの変数を設定することをお勧めします。

>[!NOTE]
>
>`linkInternalFilters` および [内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)は、別々の目的を満たす個別の機能です。 `linkInternalFilters` 変数は、離脱リンクの追跡に特別に機能します。 内部 URL フィルターは、参照ドメインなどのトラフィックソースディメンションの操作に役立つ管理者設定です。

## Web SDK の離脱リンク

リンクターゲットドメインが現在の `window.location.hostname` と異なる場合は、リンクが自動的に離脱リンクとして選定されます。 Web SDK には、自動離脱リンク検出を変更するための設定変数は用意されていません。 離脱リンクとして選定するドメインをカスタマイズする必要がある場合、`onBeforeEventSend` コールバックでカスタムロジックを使用できます。

詳しくは、Web SDK ドキュメントの[自動リンクトラッキング](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja#automaticLinkTracking)を参照してください。

## Adobe Analytics 拡張機能を使用したアウトバウンドリンク - 追跡しない

「追跡しない」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡しない]」フィールドが表示されます。

離脱リンクとして追跡しないフィルターをこのフィールドに配置します。 複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.linkInternalFilters

`s.linkInternalFilters` 変数は、サイト内部と見なすフィルター（ドメインなど）を含む文字列です。 複数のフィルターは、スペースなしのコンマで区切ります。

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
