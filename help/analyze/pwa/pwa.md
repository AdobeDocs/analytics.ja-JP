---
title: Analytics用のPWA
seo-title: Analytics用のPWA
description: Adobe Analytics用プログレッシブWebアプリ
seo-description: AnalyticsでのPWAの使用
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Analytics用のPWA

このガイドでは、Adobe AnalyticsをプログレッシブWebアプリ(PWA)と共に使用する方法について説明します。

## はじめに

PWAは、Webサイトに対してネイティブのアプリエクスペリエンスとオフライン機能を提供できます。 通常、PWAにはサービスワーカー、キャッシュのプロビジョニング、マニフェストファイルが含まれ、これらのファイルは、読み込み時間の短縮、ナビゲーションの容易化、レスポンシブな動作に役立ちます。

Adobe Analyticsは、従来のWebサイトと同様に、PWAとシームレスに連携します。 PWAには、プログレッシブに動作するための要件がいくつかありますが、従来のWebサイトとは異なる方法でAnalyticsがデータを収集したりレポートする方法に関する障害や制限は生じません。 実際、Analyticsには既にオフライン追跡機能が含まれているので、PWAは、従来のWebサイトよりも簡単にこの組み込み機能を利用できます。

## PWA解析データの取得

AnalyticsでPWAデータを収集して分析する場合は、設定を変更する必要はありません。 Analyticsは、従来のWebサイトと同じ機能と機能をすべて自動的に提供します。

## PWAの効果を高めるためのオフライン追跡の追加

Analyticsのオフライン追跡機能を使用して、PWAの効果を高め [ることができます](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 。 デフォルトでは、この機能はオフになっていますが、AppMeasurement.jsファイルに次のプロパティを追加してオンにすることができます。 `s.trackOffline=true;`.

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


AppMeasurement.jsファイルの編集について詳しくは、「AppMeasurement.jsファ [イルへのコードの挿入」を参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

AppMeasurement.jsファイルの設定例については、AppMeasurement.jsファ [イルの設定を参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

AppMeasurement.jsファイルの特性について詳しくは、 [Javascript実装の概要を参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。
