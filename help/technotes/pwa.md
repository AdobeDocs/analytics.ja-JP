---
title: Analytics 用 PWA
description: Adobe Analytics 用プログレッシブ Web アプリ
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
TQID: https://experienceleague.adobe.com/IKf2D1AqfbD6qurNczyJWaZIOzQyOTURfJFSJNDucnU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 100%

---

# Adobe Analytics の PWA

このページでは、Adobe Analytics をプログレッシブウェブアプリ（PWA）と共に使用する方法について説明します。

## はじめに

PWA は、Web サイトにネイティブアプリケーションエクスペリエンスやオフライン機能を提供できます。 通常、PWA には、service worker、キャッシングプロビジョニング、およびマニフェストファイルが含まれます。これらはすべて、読み込み時間の短縮、ナビゲーションの簡素化、レスポンシブな動作に役立ちます。

Adobe Analytics は、従来の Web サイトと同様、PWA とシームレスに連携します。 PWA には、それ自体で漸進的に動作するための追加要件がいくつかありますが、Analytics がデータを収集してレポートする方法に対して科す障壁や制限は、従来の Web サイトと同じものです。 実際、Analytics には既にオフライントラッキング機能が含まれているため、PWA を使用すると、このビルトインの機能を従来の web サイトよりも簡単に活用できます。

## PWA Analytics データの取得

[!UICONTROL Analytics] を使用して PWA データを収集および分析するために構成を変更する必要はありません。 [!UICONTROL Analytics] は、従来の Web サイトに対してと同じ機能や特徴をすべて自動的に提供します。

## オフライントラッキングの追加による PWA 有効性の向上

Adobe Analytics の[オフライントラッキング機能](/help/implement/vars/config-vars/trackoffline.md)を使用して、PWA の効果を高めることができます。 デフォルトでは、この機能はオフになっていますが、AppMeasurement.js ファイルにプロパティ「`s.trackOffline=true;`」を追加してオンにすることができます。

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

AppMeasurement.js ファイルの設定について詳しくは、「[設定変数の概要](/help/implement/vars/config-vars/configuration-variables.md)」と、同じサブチャプター内の個々の変数固有のページを参照してください。

AppMeasurement.js ファイルの特性について詳しくは、「[JavaScript 実装の概要](/help/implement/js/overview.md)」を参照してください。
