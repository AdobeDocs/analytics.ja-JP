---
description: ユーザーが最後にサイトを訪問してからの日数を判断し、その情報を Analytics 変数に取り込みます。
keywords: Analytics の導入
seo-description: ユーザーが最後にサイトを訪問してからの日数を判断し、その情報を Analytics 変数に取り込みます。
seo-title: getDaysSinceLastVisit
solution: Analytics
subtopic: プラグイン
title: getDaysSinceLastVisit
topic: 開発者と導入
uuid: cad95882-3bd0-4f94- a0c3-4e7b6058d246
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getDaysSinceLastVisit

ユーザーが最後にサイトを訪問してからの日数を判断し、その情報を Analytics 変数に取り込みます。

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) には、最後の訪問 **** ディメンションからの日数が含まれるようになり、このプラグインの必要がなくなりました。

この再訪問頻度データによって次の質問に答えることができます。

* ユーザーはどのぐらいの頻度で自分のサイトを訪問しているか。
* 再訪問頻度はコンバージョンとどう関連しているか。リピート購入者は頻繁に訪問するかどうか。
* キャンペーンでクリックスルーしたユーザーは頻繁に訪問するか。

また、プラグインから、セグメント化に使用する値を生成できます。例えば、先回訪問してから 30 日以上経過しているユーザーの訪問のみのデータをすべて表示するセグメントを作成できます。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_5600DBB819F143D59527A73BD94418DE}

**CONFIG SECTION**

変更は必要ありません。

**Plugin Config**

Place the following code within the `s_doPlugins()` function, which is located in the area of the [!DNL s_code.js] file labeled *Plugin Config*. 再訪問頻度データを取り込むために、1 つのカスタムトラフィック（s.prop）変数および 1 つのカスタムコンバージョン（s.eVar）変数、またはそのいずれかを選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次の例はあくまでもサンプルとして提供されており、お客様の必要に応じて適切に更新する必要があります。

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**PLUGINS SECTION**[!DNL s_code.js] ファイルにある *PLUGINS SECTION* という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**メモ**

* 必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
* プラグインは、ユーザーを再訪問頻度に基づいて次のグループに分類します。

   * 初回の訪問
   * 1 日未満
   * 7 日未満
   * 7 日を超える
   * 30 日を超える

* このプラグインは cookie を使って、ユーザーが以前に訪問したことがあるかどうかをフラグします。ブラウザーが cookie を受け付けない場合は、「*Cookies 未サポート*」という値を返します。

