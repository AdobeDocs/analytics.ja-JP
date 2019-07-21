---
description: ページがブラウザー内でアクティブタブになっていた秒数を記録し、その値を次のページビューに関する指標に渡します。
keywords: Analytics の導入
seo-description: ページがブラウザー内でアクティブタブになっていた秒数を記録し、その値を次のページビューに関する指標に渡します。
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: 開発者と導入
uuid: 3891e2aa- d5c1-4a2b-8522- eb2bae39ea2e
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPageVisibility

ページがブラウザー内でアクティブタブになっていた秒数を記録し、その値を次のページビューに関する指標に渡します。

>[!NOTE]
>
>これはベータ版のプラグインであり、追加のアップデートが提供される可能性があります。

This plug-in requires [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

このプラグインは、ページがブラウザー内にあった秒数の合計（アクティブとパッシブ両方の表示時間）も記録します。ページ表示イベントに関連付けられた前のページ名を追跡するには、getPreviousValue プラグインを使用する必要があります。これらの値を追跡すると、訪問者エンゲージメントについてより深く理解し、サイトでの訪問者の行動をより正確に追跡することができます。

ページ表示イベントに関連付けられた前のページ名を追跡するには、getPreviousValue プラグインを使用する必要があります。これらの値を追跡すると、訪問者エンゲージメントについてより深く理解し、サイトでの訪問者の行動をより正確に追跡することができます。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、Analytics の使用と導入の経験がある開発者のみがおこなうようにしてください。This plug-in is compatible only with [!DNL AppMeasurement] tracking libraries.

## 必要なサポートプラグイン {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## プラグインコードと導入 {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Config セクション**

`s.pvel` 変数には、使用する次の 3 つのイベントを含める必要があります。

| イベント | 定義 |
|---|---|
| ページ表示秒数合計（数値） | ページがブラウザー内でアクティブだった時間 |
| ページ秒数合計（数値） | 表示状態にかかわらず、ページがブラウザーに読み込まれていた時間 |
| ページ表示インスタンス数合計（カウンター） | 上述の 2 つのイベントについて値が記録された合計回数 |

**サンプル呼び出し**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**doPlugins セクション**

このプラグインを初期化するには、s_code の `doPlugins` セクション内の、できれば `s.pageName` 変数を指定したあとに、2 行のコードを記述します。

**サンプル呼び出し**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Plug-ins セクション**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## メモ {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* 必ず、プラグインでデータの収集が希望どおりに実行されることをテストし確認してから、実稼動環境に実装してください。
* このプラグインは、前のページに関連付けられているページ表示秒数と合計秒数を渡すものなので、訪問の最終ページビューに関するデータは収集されません。
* このプラグインは、ユーザーの Web ブラウザーに cookie を設定できることを前提にしています。ユーザーがファーストパーティ cookie を許可していない場合、プラグインは Analytics にデータを渡しません。
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`.

* ブラウザーの制限により、ごくわずかな割合のユーザーで、ページビューデータの受け渡しがおこなわれない場合があります。また、結果的にデータがゆがめられないようにするロジックがプラグインに含まれています。なお、このプラグインは IE、Firefox、Chrome および Safari で動作することが確認されています。
* プラグインが合計秒数を測定し、その値を前のページ名に関連付ける方法によって、ページ指標と合計秒数指標に対して費やされるデフォルトの時間が異なります。
* [!UICONTROL 以下の指標に関連付けられた訪問者行動を要約し、把握するために、計算指標] を作成できます。

   * **ページ表示比率**（ページ表示秒数合計/ページ秒数合計）
   * **非表示の秒数**の合計**（ページ秒数合計-ページ表示秒数合計）
   * **平均ページ表示秒数**（ページ表示秒数合計/ページ表示インスタンス数合計）
   * **平均ページ非表示秒数**（（ページ秒数合計 - ページ表示秒数合計）/ページ表示インスタンス数合計）

* プラグインが秒数を丸める方法によって、ページ表示秒数合計と秒数合計に 1 ～ 2 秒の違いが生じ、合計秒数の方が大きくなることがあります（今後のアップデートで解決されます）。
* getVisitStart プラグインの使用は、30 分以上操作を実行せず、そのあとに新しい訪問を開始する訪問者を考慮する必要があります。このプラグインは設計どおりに機能していませんが、今後のバージョンで「アクティブ秒数合計」が組み込まれると、回避できるようになる可能性があります。

## よくある質問 {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**このプラグインは追加のサーバーコールを行いますか。**

このプラグインは、後続のページビューサーバー呼び出しに対するページ表示値を記録するだけです。その際に追加のサーバー呼び出しは使用しません。

**合計ページ秒数または合計ページ表示インスタンス数を取り込みたくない場合は、イベントリストからそれらを除外できますか。**

はい。ページ秒数合計と表示インスタンス数合計はオプションのイベントなので、必要に応じてリストから除外することができます。

**キャプチャしたイベントは、前のページ名以外のレポートで使用すると意味がありますか。**

このプラグインは後続のイメージリクエストに対する値を記録するので、「前のページ」のコンテキスト（「前のページの URL」など）で取り込まれた他の eVar のみを適用できます。

**このプラグインは、s.tl() 呼び出しに対する表示時間を送信しますか、それとも s.t() 呼び出しに対する表示時間だけを送信しますか。**

表示時間は s.t() 呼び出しに関してのみ記録されます。
