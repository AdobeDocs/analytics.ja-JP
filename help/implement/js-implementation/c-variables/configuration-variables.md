---
description: Configuration variables set in AppMeasurement.js.
keywords: Analytics の実装
seo-description: AppMeasurement.jsで設定されたAdobe Analytics用の設定変数
seo-title: 設定変数
solution: Analytics
subtopic: 変数
title: 設定変数
topic: 開発者と実装
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 9212d70ab8fd7bc0ccfb7e781a92b1731f0a40bd

---


# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). これらの変数は、必要に応じて、Analyticsのページレベルコード内およびリンク内に設定できます。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. これらの設定変数の一部は、サイトの導入ニーズに当てはまらない可能性があります。

これらの設定変数を使用するうえでの目標の一部を次に示します。

* 複数のサイト／ドメインをトラッキングする。
* 購入時に任意の通貨を使用する。
* データに無関係な言語を取得する。
* リンクトラッキング（ダウンロードしたファイルの数、外部サイトへのリンク数）。
* 独自の用途でカスタムリンクをトラッキングする。

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. の呼び出しの後に設定変数が設定されている場合、予期しな `t()`い結果が発生する可能性があります。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

特定の設定変数に関するヘルプが必要な場合は、次のリンクをクリックしてください。

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):データの保存とレポートを行うレポートスイートを指定します。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):各ページのURLに基づいてレポートスイートを動的に選択します。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):送信先レポートスイートの決定に使用するルールを指定します。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):DOMオブジェクトを使用して、すべてのルールが適用されるURLのセクションを取得します。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):動的に設定された変数のデプロイフラグ。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):受信データをUTF-8に変換して、Analyticsでの保存とレポートを可能にします。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):売上高に適用するコンバージョン率を決定します。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):CookieとCookieを設定するド `s_cc` メイン `s_sq` を決定します。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):ページURLのドメイン `s_cc` 内のピ `s_sq` リオド数を指定して、のドメインとcookieを決定します。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):JavaScript（、プラグイン）によって設定さ`s_sq`れた、本質的にファ `s_cc`ーストパーティのCookie（サードパーティまたはドメインを含む）を `2o7.net` 指定 `omtrdc.net` します。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):JavaScriptとデータ収集サーバーの両方で処理されるcookieの有効期限を決定します。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):JavaScriptファイル内の適切な場所で関数を参照し、呼び出すことを許可します。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):コールバック（関数）とその関数のパラメーターの両方をパラメーターとして取る関数。

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):コールバック（関数）とその関数のパラメーターの両方をパラメーターとして取る関数。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):サイト上のダウンロード可能ファイルへのリンクを追跡します。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):クリックされたリンクが離脱リンクであるかどうかを判定します。

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):ClickMapデータを収集するかどうかを決定します。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):ファイル拡張子のコンマ区切りリストを含めます。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):サイトの一部であるリンクを表すフィルターのコンマ区切りリストが含まれます。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):クエリ文字列を離脱リンクおよびファイルのダウンロード数レポートに含めるかどうかを決定します。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):カスタムリンク、離脱リンクおよびダウンロードリンクで送信される変数のコンマ区切りリストを含めます。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):離脱リンクの特定のサブセットに関するレポートを作成するために使用します。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):各イメージリクエ `s_doPlugins` ストの前に関数を呼び出します。

