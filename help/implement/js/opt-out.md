---
title: オプトアウトリンク
description: サイトへの訪問者を対象にしたオプトアウトリンクの作成方法を説明します。
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 67%

---

# オプトアウトリンクの実装

>[!IMPORTANT]
>
> この記事では、Web サイトにAdobe Analyticsを実装する **Adobe Analyticsのお客様に** Web サイトのユーザーにオプトアウトリンクを提供する方法を説明します。 <p><p>
><p>-ERR:REF-NOT-FOUND-<p>-ERR:REF-NOT-FOUND-> **Adobe Analyticsを実装した web サイトにアクセス** していて、オプトアウトする場合 **<span style="color:red">この記事は該当しません</span>**。 Adobeでの情報の使用方法を制御するには、[Adobeのプライバシーの選択肢 &#x200B;](https://www.adobe.com/jp/privacy/opt-out.html) を参照してください。

Web サイトへの訪問者の中には、自分の閲覧情報をデータセットに含めないことを好む訪問者もいます。Adobeでは、Web サイトの訪問者に、分析中の情報をオプトアウトする手段を提供できます。

オプトアウトリンクを使用すると、web サイトの訪問者が、Analytics のレポートからデータを省略できます。 これらのリンクは、AppMeasurement実装に限定されます。Adobeでは、代わりに [Adobe Experience Cloud オプトインサービスを使用することをお勧め &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja) ます。 オプトインサービスはより堅牢で、Adobe AnalyticsやAppMeasurementなど、複数のAdobe Experience Cloud製品で機能します。

訪問者がオプトアウト URL にアクセスすると、オプトアウト Cookie のインストールを促すメッセージが表示されます。ユーザーがトラッキングされないことを選択し、オプトアウト cookie が設定されている場合、AppMeasurementは引き続きAdobeにデータを送信します。 ただし、そのデータは処理されず、レポートに含まれません。

>[!TIP]
>
> また、アドビでは、レポートスイートごとにプライバシー設定を提供しています。詳しくは、『管理者ユーザーガイド』の[プライバシー設定](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md)を参照してください。

## オプトアウト URL

組織のオプトアウトページは、実装内の [`trackingServer`](../vars/config-vars/trackingserver.md) 変数値に応じて異なります。

* Analytics 拡張機能で：
   1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
   1. 目的のタグプロパティをクリックします。
   1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics で「[!UICONTROL 設定]」をクリックします。
   1. 「[!UICONTROL 一般]」アコーディオンをクリックし、「[!UICONTROL トラッキングサーバー]」の値をメモします。

* JavaScript 実装の場合：
   1. Web サーバー上で、サイトで使用している AppMeasurement.js ファイルをコードエディターまたはテキストエディターで開きます。
   1. `trackingServer` 変数の値をメモしておきます。

* [Adobe Experience Cloud デバッガー](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html)を使用して、以下を実行します。
   1. Chrome ブラウザーを使用してサイトに移動します。
   1. Experience Cloud デバッガーを開き、「[!UICONTROL ネットワーク]」タブに移動します。
   1. 「[!UICONTROL リクエスト URL - ホスト名]」の値に注意してください。

実装の `trackingServer` ドメインが見つかったら、最後にパス `/optout.html` を追加します。次に例を示します。

* サードパーティ Cookie： `https://example.data.adobedc.net/optout.html`
* ファーストパーティ Cookie：`https://stats.example.com/optout.html`

## オプトアウトクエリ文字列パラメーター

クエリ文字列を使用してこのページに自動的に読み込むことができる設定があります。

### ロケール

`locale` クエリ文字列パラメーターを含めて、オプトアウトページの言語を自動的に切り替えます。このクエリ文字列パラメーターに、次のいずれかの値を割り当てます。

* `en_US` （英語、デフォルト）
* `bg_BG` （ブルガリア語）
* `zh_CN` （簡体字中国語）
* `zh_TW` （繁体字中国語）
* `cs_CZ` （チェコ語）
* `da_NK` （デンマーク語）
* `nl_NL` （オランダ語）
* `et_EE` （エストニア語）
* `fi_FI` （フィンランド語）
* `fr_FR` （フランス語）
* `de_DE` （ドイツ語）
* `el_GR` （ギリシャ語）
* `it_IT` （イタリア語）
* `jp_JP` （日本語）
* `ko_KR` （韓国語）
* `lv_LV` （ラトビア語）
* `lt_LT` （リトアニア語）
* `nb_NO` （ノルウェー語）
* `pl_PL` （ポーランド語）
* `pt_BR` （ポルトガル語）
* `sk_SK` （スロバキア語）
* `es_ES` （スペイン語）

例えば、`https://example.data.adobedc.net/optout.html?locale=ko_KR` は、オプトアウトページを韓国語で読み込みます。

### ポップアップ

ページに「ウィンドウを閉じる」ボタンを追加すると、オプトアウトページをポップアップウィンドウにすることができます。`popup` クエリ文字列パラメーターを使用し、`1` 値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?popup=1` は、「ウィンドウを閉じる」ボタンを含むオプトアウトページを読み込みます。

>[!NOTE]
>
>以前は、このクエリ文字列パラメーターによって、ポップアップウィンドウが強制的に表示されました。ただし、ほとんどの最新のブラウザーは、エンドユーザーに対してポップアップの制御を提供します。

### シングルクリックのオプトアウト

ユーザーが追跡を直ちにオプトアウトできるようにします。`opt_out` と `confirm_change` の 2 つのクエリ文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` は、オプトアウト Cookie を訪問者のページに直ちにインストールします。

### シングルクリックのオプトイン

ユーザーがオプトアウト Cookie を削除して、追跡を即座にオプトインできるようにします。`opt_in` と `confirm_change` の 2 つのクエリ文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` は、訪問者のオプトアウト Cookie を直ちに削除します。
