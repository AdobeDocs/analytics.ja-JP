---
description: オプトアウトリンクを指定し、リンクのブランディングをカスタマイズします。Web サイトの訪問者は、データ収集ドメインのオプトアウトページを開いて、自分の行動が Adobe Analytics 製品でトラッキングされないように選択することができます。
keywords: Analytics の導入
seo-description: オプトアウトリンクを指定し、リンクのブランディングをカスタマイズします。Web サイトの訪問者は、データ収集ドメインのオプトアウトページを開いて、自分の行動が Adobe Analytics 製品でトラッキングされないように選択することができます。
seo-title: オプトアウトリンクの追加
solution: Analytics
subtopic: トラブルシューティング
title: オプトアウトリンクの追加
topic: 開発者と導入
uuid: c12092be-3be7-4621- b838- d6b78d074f84
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# オプトアウトリンクの追加

オプトアウトリンクを指定し、リンクのブランディングをカスタマイズします。Web サイトの訪問者は、データ収集ドメインのオプトアウトページを開いて、自分の行動が Adobe Analytics 製品でトラッキングされないように選択することができます。

ユーザーがトラッキングされないことを選択し、オプトアウト cookie が設定された場合、JavaScript ファイルは引き続きアドビのサーバーにデータを送信しますが、そのデータが処理されたり、レポートの作成に使用されたりすることはなくなります。

URL 構成の collection_domain セクションが、JavaScript ファイルで使用される trackingServer です。Adobe Analytics の導入に使用されている収集ドメインは、Adobe Analytics テーブルの 1 行目の DigitalPulse Debugger で確認できます。導入方法に応じて、「First Party Cookies」または「Third Party Cookies」という見出しが付けられています。Web サイトの収集ドメインには、2o7.net、omtrdc.net またはお客様が所有する Web サイトドメイン（例えば metrics.example.com など）が含まれる場合があります。

訪問者がオプトアウトページのリンクをクリックすると、cookie がブラウザーに設定されます。対象のトラッキングドメインに対して `omniture_optout` cookie を設定することで、そのユーザーのアクティビティが Adobe Analytics のレポートに含まれなくなります。オプトアウト cookie へのリンクを独自に用意するか、以下の手順に従ってオプトアウト cookie を設定します。

アドビでは、すべての導入タイプに応じたオプトアウト方法を用意しています。お客様は自身のプライバシーポリシーに責任を負うとともに、それ以外にお客様が署名した規約を遵守する責任を負います。ここで説明しているように、導入タイプに応じてオプトアウトページへのリンクが変わることに注意してください。

アドビが所有するドメイン（つまり、207.net または omtrdc.net）に設定された cookie を使用して Adobe Analytics 製品およびサービスを導入した場合、Adobe Analytics の製品およびサービスに対応するアドビ cookie を使用するすべてのサイトについて、[アドビプライバシーセンター](https://www.adobe.com/privacy/opt-out.html)で提供されるオプトアウトメカニズムへのリンクを Web サイトに設置できます。The direct link to the Adobe opt-out mechanism is `https:// *collection_domain* /optout.html`.

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [オプトアウトページの URL 構成](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [オプトアウト URL の例](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [オプトアウト URL のブランディング](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## オプトアウトページの URL 構成 {#section_E0462428D2E440E7863E24D2F6DBF748}

オプトアウトページの URL は以下のようになります。

```
https://collection_domain/optout.html[?optional_parameters]
```

The `optional_parameters` include:

`locale=[code]`:翻訳版のオプトアウトページを提供します。以下のロケールがサポートされています。

* en_US（デフォルト）
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`：ページをポップアップとして開き、「ウィンドウを閉じる」ボタンを表示します。

## オプトアウト URL の例 {#section_258DE5226AA0483CA790D2C9C5318B2E}

英語版の Web ページが通常のウィンドウで表示されます。ページ内のリンクをクリックすると、訪問者が metrics.example.com でトラッキングされないようになります。

```
https://metrics.example.com/optout.html
```

フランス語版の Web ページが通常のウィンドウで表示されます。ページ内のリンクをクリックすると、訪問者が example.d3.sc.omtrdc.net でトラッキングされないようになります。

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

ドイツ語版の Web ページがポップアップウィンドウで表示されます。ページ内のリンクをクリックすると、訪問者が example.112.2o7.net でトラッキングされないようになります。

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## オプトアウト URL のブランディング {#section_674AB62E810B414AB8F1615C0E3061F8}

次のようなリンクを、Web サイトの任意の場所に設定できます。

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

ここで、「*`stats.adobe.com`* は、 *`s.trackingServer`* 変数が設定されているものに置き換えられます。

Additionally, if you want like to provide a link to opt-in, use the same URL, but replace `?optout=1` with `?optin=1`, and keep the `confirm_change=1`.
