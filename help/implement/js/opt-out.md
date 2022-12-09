---
title: オプトアウトリンク
description: サイトへの訪問者を対象にしたオプトアウトリンクの作成方法を説明します。
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 99%

---

# オプトアウトリンクの実装

>[!IMPORTANT]
>
> 特に GDPR 規制への懸念がある組織では、オプトインサービスの使用をお勧めします。『Experience Cloud ID サービスユーザーガイド』の[オプトインサービスの概要](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)を参照してください。

Web サイトへの訪問者の中には、自分の閲覧情報をデータセットに含めないことを好む訪問者もいます。アドビでは、Web サイトの訪問者が自分の情報が収集されないようにする機能を用意しています。この機能はすべての実装タイプに対応しています。組織は、自らのプライバシーポリシーに責任を持ち、署名済みの利用条件に従う責任を負うものとします。

訪問者がオプトアウト URL にアクセスすると、オプトアウト Cookie のインストールを促すメッセージが表示されます。ユーザーが追跡を選択せず、オプトアウト Cookie が設定されている場合、JavaScript ファイルは引き続きアドビのサーバーにデータを送信します。ただし、そのデータは処理されず、レポートに含まれません。

>[!TIP]
>
> また、アドビでは、レポートスイートごとにプライバシー設定を提供しています。詳しくは、『管理者ユーザーガイド』の[プライバシー設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)を参照してください。

## オプトアウト URL

組織のオプトアウトページは、実装内の [`trackingServer`](../vars/config-vars/trackingserver.md) 変数値に応じて異なります。

* Analytics 拡張機能では、以下の操作をおこないます。
   1. Adobe ID 資格情報を使用して、[Adobe Experience Platform データ収集](https://experience.adobe.com/data-collection)にログインします。
   1. 目的のタグプロパティをクリックします。
   1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics で「[!UICONTROL 設定]」をクリックします。
   1. 「[!UICONTROL 一般]」アコーディオンをクリックし、「[!UICONTROL トラッキングサーバー]」の値をメモします。

* JavaScript 実装の場合：
   1. Web サーバー上で、サイトで使用している AppMeasurement.js ファイルをコードエディターまたはテキストエディターで開きます。
   1. `trackingServer` 変数の値をメモしておきます。

* [Adobe Experience Cloud デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用して、以下を実行します。
   1. Chrome ブラウザーを使用してサイトに移動します。
   1. Experience Cloud デバッガーを開き、「[!UICONTROL ネットワーク]」タブに移動します。
   1. 「[!UICONTROL リクエスト URL - ホスト名]」の値に注意してください。

実装の `trackingServer` ドメインが見つかったら、最後にパス `/optout.html` を追加します。次に例を示します。

* サードパーティ Cookie： `https://example.data.adobedc.net/optout.html`
* ファーストパーティ Cookie：`https://stats.example.com/optout.html`

## オプトアウトクエリー文字列パラメーター

クエリー文字列を使用してこのページに自動的に読み込むことができる設定があります。

### 地域

`locale` クエリー文字列パラメーターを含めて、オプトアウトページの言語を自動的に切り替えます。このクエリー文字列パラメーターに、次のいずれかの値を割り当てます。

* en_US（英語、デフォルト）
* bg_BG（ブルガリア語）
* zh_CN（簡体字中国語）
* zh_TW（繁体字中国語）
* cs_CZ（チェコ語）
* da_NK（デンマーク語）
* nl_NL（オランダ語）
* et_EE（エストニア語）
* fi_FI（フィンランド語）
* fr_FR（フランス語）
* de_DE（ドイツ語）
* el_GR（ギリシャ語）
* it_IT（イタリア語）
* jp_JP（日本語）
* ko_KR（韓国語）
* lv_LV（ラトビア語）
* lt_LT（リトアニア語）
* nb_NO（ノルウェー語）
* pl_PL（ポーランド語）
* pt_BR（ポルトガル語）
* sk_SK（スロバキア語）
* es_ES（スペイン語）

例えば、`https://example.data.adobedc.net/optout.html?locale=ko_KR` は、オプトアウトページを韓国語で読み込みます。

>[!TIP]
>
> ページはデフォルトで英語で読み込まれるので、`en_US` クエリー文字列値は必須ではありません。

### ポップアップ

ページに「ウィンドウを閉じる」ボタンを追加すると、オプトアウトページをポップアップウィンドウにすることができます。`popup` クエリー文字列パラメーターを使用し、`1` 値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?popup=1` は、「ウィンドウを閉じる」ボタンを含むオプトアウトページを読み込みます。

>[!NOTE]
>
> 歴史的に、このクエリー文字列パラメーターによって、ポップアップウィンドウが強制的に表示されました。ただし、ほとんどの最新のブラウザーは、エンドユーザーに対してポップアップの制御を提供します。

### シングルクリックのオプトアウト

ユーザーが追跡を直ちにオプトアウトできるようにします。`opt_out` と `confirm_change` の 2 つのクエリー文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` は、オプトアウト Cookie を訪問者のページに直ちにインストールします。

### シングルクリックのオプトイン

ユーザーがオプトアウト Cookie を削除して、追跡を即座にオプトインできるようにします。`opt_in` と `confirm_change` の 2 つのクエリー文字列パラメーターを追加し、それぞれに `1` の値を指定します。

例えば、`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` は、訪問者のオプトアウト Cookie を直ちに削除します。
