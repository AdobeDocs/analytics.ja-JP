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
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。最も一般的な設定変数は、通常、メインのグローバルJavaScript appMeasurement.jsに設定されます。 これらの変数は、必要に応じて、Analyticsのページレベルコード内およびリンク内に設定できます。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. これらの設定変数の一部は、サイトの導入ニーズに当てはまらない可能性があります。

これらの設定変数を使用するうえでの目標の一部を次に示します。

* 複数のサイト／ドメインをトラッキングする。
* 購入時に任意の通貨を使用する。
* データに無関係な言語を取得する。
* リンクトラッキング（ダウンロードしたファイルの数、外部サイトへのリンク数）。
* 独自の用途でカスタムリンクをトラッキングする。

>[!NOTE]
>
>[!DNL AppMeasurement] は、track関数の最初の呼び出しの前に、すべての設定変数が設定されている必要がありま `t()`す。 の呼び出しの後に設定変数が設定されている場合、予期しな `t()`い結果が発生する可能性があります。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

特定の設定変数に関するヘルプが必要な場合は、次のリンクをクリックしてください。

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):データの保存とレポートを行うレポートスイートを指定します。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html):各ページのURLに基づいてレポートスイートを動的に選択します。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html):送信先レポートスイートの決定に使用するルールを指定します。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html):DOMオブジェクトを使用して、すべてのルールが適用されるURLのセクションを取得します。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html):動的に設定された変数のデプロイフラグ。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html):受信データをUTF-8に変換して、Analyticsでの保存とレポートを可能にします。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determine the conversion rate to apply to revenue.

* [s.cookieDomain: Determines which domain the  and  cookies are set.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html)`s_cc``s_sq`

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Specify cookies set by JavaScript (`s_sq`, `s_cc`, plug-ins) that are inherently first-party cookies, even with third-party `2o7.net` or `omtrdc.net` domains.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determine lifespan of a cookie as processed by both JavaScript and data collection servers.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.registerPostTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.trackDownLoadLinks: Track links to downloadable files on your site.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html)

* [s.trackExternalLinks: Determine whether any link clicked is an exit link.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html)

* [s.trackInlineStats: Determine whether ClickMap data is gathered.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html)

* [s.linkDownloadFileTypes: Include a comma-separated list of file extensions.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html)

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html):サイトの一部であるリンクを表すフィルターのコンマ区切りリストが含まれます。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html):クエリ文字列を離脱リンクおよびファイルのダウンロード数レポートに含めるかどうかを決定します。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html):カスタムリンク、離脱リンクおよびダウンロードリンクで送信される変数のコンマ区切りリストを含めます。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):離脱リンクの特定のサブセットに関するレポートを作成するために使用します。

* [s.usePlugins: Call the  function prior to each image request.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html)`s_doPlugins`

