---
title: AnalyticsのPWA
description: Adobe Analytics用のプログレッシブWebアプリ
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# AnalyticsのPWA

このページでは、Adobe AnalyticsをプログレッシブWebアプリ(PWA)と共に使用する方法について説明します。

## はじめに

PWAは、Webサイトに対してネイティブのアプリエクスペリエンスとオフライン機能を提供できます。 通常、PWAにはサービスワーカー、キャッシュのプロビジョニング、マニフェストファイルが含まれ、これらのファイルはすべて読み込み時間の短縮、ナビゲーションの容易化、レスポンシブな動作に役立ちます。

Adobe Analyticsは、従来のWebサイトと同様にPWAとシームレスに連携します。 PWAには、プログレッシブに動作するための要件がいくつかありますが、従来のWebサイトとは異なる方法でAnalyticsがデータを収集し、レポートする方法に関する障害や制限は生じません。 実際、Analyticsには既にオフライン追跡機能が含まれているので、PWAは、従来のWebサイトよりも簡単にこの組み込み機能を利用できます。

## PWA解析データの取得

AnalyticsでPWAデータを収集して分析する場合は、設定を変更する必要はありません。 Analyticsは、従来のWebサイトと同じ機能と機能をすべて自動的に提供します。

## PWAの効果を高めるためのオフライン追跡の追加

Analyticsのオフライン追跡機能を使用すると、PWAの効果 [を高めることが](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) できます。 デフォルトでは、この機能はオフになっていますが、次のプロパティをAppMeasurement.jsファイルに追加してオンにすることができます。 `s.trackOffline=true;`.

例えば、次のAppMeasurement.jsファイルでは、プロパティが `CONFIG SECTION`

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
*** 
```

AppMeasurement.js ファイルの編集について詳しくは、「[AppMeasurement.js ファイルへのコードの挿入](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)」を参照してください。

AppMeasurement.jsファイルの設定例については、AppMeasurement.jsファ [イルの設定を参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

AppMeasurement.jsファイルの特性について詳しくは、 [Javascript実装の概要を参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。
