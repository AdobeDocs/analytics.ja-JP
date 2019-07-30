---
description: s.hitGovernor プラグインは、事前定義された期間内に送信された Analytics のイメージリクエストの総数を追跡し、その総数が一定のしきい値を超えた場合に、必要に応じて追加のロジックを実行できます。
seo-description: s.hitGovernor プラグインは、事前定義された期間内に送信された Analytics のイメージリクエストの総数を追跡し、その総数が一定のしきい値を超えた場合に、必要に応じて追加のロジックを実行できます。
seo-title: hitGovernor
title: hitGovernor
uuid: d9091ae-005a-43c2- b419-980b795bc2a9
translation-type: tm+mt
source-git-commit: 5abac13c231659108a26b8513a3bb32e4e530b94

---


# hitGovernor

s.hitGovernor プラグインは、事前定義された期間内に送信された Analytics のイメージリクエストの総数を追跡し、その総数が一定のしきい値を超えた場合に、必要に応じて追加のロジックを実行できます。

## hitGovernor {#topic_56B636A42A624B38A0A446C607ACD700}

s.hitGovernor プラグインは、事前定義された期間内に送信された Analytics のイメージリクエストの総数を追跡し、その総数が一定のしきい値を超えた場合に、必要に応じて追加のロジックを実行できます。

ボット、スパイダー、特定のユーザーエージェントまたは特定の IP アドレスのリストからのトラフィックは、ボットトラフィックとして識別したり、レポートから除外したりできますが、レポートスイートに、本来ならカウントされるべきではないトラフィックのデータが含まれることもあります。例えば、不自然な間隔（約 1 秒ごとにリクエストが 1 回など）でクリックやページビューが大量に発生している場合は、不正なトラフィックの可能性があります。

このプラグインを利用すると、該当の訪問者の以降のトラフィックを自動的にブロックできます。そうしたトラフィックをレポート内で動的に識別することもできます。

## hitGovernor プラグインの仕組み {#section_541BC639E31442D09B1C85A2FFCDC02C}

このプラグインは、イメージリクエストがトラッキングサーバーに送信されるたびに Cookie の値を増分し、一定の期間にわたってそれを追跡します。デフォルトの期間は 1 分ですが、変更できます（以下の[導入](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2)を参照）。If the total number of hits during that time frame exceeds the default hit threshold (60), a final custom link image request is sent to set the *`exceptionFlag`* context data variable. デフォルトのヒット数のしきい値も変更できます。

必要に応じて、その時点からデフォルトの 60 日間が経過するまでは、該当の訪問者のトラフィックデータの収集をブロックできます。トラフィックをブロックするためには、以下に示すように、doPlugins 関数にコードを追加する必要があります。期間も変更できます。The logic allows time to either include that visitor's IP address, User Agent, or [!DNL Experience Cloud] Visitor ID in the proper permanent exception logic, or to reset the timeout period after the sixty days have elapsed. 60 日後にプラグインによってこのトラフィックが不正と見なされた場合は、再度例外としてマークされ、さらに 60 日間データの収集がブロックされます。

## レポート {#section_E742F19B528041808454744DB2C7007C}

設定する必要があるデフォルトの変数およびイベントはありませんが、処理ルールのロジックをセットアップし、適切な変数やイベントを設定することを強くお勧めします。そうしたカスタムの変数やイベントの例は次のとおりです。

* [!DNL Experience Cloud] 訪問者 ID
* IP アドレス
* ユーザーエージェント
* マークされた例外イベント

これらの変数のセグメントを作成すると、セグメントと仮想レポートスイートを作成し、これらの不明瞭なヒットのサイトへの全体的な影響を確認できます。

レポートで収集された値を参考に、ボットのルール、DB VISTA ルールまたは会社の IP 除外設定を更新することをお勧めします。

## 実装 {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

hitGovernor プラグインを導入する手順は次のとおりです。

1. AppMeasurement ライブラリに変更を加えます。

   このプラグインを初期化するためには、以下のコード行（太字）を AppMeasurement ライブラリコードの `registerPostTrackCallback` 関数内に追加します。

   >[!NOTE]
   >
   >Although the `registerPostTrackCallback` functionality is included in AppMeasurement libraries 1.8.0+, it is not included in any custom code configuration by default. doPlugins 関数の後および&#x200B;*外*&#x200B;に追加します。

   ```
    s.registerPostTrackCallback(function(){ 
    s.governor();
   }); 
   ```

   AppMeasurement ファイルの doPlugins セクションの下に、以下の[プラグインのソースコード](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0)に含まれているプラグインコードを追加します。

   ヒット数上限のしきい値、ヒット時間のしきい値およびトラフィック除外期間は、プラグイン自体の外で以下の変数を設定することで変更できます。他の設定変数と一緒に設定することをお勧めします。

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 構文 </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ヒット数上限のしきい値 </p> </td> 
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>特定の期間におけるヒット数の上限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ヒット時間のしきい値 </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>ヒット数を記録する秒数。この数値を 6 で割ることで期間が決定されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>除外のしきい値 </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>該当の訪問者に対して除外 Cookie を設定する日数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>実装では、デフォルトの解析の"s"オブジェクトとは異なるオブジェクト名を使用することがあります。その場合は適切なオブジェクト名に変更してください。

1. 処理ルールを設定します。

   このプラグインは、リンクトラッキングイメージリクエストで、マークされた除外をコンテキストデータとして記録します。そのため、処理ルールを設定し、マークされた該当の除外を以下のような適切な変数に割り当て、追跡する必要があります。

   ![](assets/hitgov-config.png)

1. （オプション）トラフィックのブロックコードを doPlugins に追加します。

   トラフィックを例外として識別した後は、以下のコードを `doPlugins` 関数内に追加することで、該当の訪問者の以降のヒットをすべてブロックできます。

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   このコードを追加しないと、該当の訪問者のトラフィックは例外としてマークされるだけでブロックされません。

## プラグインのソースコード {#reference_76423C81A7A342B2AC4BE41490B27DE0}

このコードは、AppMeasurement ライブラリの doPlugins セクションの下に追加する必要があります。

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 
```

