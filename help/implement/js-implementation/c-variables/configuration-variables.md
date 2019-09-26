---
description: AppMeasurement.jsに設定される設定変数。
keywords: Analytics の実装
seo-description: AppMeasurement.jsで設定されたAdobe Analytics用の設定変数
seo-title: 設定変数
solution: Analytics
subtopic: 変数
title: 設定変数
topic: 開発者と実装
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# Configuration variables overview

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
>[!DNL AppMeasurement] は、track関数の最初の呼び出しの前に、すべての設定変数が設定されている必要がありま `t()`す。 If configuration variables are set after the call to , unexpected results may occur. `t()`To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

For help with specific configuration variables, refer to the following links:

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):データの保存とレポートを行うレポートスイートを指定します。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):各ページのURLに基づいてレポートスイートを動的に選択します。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify the rules used for determining the destination report suite.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):DOMオブジェクトを使用して、すべてのルールが適用されるURLのセクションを取得します。

* [s.dynamicVariablePrefix: Deploy flagging for dynamically-populated variables.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):受信データをUTF-8に変換して、Analyticsでの保存とレポートを可能にします。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):売上高に適用するコンバージョン率を決定します。

* [s.cookieDomain: Determines which domain the  and  cookies are set.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine the domain for `s_cc` and `s_sq` cookies by specifying the number of periods in the domain of the page URL.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify cookies set by JavaScript (`s_sq`, `s_cc`, plug-ins) that are inherently first-party cookies, even with third-party `2o7.net` or `omtrdc.net` domains.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):JavaScriptとデータ収集サーバーの両方で処理されるcookieの有効期限を決定します。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):コールバック（関数）とその関数のパラメーターの両方をパラメーターとして取る関数。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):サイト上のダウンロード可能ファイルへのリンクを追跡します。

* [s.trackExternalLinks: Determine whether any link clicked is an exit link.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [strackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):ClickMapデータを収集するかどうかを決定します。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):ファイル拡張子のコンマ区切りリストを含めます。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):サイトの一部であるリンクを表すフィルターのコンマ区切りリストが含まれます。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):クエリ文字列を離脱リンクおよびファイルのダウンロード数レポートに含めるかどうかを決定します。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):カスタムリンク、離脱リンクおよびダウンロードリンクで送信される変数のコンマ区切りリストを含めます。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):離脱リンクの特定のサブセットに関するレポートを作成するために使用します。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):各イメージリクエ `s_doPlugins` ストの前に関数を呼び出します。

