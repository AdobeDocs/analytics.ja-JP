---
title: linkExternalFilters
description: linkExternalFilters 変数の使用は離脱リンクの自動トラッキングに役立ちます。
feature: Appmeasurement Implementation
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mTFSu9z4xpENpqGTdzND5IvLqFsaV7GjWlY2WxtCTGc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 91%

---

# linkExternalFilters

AppMeasurement は、サイト外を指すリンクを自動的に追跡する機能を提供します。 [`trackExternalLinks`](trackexternallinks.md)（AppMeasurement）または [`clickCollectionEnabled`](trackexternallinks.md)（Web SDK）が有効になっている場合、訪問者がリンクをクリックしてサイトを離れると、イメージリクエストがアドビに直接送信されます。 `linkExternalFilters` 変数と [`linkInternalFilters`](linkinternalfilters.md) 変数は、リンクが外部と見なされるか内部と見なされるかを決定します。

この変数に値が含まれている場合、自動終了リンクトラッキングは許可リストのように動作します。 リンククリックがどの `linkExternalFilters` 値とも一致しない場合、そのリンクは離脱リンクと見なされません。 この変数に対して URL 全体が調べられます。 [`linkLeaveQueryString`](linkleavequerystring.md) が有効になっている場合は、クエリ文字列も調べられます。

>[!TIP]
>
>この変数は、離脱リンクと見なすドメインが正確にわかっている場合にのみ使用します。 多くの組織では、離脱リンクのトラッキングのニーズを満たすには `linkInternalFilters` を使用すれば十分であると考え、`linkExternalFilters`を使用しません。

`linkInternalFilters` と `linkExternalFilters` の両方を同時に使用する場合は、クリックされたリンクが離脱リンクと見なされるには、`linkExternalFilters` に一致すると&#x200B;**ともに** `linkInternalFilters` に一致しない必要があります。 クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Web SDK の離脱リンク

リンクターゲットドメインが現在の `window.location.hostname` と異なる場合は、リンクが自動的に離脱リンクとして選定されます。 Web SDK には、自動離脱リンク検出を変更するための設定変数は用意されていません。 離脱リンクとして選定するドメインをカスタマイズする必要がある場合、`onBeforeEventSend` コールバックでカスタムロジックを使用できます。

詳しくは、Web SDK ドキュメントの[自動リンクトラッキング](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja#automaticLinkTracking)を参照してください。

## アウトバウンドリンク - Adobe Analytics拡張機能を使用したトラッキング

「追跡」フィールドは、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるフィルター（通常はドメイン）のコンマ区切りリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンク - 追跡]」フィールドが表示されます。

常に外部と見なすフィルターをこのフィールドに配置します。 複数のドメインは、スペースなしのコンマで区切ります。

## AppMeasurementのs.linkExternalFiltersとAnalytics拡張機能のカスタムコードエディター

`s.linkExternalFilters` 変数は、離脱リンクと見なすフィルター（ドメインなど）を含む文字列です。 複数のドメインは、スペースなしのコンマで区切ります。

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
