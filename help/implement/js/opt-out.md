---
title: オプトアウトリンク
description: サイトへの訪問者を対象にした実装オプトアウトリンクの作成方法を説明します。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# オプトアウトリンクの実装

> [!IMPORTANT] 特にGDPR規制に関する組織には、オプトインサービスの使用をお勧めします。 See [Opt-in service overview](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) in the Experience Cloud Identity Service user guide.

Webサイトへの訪問者の中には、自分の閲覧情報をデータセットに含めないことを好む訪問者もいます。 アドビでは、Webサイトの訪問者が収集した情報をオプトアウトする手段を提供する機能を提供しています。 すべての導入タイプに対応組織は、お客様自身のプライバシーポリシーを責任を持ち、署名済みの利用条件に従って責任を負います。

訪問者がオプトアウトURLに到達すると、オプトアウトCookieのインストールを促すメッセージが表示されます。 ユーザーが追跡を選択せず、オプトアウトcookieが設定されている場合、JavaScriptファイルは引き続きアドビのサーバーにデータを送信します。 ただし、そのデータは処理されず、レポートに含まれません。

> [!TIP] また、アドビでは、レポートスイートごとにプライバシー設定を提供しています。 詳しくは、管 [理者ユーザーガイドの](../../admin/admin/privacy-settings.md) 「プライバシー設定」を参照してください。

## オプトアウトURL

組織のオプトアウトページは、実装内の変数 [`trackingServer`](../vars/config-vars/trackingserver.md) 値に応じて異なります。

* Adobe Experience Platform Launch:
   1. launch.adobe.comにロ [グインし、目的のプロパティ](https://launch.adobe.com) をクリックします。
   2. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
   3. 「一般」アコ [!UICONTROL ーディオン] をクリックし、「トラッキングサーバ [!UICONTROL ー」の値をメモしま] す。

* JavaScript実装の場合：
   1. Webサーバー上で、サイトで使用しているAppMeasurement.jsファイルをコードエディターまたはテキストエディターで開きます。
   2. 変数の値をメモ `trackingServer` しておきます。

* Using the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. Chromeブラウザーを使用してサイトに移動します。
   2. Experience cloudデバッガーを開き、「ネットワーク」タブに移 [!UICONTROL 動します]。
   3. リクエストURL [!UICONTROL — ホスト名の値に注意してください] 。

実装のドメインが見つかったら、 `trackingServer` 最後にパスを追 `/optout.html` 加します。 次に例を示します。

* サードパーティcookie: `https://example.sc.omtrdc.net/optout.html`
* ファーストパーティ cookie: `https://stats.example.com/optout.html`

## オプトアウトクエリ文字列パラメータ

クエリ文字列を使用してこのページに自動的に読み込むことができる設定があります。

### 地域

クエリ文字列パラメーターを含めて、オプトアウトページの言語を自 `locale` 動的に切り替えます。 このクエリ文字列パラメーターに、次のいずれかの値を割り当てます。

* en_US（英語、デフォルト）
* bg_BG （ブルガリア語）
* zh_CN（簡体字中国語）
* zh_TW（繁体字中国語）
* cs_CZ（チェコ語）
* da_NK （デンマーク語）
* nl_NL （オランダ語）
* et_EE （エストニア語）
* fi_FI （フィンランド語）
* fr_FR （フランス語）
* de_DE（ドイツ語）
* el_GR （ギリシャ語）
* it_IT（イタリア語）
* jp_JP（日本語）
* ko_KR（韓国語）
* lv_LV （ラトビア語）
* lt_LT （リトアニア語）
* nb_NO （ノルウェー語）
* pl_PL （ポーランド語）
* pt_BR （ポルトガル語）
* sk_SK （スロバキア語）
* es_ES（スペイン語）

例えば、オプトア `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` ウトページを韓国語で読み込みます。

> [!TIP] ペー `en_US` ジはデフォルトで英語で読み込まれるので、クエリ文字列値は必須ではありません。

### ポップアップ

ページに「ウィンドウを閉じる」ボタンを追加して、オプトアウトページをポップアップウィンドウにする可能性を高めます。 クエリ文 `popup` 字列パラメーターを使用し、値をに指定します `1`。

例えば、「ウィン `https://example.sc.omtrdc.net/optout.html?popup=1` ドウを閉じる」ボタンを含むオプトアウトページを読み込みます。

> [!NOTE] このクエリ文字列パラメーターによって、ポップアップウィンドウが強制的に表示されました。 ただし、ほとんどの最新のブラウザーは、エンドユーザーに対してポップアップの制御を提供します。

### シングルクリックのオプトアウト

ユーザーが追跡を直ちにオプトアウトできるようにします。 2つのクエリ文字列パラメーターと `opt_out` を追加 `confirm_change`し、それぞれにの値を指定しま `1`す。

例えば、オプト `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` アウトcookieを訪問者のページに直ちにインストールします。

### シングルクリックのオプトイン

ユーザーがオプトアウトcookieを削除して、追跡を即座にオプトインできるようにします。 2つのクエリ文字列パラメーターと `opt_in` を追加 `confirm_change`し、それぞれにの値を指定しま `1`す。

例えば、訪問者 `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` のオプトアウトcookieを直ちに削除します。
