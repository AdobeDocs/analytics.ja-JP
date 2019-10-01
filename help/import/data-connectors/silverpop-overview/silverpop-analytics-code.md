---
description: 'JavaScriptプラグインのデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAnalyticsコードに追加します '
seo-description: 'JavaScriptプラグインのデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAnalyticsコードに追加します '
seo-title: Analyticsプラグインコード
title: Analyticsプラグインコード
uuid: 534874bd-49d9-4b15-8019-b503dfcf3182
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analyticsプラグインコード{#analytics-plug-in-code}

JavaScriptプラグインのデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAnalyticsコードに追加します。

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>上記のプラグインは、特定のカスタムコマース変数(eVar)が使用可能であることを前提としています。 上記のプラグインで指定した変数がAnalyticsのデプロイメント内で使用できない場合は、それらの変数を使用可能な変数に置き換えます。