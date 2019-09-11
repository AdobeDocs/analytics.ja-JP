---
title: Analyticsの場合はpID
seo-title: Analyticsの場合はpID
description: Adobe Analytics用のプログレッシブWebアプリケーション
seo-description: AnalyticsでのpIDの使用
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# Analyticsの場合はpID

このガイドでは、Adobe AnalyticsをプログレッシブWebアプリケーション（pID）と共に使用する方法について説明します。

## はじめに

PIDは、Webサイトのネイティブアプリケーションエクスペリエンスおよびオフライン機能を提供できます。通常、pIDにはサービスワーカー、キャッシュの条件、マニフェストファイルが含まれています。これらのファイルはすべて読み込み時間、容易なナビゲーションおよびレスポンシブ動作に役立ちます。

Adobe Analyticsは従来のWebサイトと同様に、pIDと共にシームレスに機能します。pIDには、プログレッシブに行動するための要件がいくつかありますが、Analyticsが従来のWebサイトとは異なる方法でデータを収集またはレポートする方法について、障害や制限は作成されません。実際、Analyticsにはオフライン追跡機能が既に含まれているので、PIDは従来のWebサイトよりも簡単にこの組み込み機能を活用するのに役立ちます。

## PWA Analyticsデータの取得

PWAデータをAnalyticsで収集および分析するには、設定変更を行う必要はありません。Analyticsは、従来のWebサイトと同じ機能と機能をすべて自動的に提供します。

## オフライントラッキングを追加してPWAの効果を高める

Analytics [のオフライン追跡機能を](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 使用して、PWAの有効性を向上できます。デフォルトでは、この機能はオフになっていますが、AppMeasurement. jsファイルに次のプロパティを追加して、有効にすることができます。 `s.trackOffline=true;`を参照してください。

例えば、次のAppMeasurement. jsファイルでは、プロパティが最後に追加 `CONFIG SECTION`されます。

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


AppMeasurement. jsファイルの編集について詳しくは、AppMeasurement. jsファイルへのコード [の挿入を](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)参照してください。

AppMeasurement. jsファイルの設定の例については、AppMeasurement. jsファイル [の設定](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)を参照してください。

AppMeasurement. jsファイルの特性について詳しくは [、JavaScriptの実装の概要](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)を参照してください。
