---
description: JavaScriptプラグインデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAdobe Analyticsコードに追加します。
seo-description: JavaScriptプラグインデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAdobe Analyticsコードに追加します。
seo-title: Adobe Analyticsプラグインコード
title: Adobe Analyticsプラグインコード
uuid: e99999be-1800-4d63- a4cb- df68a1b53d0d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe Analytics Plug-In Code{#adobe-analytics-plug-in-code}

JavaScriptプラグインデータ収集方法を選択した場合は、次のコード行をコピーして、ページ上のAdobe Analyticsコードに追加します。

```
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/* 
 * in the s_doPlugins function 
 */ 
s.eVar8=s.getQueryParam("MID"); // Message ID as assigned by broadmail 
s.eVar9=s.getQueryParam("RID"); // Recipient ID as assigned by broadmail 
 
I am not sure, if that is useful and/or necessary, but I though the  
client may specify the Post Click values in the s_doPlugins function as  
well. Maybe it were useful to add some example definitions like the  
following to indicate the use of these variables. 
 
/* 
 * Optional custom settings of the Post Click data that is transferred to optivo broadmail. 
 * Also to be defined in the s_doPlugins function. 
 */ 
s.eVar10="May 10, 2012"; // the date the Post Click occurred 
s.eVar11="Post Click Product ID"; // e.g. "shoes" 
s.eVar12="Post Click Type of Action"; // e.g. "purchase"; 
```

>[!NOTE]
>
>上記のプラグインは、特定のカスタムコマース変数（eVar）を使用できることを前提としています。上記のプラグインで指定した変数がAdobe Analyticsのデプロイメント内で使用できない場合は、使用可能なものに置き換えてください。

