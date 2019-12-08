---
description: 設定変数は、AppMeasurement.js に設定されます。
keywords: Analytics Implementation
subtopic: Variables
title: 設定変数
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。最も一般的な設定変数は、通常、メインのグローバルJavaScript appMeasurement.jsに設定されます。 これらの変数は、必要に応じて、Analytics のページレベルのコード内およびリンクに設定できます。

**[!UICONTROL 管理ツール]**／**[!UICONTROL コードマネージャー]**&#x200B;でコードを生成する場合、これらのすべての変数がデフォルトでコードに現れるわけではありません。これらの設定変数の一部は、サイトの導入ニーズに適用できない場合があります。

これらの設定変数を使用するうえでの目標の一部を次に示します。

* 複数のサイト/ドメインの追跡
* 購入時に任意の通貨を使用
* データに関係のない言語の取得
* リンクトラッキング（ダウンロードされたファイルの数、外部サイトへのリンク）
* 独自の目的でのカスタムリンクの追跡

> [!NOTE][!DNL AppMeasurement] では、トラック関数 `t()` に最初の呼び出しをおこなう前に、すべての設定変数を設定する必要があります。`t()` への呼び出しの後に設定変数が設定されている場合、予期しない結果が発生する可能性があります。適切なデータ収集を確実におこなうには、すべての設定変数が.`doPlugins` 関数以上に設定されている必要があります。

特定の設定変数に関するヘルプが必要な場合は、次のリンクをクリックしてください。

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):データの保存とレポートを行うレポートスイートを指定します。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html):各ページのURLに基づいてレポートスイートを動的に選択します。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html):送信先レポートスイートの決定に使用するルールを指定します。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html):DOMオブジェクトを使用して、すべてのルールが適用されるURLのセクションを取得します。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html):動的に設定された変数のデプロイフラグ。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html):受信データをUTF-8に変換して、Analyticsでの保存とレポートを可能にします。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html):売上高に適用するコンバージョン率を決定します。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html):CookieとCookieを設定するド `s_cc` メイン `s_sq` を決定します。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html):ページURLのドメイン `s_cc` 内のピ `s_sq` リオド数を指定して、のドメインとcookieを決定します。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html):JavaScript（、プラグイン）によって設定さ`s_sq`れた、本質的にファ `s_cc`ーストパーティのCookie（サードパーティまたはドメインを含む）を `2o7.net` 指定 `omtrdc.net` します。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html):JavaScriptとデータ収集サーバーの両方で処理されるcookieの有効期限を決定します。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html):JavaScriptファイル内の適切な場所で関数を参照し、呼び出すことを許可します。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html):コールバック（関数）とその関数のパラメーターの両方をパラメーターとして取る関数。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html):サイト上のダウンロード可能ファイルへのリンクを追跡します。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html):クリックされたリンクが離脱リンクであるかどうかを判定します。

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html):ClickMapデータを収集するかどうかを決定します。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html):ファイル拡張子のコンマ区切りリストを含めます。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html):サイトの一部であるリンクを表すフィルターのコンマ区切りリストが含まれます。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html):クエリ文字列を離脱リンクおよびファイルのダウンロード数レポートに含めるかどうかを決定します。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html):カスタムリンク、離脱リンクおよびダウンロードリンクで送信される変数のコンマ区切りリストを含めます。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):離脱リンクの特定のサブセットに関するレポートを作成するために使用します。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html):各イメージリクエ `s_doPlugins` ストの前に関数を呼び出します。

* [s.useForcedlinkTracking](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-usedforcedlinktracking.html):一部のブラウザーの強制リンクトラッキングを無効にします。

* [s.linkType](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktype.html):ダウンロード、終了またはカスタムのリンクタイプを設定します。

* [s.linkName](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html):ダウンロード、離脱またはカスタムリンクのレポートに表示する名前を設定します。

* [s.ForcedlinkTrackingTimeout](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-forcedlinktrackingtimeout.html):トラッキングの最大待機時間を設定します。

* [s.linkTrackEvents](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackingevents.html):一部のブラウザーの強制リンクトラッキングを無効にします。

* [s.linkUrl](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html):リンクのURLを設定します。

* [s.linkObject](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkobject.html):クリックされたオブジェクトを参照します。
