---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# campaign

 変数は、訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別します。通常、 の値はクエリ文字列パラメーターから取得します。https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables/browserheight.html

<!-- 

campaign.xml

 -->

**パラメーター**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 バイト </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>コンバージョン／キャンペーン／トラッキングコード </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

マーケティングキャンペーンのすべてのリンクに、一意のトラッキングコードを関連付ける必要があります。例えば、有料検索エンジンキーワードのトラッキングコードが 112233 であるとします。このトラッキングコード 112233 のキーワードをクリックした人が、対応する Web サイトに導かれた場合、*`campaign`* 変数にこのトラッキングコードが記録されます。

*`campaign`* 変数の生成方法は主に 2 つあります。

* [!UICONTROL getQueryParam] プラグインを JavaScript ファイル内で使用して、URL からクエリ文字列パラメーターを取得します。[!UICONTROL getQueryParam] プラグインについて詳しくは、[実装プラグイン](/help/implement/js-implementation/plugins/impl-plugins.md)を参照してください。

* Web ページ上の HTML の *`campaign`* 変数に値を割り当てます。

どちらの方法で *`campaign`* 変数を生成する場合でも、「戻る」ボタンのトラフィックによって、キャンペーン要素からの実際のクリックスルー数が水増しされる場合があります。

例えば、ある訪問者が有料検索キーワードをクリックしてサイトに訪問したとします。この訪問者がランディングページに到達したとき、URL にはそのキーワードのトラッキングコードを識別するクエリ文字列パラメーターが含まれます。次に、この訪問者が別のページへのリンクをクリックした後、すぐに「戻る」ボタンをクリックしてランディングページに戻ったとします。この場合、この訪問者がランディングページに 2 回目に到達したとき、クエリ文字列パラメーターを含む URL によって、トラッキングコードが再び識別されます。この 2 回目のクリックスルーが登録されるので、クリックスルー数が誤って水増しされます。

このようなクリックスルー数の水増しを防ぐには、[!UICONTROL getValOnce] プラグインを使用して、各キャンペーンのクリックスルーをセッションあたり 1 回のみカウントするように設定することをお勧めします。[!UICONTROL getValOnce] プラグインについて詳しくは、[実装プラグイン](/help/implement/js-implementation/plugins/impl-plugins.md)を参照してください。

**構文と可能な値** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

*`campaign`* 変数には、他のすべての変数と同じ制限があります。値の範囲を、標準的な ASCII 文字に制限することをお勧めします。

**大文字と小文字の区別** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVar では大文字と小文字が区別されませんが、表示上は、各単語の 1 文字目が大文字で示されます。例えば、eVar1 の最初のインスタンスを「Logged In」に設定し、以降のすべてのインスタンスを「logged in」として渡した場合、レポートには常に eVar の値として「Logged In」と表示されます。

**例** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**設定** {#section_4083F281968443169EAF8C0E8529D7BC}

campaign の各値はユーザーに対して引き続き有効となり、有効期限が切れるまで、そのユーザーのアクティビティおよび成功イベントのクレジットを受け取ります。campaign 変数の有効期限は Admin Console で変更できます。

**注意事項、質問、ヒント** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* クリックスルー数の水増しを防ぐには、[!UICONTROL getValOnce] プラグインを使用して、キャンペーンのクリックスルーがセッションあたり 1 回のみカウントされるようにします。[!UICONTROL getValOnce] プラグインについて詳しくは、[実装プラグイン](/help/implement/js-implementation/plugins/impl-plugins.md)を参照してください。

* マーケティングキャンペーンの追跡およびキーワードの購入について詳しくは、[キャンペーン](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)を参照してください。
* キャンペーンの実際の値を確認するには、[!DNL DigitalPulse Debugger] を使用します（デバッガーで v0 を確認します）。デバッガーで v0 が表示されない場合は、そのキャンペーンデータは記録されていません。
