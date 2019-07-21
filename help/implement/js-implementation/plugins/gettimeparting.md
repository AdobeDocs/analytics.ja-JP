---
description: getTimeParting プラグインは、時間、曜日および週末と平日の値をカスタム変数に入力します。Analysis Workspace では、初期設定で時間分割のディメンションを利用できます。このプラグインは、他の Analytics ソリューション（Analysis Workspace 以外）で時間分割のディメンションが必要な場合に使用します。
keywords: Analytics の導入
seo-description: getTimeParting プラグインは、時間、曜日および週末と平日の値をカスタム変数に入力します。Analysis Workspace では、初期設定で時間分割のディメンションを利用できます。このプラグインは、他の Analytics ソリューション（Analysis Workspace 以外）で時間分割のディメンションが必要な場合に使用します。
seo-title: getTimeParting
solution: Analytics
subtopic: プラグイン
title: getTimeParting
topic: 開発者と導入
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getTimeParting

getTimeParting プラグインは、時間、曜日および週末と平日の値をカスタム変数に入力します。Analysis Workspace では、初期設定で時間分割のディメンションを利用できます。The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of [!UICONTROL Analysis Workspace].

このプラグインは、ユーザーの Web ブラウザーから日付および時間の情報を読み込みます。この情報から、時間帯と曜日の情報を取得します。その後、選択したタイムゾーンにこのデータを変換します。夏時間にも対応しています。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコード {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Config セクション**

次のコードを [!DNL s_code.js] ファイルにある [!UICONTROL CONFIG SECTION] という名称の領域に置き、下記の説明のとおりに更新をおこないます。

`s._tpDST` - DST値の配列。The array is structured in the following format: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27'}
```

北半球のクライアントに対する注意：この配列内の DST 値は DST 開始日と DST 終了日です。

南半球のクライアントに対する注意：この配列内の DST 値は DST 終了日と DST 開始日です。

**パラメーター**

```js
var tp = s.getTimeParting(h,z);
```

* h =（必須）半球 - 時間を北半球または南半球のどちらに変換するかを指定します。この値は 'n' または 's' です。これは、渡された DST 配列の使用方法の決定に使用されます。'n' が渡されると、プラグインは DST がオンの場合に日付を使用します。's' が渡されると、プラグインは DST がオフの場合に日付を使用します。
* z =（オプション）タイムゾーン - データを特定の期間に基づかせたい場合は、ここに GMT とは別のタイムゾーンを指定する必要があります。これは DST 期間を除く GMT でなければなりません。値が指定されていない場合は GMT がデフォルトで使用されます（つまり、米国東部時間は '-5'）。

**戻り値**

次のように、時刻（分まで）と曜日を連結した値を返します。

```
8:03 AM|Monday
```

次に、[分類](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)を使用して訪問を期間にグループ化します。例えば、分類ルールビルダーでルールを設定し、9:00 AM ～ 9:59 AM の間の訪問を "9:00 AM - 10:00 AM" にグループ化できます。また、分類の代替策として、JavaScript でクライアント側のロジックを追加して訪問をグループ化することもできます。

**呼び出し例**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**PLUGINS SECTION**

次のコードを [!UICONTROL  ファイルの ]PLUGINS SECTION[!DNL s_code.js] に追加します。

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**メモ**

* 必ず、プラグインでデータの収集が希望どおりに実行されることをテストし確認してから、実稼動環境に実装してください。
* プラグインが正しく機能するには、設定変数を設定する必要があります。

