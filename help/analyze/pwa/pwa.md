---
title: Analytics 用 PWA
description: Adobe Analytics 用プログレッシブウェブアプリ
role: Business Practitioner, Administrator
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 82%

---

# Adobe Analytics の PWA

このページでは、Adobe Analytics をプログレッシブウェブアプリ（PWA）と共に使用する方法について説明します。

## はじめに

PWA は、Web サイトにネイティブアプリケーションエクスペリエンスやオフライン機能を提供できます。通常、PWA には、service worker、キャッシングプロビジョニング、およびマニフェストファイルが含まれます。これらはすべて、読み込み時間の短縮、ナビゲーションの簡素化、レスポンシブな動作に役立ちます。

Adobe Analyticsは、従来のWebサイトと同様にPWAとシームレスに連携します。 PWA には、それ自体で漸進的に動作するための追加要件がいくつかありますが、Analytics がデータを収集してレポートする方法に対して科す障壁や制限は、従来の Web サイトと同じものです。実際、Analytics には既にオフライントラッキング機能が含まれているため、PWA を使用すると、この組み込み機能を従来の Web サイトよりも簡単に活用できます。

## PWA Analytics データの取得

[!UICONTROL Analytics] を使用して PWA データを収集および分析するために構成を変更する必要はありません。[!UICONTROL Analytics] は、従来の Web サイトに対してと同じ機能や特徴をすべて自動的に提供します。

## オフライントラッキングの追加による PWA 有効性の向上

Adobe Analytics の[オフライントラッキング機能](/help/implement/vars/config-vars/trackoffline.md)を使用して、PWA の効果を高めることができます。デフォルトでは、この機能はオフになっていますが、AppMeasurement.js ファイルにプロパティ「`s.trackOffline=true;`」を追加してオンにすることができます。 

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

AppMeasurement.jsファイルの設定について詳しくは、[設定変数の概要](/help/implement/vars/config-vars/configuration-variables.md)と、同じサブチャプター内の個々の変数固有のページを参照してください。

AppMeasurement.jsファイルの特性について詳しくは、[JavaScript実装の概要](/help/implement/js/overview.md)を参照してください。
