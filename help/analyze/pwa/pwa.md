---
title: Analytics 用 PWA
description: Adobe Analytics 用プログレッシブウェブアプリ
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 75%

---


# Adobe AnalyticsのPWA

このページでは、Adobe AnalyticsをプログレッシブWeb Apps(PWA)と共に使用する方法について説明します。

## はじめに

PWA は、Web サイトにネイティブアプリケーションエクスペリエンスやオフライン機能を提供できます。通常、PWA には、service worker、キャッシングプロビジョニング、およびマニフェストファイルが含まれます。これらはすべて、読み込み時間の短縮、ナビゲーションの簡素化、レスポンシブな動作に役立ちます。

Adobe Analytics は、従来の Web サイトと同様、PWA とシームレスに連携します。PWA には、それ自体で漸進的に動作するための追加要件がいくつかありますが、Analytics がデータを収集してレポートする方法に対して科す障壁や制限は、従来の Web サイトと同じものです。実際、Analyticsには既にオフライン追跡機能が含まれているので、PWAを使用すると、従来のWebサイトよりも簡単にこの組み込み機能を利用できます。

## PWA分析データの取得

[!UICONTROL AnalyticsでPWAデータを収集して分析するには]、設定を変更する必要はありません。 [!UICONTROL Analytics は、従来の Web サイトに対してと同じ機能や特徴をすべて自動的に提供します。]

## オフライントラッキングの追加による PWA 有効性の向上

You can increase the effectiveness of your PWA by using Adobe Analytics [offline tracking capabilities](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/functions/forceoffline.translate.html) with it. デフォルトでは、この機能はオフになっていますが、AppMeasurement.js ファイルにプロパティ「`s.trackOffline=true;`」を追加してオンにすることができます。 

例えば、次の AppMeasurement.js ファイルでは、プロパティが `CONFIG SECTION` の最後に追加されています。

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

AppMeasurement.js ファイルの編集について詳しくは、「[AppMeasurement.js ファイルへのコードの挿入](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html)」を参照してください。

AppMeasurement.js ファイルの構成例については、「[AppMeasurement.js ファイルの構成](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/js/overview.translate.html#section_042412C29CC249E298F19B2BC2F43CE7)」を参照してください。

AppMeasurement.js ファイルの特性について詳しくは、「[Javascript 実装の概要](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/js/migrate-from-hcode.translate.html)」を参照してください。
