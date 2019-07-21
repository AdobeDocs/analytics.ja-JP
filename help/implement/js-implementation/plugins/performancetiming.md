---
description: このプラグインは、Web のパフォーマンスを正確に測定するための Navigation Timing JavaScript API を使用することで動作します。これは、ページ読み込みイベントおよびアセット読み込み時間に関する正確で詳細なタイミング統計を取得するネイティブメソッドを提供します。以前は、この種の測定は、タイミング指標の JavaScript Date オブジェクト、または Navigation Timing 指標の基本的な推定を使用していました。どちらの方法も、ページ読み込み時間に関するあるトレンドを提供しますが、信頼性に欠けます。
keywords: Analytics の導入
seo-description: このプラグインは、Web のパフォーマンスを正確に測定するための Navigation Timing JavaScript API を使用することで動作します。これは、ページ読み込みイベントおよびアセット読み込み時間に関する正確で詳細なタイミング統計を取得するネイティブメソッドを提供します。以前は、この種の測定は、タイミング指標の JavaScript Date オブジェクト、または Navigation Timing 指標の基本的な推定を使用していました。どちらの方法も、ページ読み込み時間に関するあるトレンドを提供しますが、信頼性に欠けます。
seo-title: performanceTiming
solution: Analytics
title: performanceTiming
topic: 開発者と導入
uuid: ab2a6c51-8791-41e7-9bea- c1ce8d312de8
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# performanceTiming

このプラグインは、Web のパフォーマンスを正確に測定するための Navigation Timing JavaScript API を使用することで動作します。これは、ページ読み込みイベントおよびアセット読み込み時間に関する正確で詳細なタイミング統計を取得するネイティブメソッドを提供します。以前は、この種の測定は、タイミング指標の JavaScript Date オブジェクト、または Navigation Timing 指標の基本的な推定を使用していました。どちらの方法も、ページ読み込み時間に関するあるトレンドを提供しますが、信頼性に欠けます。

## このプラグインの機能 {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>これはベータ版のプラグインであり、追加のアップデートが提供される可能性があります。

このプラグインは、次の詳細なイベントを使用して、ページ読み込みの個別のタイミングコンポーネントをトラッキングします。

| イベント | 名前 | 計算元 |
|---|---|---|
| 1 | リダイレクトのタイミング | fetchStart - navigationStart |
| 2 | アプリキャッシュのタイミング | domainLookupStart - fetchStart |
| 3 | DNS のタイミング | domainLookupEnd - domainLookupStart |
| 4 | TCP のタイミング | connectEnd - connectStart |
| 5 | リクエストのタイミング | responseStart - connectEnd |
| 6 | 応答のタイミング | responseEnd - responseStart |
| 7 | 処理のタイミング | loadEventStart - domLoading |
| 8 | onLoad のタイミング | loadEventEnd - loadEventStart |
| 9 | 合計ページ読み込み時間 | loadEventEnd - navigationStart |
| 10 | パフォーマンスインスタンス | カウンター |

次の図で、PerformanceTiming インターフェイスおよび PerformanceNavigation インターフェイスで定義されるタイミング属性を、それぞれリダイレクトがある場合とない場合について説明します。

![](assets/timing-attributes.png)

Navigation Timing オブジェクトの詳細については、次を参照してください。

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

さらに、このプラグインは、オプションで performanceEntries オブジェクトを使用して、特定のページに読み込まれた個別のアセットごとに、アセット名、アセット読み込み開始時間、アセット読み込み時間の詳細を記録できます。大量の情報がプラグインと共に記録されるので、ページビュー間のページ読み込み情報を格納するために、DOM ストレージオブジェクトが有効になっている必要があります。この機能を有効にする前に、会社のプライバシーポリシーが DOM ストレージオブジェクトの使用を許可していることを確認してください。また、すべてのアセットをトラッキングするために、listVar を使用する必要があります。

## 必要なサポートプラグイン {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList
* getPreviousValue

## プラグインコードと導入 {#section_564D77E1CF0E445586D95AD9769CE57D}

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、Adobe Analytics の使用と導入の経験がある開発者のみがおこなうようにしてください。This plugin is compatible only with [!DNL AppMeasurement] tracking libraries.

**Config セクション（doPlugins の前）：**

`s.pte`：使用したい 10 のイベントを特定の順番で含むイベントのコンマ区切りのリスト（個別のタイミングイベントコンポーネント（events 1 ～ 8）、合計ページ読み込み時間（event 9）および合計パフォーマンスインスタンス（event 10））。

`s.ptc`：doPlugins 内でプラグインを実行するかどうかを設定します。常に false に設定します。

*サンプル呼び出し*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 
```

**doPlugins セクション：**

このプラグインを初期化するには、s_code の `doPlugins` セクション内の、できれば `s.pageName` 変数を指定したあとに、1 行のコードを記述します。プラグイン内でアセット読み込み時間機能を使用したい場合、使用するリスト変数の名前を渡す必要があります。そうしないと、パフォーマンスタイミングエントリのみが、以前 `s.pte` 変数で指定したイベントでトラッキングされます。

>[!NOTE]
>
>In order to correlate performance timing entries with pages on your site, you must also initialize the `getPreviousValue` plug-in. これらのパフォーマンスエントリをすべての以前のページ名または以前のページ URL 値と比較することをお勧めします。

*サンプル呼び出し*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  
```

**Plugins セクション：**

最後に、プラグイン自体を JavaScript 実装に追加します。

```
/* Plugin: Performance Timing Tracking - 0.11 BETA */ 
s.performanceTiming=new Function("v","" 
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf" 
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo" 
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead(" 
+");}else{s.rfe();s[s.ptv]='';}}"); 
s.performanceWrite=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{" 
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc" 
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo" 
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook" 
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect" 
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart," 
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo" 
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad" 
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart" 
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);" 
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt" 
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v" 
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')" 
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe[" 
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000" 
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec" 
+"',tempPe);}}catch(err){return;}}}catch(err){return;}"); 
s.performanceCheck=new Function("a","b","" 
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix" 
+"ed(2);}else{return 600;}}"); 
s.performanceRead=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='" 
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt" 
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even" 
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl" 
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora" 
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt" 
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s" 
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;"); 
/* Remove from Events 0.1 - Performance Specific,  
removes all performance events from s.events once being tracked. */ 
s.rfe=new Function("","" 
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');" 
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev" 
+"ents']=s.events;}}catch(e){return;}"); 
/* Plugin Utility - RFL (remove from list) 1.0*/ 
s.rfl=new Function("l","v","d1","d2","ku","" 
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:" 
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde" 
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i" 
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}" 
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i" 
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s." 
+"join(R,{delim:d2})"); 
```

## メモ {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* 必ず、プラグインでデータの収集が希望どおりに実行されることをテストし確認してから、実稼動環境に実装してください。
* このプラグインは、前のページに関連付けられているパフォーマンスデータを渡すものなので、訪問の最終ページビューに関するデータは収集されません。
* アセットタイミングをトラッキングしている場合、このプラグインは、ユーザーの Web ブラウザーに DOM ストレージ値を設定できることが前提になります。ユーザーが cookie を許可しておらず、DOM ストレージを有効にしていない場合、プラグインは Analytics にデータを渡しません。
* ブラウザーの制限により、ごくわずかな割合のユーザーがナビゲーションタイミングデータを渡さないことがあります。これにより、特にモバイルブラウザーのごく一部でデータが歪曲されないように、プラグインがプラグインに含まれています。なお、このプラグインは IE、Firefox、Chrome および Safari で動作することが確認されています。
* [!UICONTROL これらの指標に関連付けられた訪問者行動を要約し、把握するために、計算指標] を作成する必要があります。

   * リダイレクトのタイミングの平均（リダイレクトのタイミング/パフォーマンスタイミングインスタンス）
   * アプリキャッシュのタイミングの平均（アプリキャッシュのタイミング/パフォーマンスタイミングインスタンス）
   * DNS のタイミングの平均（DNS のタイミング/パフォーマンスタイミングインスタンス）
   * TCP のタイミングの平均（TCP のタイミング/パフォーマンスタイミングインスタンス）
   * リクエストのタイミングの平均（リクエストのタイミング/パフォーマンスタイミングインスタンス）
   * 応答のタイミングの平均（応答のタイミング/パフォーマンスタイミングインスタンス）
   * 処理のタイミングの平均（処理のタイミング/パフォーマンスタイミングインスタンス）
   * onLoad のタイミングの平均（onLoad のタイミング/パフォーマンスタイミングインスタンス）
   * ページ読み込みタイミングの平均（合計ページ読み込み時間/パフォーマンスタイミングインスタンス）

