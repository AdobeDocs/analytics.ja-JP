---
title: オプトアウトリンク
description: サイトへの訪問者を対象にしたオプトアウトリンクの作成方法を説明します。
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
role: Developer
TQID: https://experienceleague.adobe.com/3X3RsfI3J96Ml4Q2UvnaaPLfBihSPvD-bfE8-yZujzU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 69%

---

# オプトアウトリンクの実装

>[!IMPORTANT]
>
> この記事では、Adobe Analytics **をweb サイトに実装する** Adobe Analyticsのお客様に、オプトアウトリンクをweb サイトのユーザーに提供する方法について説明します。 <p><p>> Adobe Analytics **を実装したweb サイトを**&#x200B;訪問していて、オプトアウトする場合、**<span style="color:red">この記事はあなたのためではありません</span>**。Adobeによる個人情報の使用方法については、[Adobe プライバシーに関する選択](https://www.adobe.com/jp/privacy/opt-out.html)を参照してください。

Web サイトへの訪問者の中には、自分の閲覧情報をデータセットに含めないことを好む訪問者もいます。 Adobeでは、web サイトへの訪問者に対して、分析中の情報をオプトアウトする手段を提供できます。

オプトアウトリンクは、web サイトへの訪問者に対して、Analytics レポートからデータを省略できるようにする方法です。 これらのリンクはAppMeasurementの実装に限定されます。Adobeでは、代わりに[Adobe CX Enterprise オプトインサービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)を使用することをお勧めします。 オプトインサービスは、より堅牢で、Adobe AnalyticsやAppMeasurementなどの、複数のAdobe CX Enterprise製品で機能します。

訪問者がオプトアウト URL にアクセスすると、オプトアウト Cookie のインストールを促すメッセージが表示されます。 ユーザーがトラッキングを行わないことを選択し、オプトアウト Cookieが設定されている場合、AppMeasurementは引き続きAdobeにデータを送信します。 ただし、そのデータは処理されず、レポートに含まれません。

>[!TIP]
>
>また、アドビでは、レポートスイートごとにプライバシー設定を提供しています。 詳しくは、『管理者ユーザーガイド』の[プライバシー設定](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md)を参照してください。

## オプトアウト URL

組織のオプトアウトページは、実装内の [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 変数値に応じて異なります。

* Analytics拡張機能で、次の操作を行います。
   1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
   1. 目的のタグプロパティをクリックします。
   1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics で「[!UICONTROL 設定]」をクリックします。
   1. 「[!UICONTROL 一般]」アコーディオンをクリックし、「[!UICONTROL トラッキングサーバー]」の値をメモします。

* JavaScript 実装の場合：
   1. Web サーバー上で、サイトで使用している AppMeasurement.js ファイルをコードエディターまたはテキストエディターで開きます。
   1. `trackingServer` 変数の値をメモしておきます。

* [Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html)を使用：
   1. Chrome ブラウザーを使用してサイトに移動します。
   1. CX Enterprise Debuggerを開き、[!UICONTROL &#x200B; ネットワーク タブ &#x200B;]に移動します。
   1. 「[!UICONTROL リクエスト URL - ホスト名]」の値に注意してください。

実装の `trackingServer` ドメインが見つかったら、最後にパス `/optout.html` を追加します。 次に例を示します。

* サードパーティ Cookie： `https://example.data.adobedc.net/optout.html`
* ファーストパーティ Cookie：`https://stats.example.com/optout.html`

## オプトアウトクエリ文字列パラメーター

クエリ文字列を使用してこのページに自動的に読み込むことができる設定があります。

### ロケール

`locale` クエリ文字列パラメーターを含めて、オプトアウトページの言語を自動的に切り替えます。 このクエリ文字列パラメーターに、次のいずれかの値を割り当てます。

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

ページに「ウィンドウを閉じる」ボタンを追加すると、オプトアウトページをポップアップウィンドウにすることができます。 `popup` クエリ文字列パラメーターを使用し、`1` 値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?popup=1` は、「ウィンドウを閉じる」ボタンを含むオプトアウトページを読み込みます。

>[!NOTE]
>
>以前は、このクエリ文字列パラメーターによって、ポップアップウィンドウが強制的に表示されました。 ただし、ほとんどの最新のブラウザーは、エンドユーザーに対してポップアップの制御を提供します。

### シングルクリックのオプトアウト

ユーザーが追跡を直ちにオプトアウトできるようにします。 `opt_out` と `confirm_change` の 2 つのクエリ文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` は、オプトアウト Cookie を訪問者のページに直ちにインストールします。

### シングルクリックのオプトイン

ユーザーがオプトアウト Cookie を削除して、追跡を即座にオプトインできるようにします。 `opt_in` と `confirm_change` の 2 つのクエリ文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` は、訪問者のオプトアウト Cookie を直ちに削除します。
