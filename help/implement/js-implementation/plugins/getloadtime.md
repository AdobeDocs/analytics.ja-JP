---
description: ページの読み込み時間（10 分の 1 秒単位）を取得し、その値を prop、eVar および数値イベントに格納できます。
keywords: Analytics の導入
seo-description: ページの読み込み時間（10 分の 1 秒単位）を取得し、その値を prop、eVar および数値イベントに格納できます。
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: 開発者と導入
uuid: 5d26a69b- cbde-4be1- bac1-5ee8a4e55ca3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getLoadTime

ページの読み込み時間（10 分の 1 秒単位）を取得し、その値を prop、eVar および数値イベントに格納できます。

このプラグインを使用するには、関数のコードを挿入し、[!DNL s_code.js] ファイル内でその関数を 2 回呼び出します。1 回目はファイルの先頭で、2 回目は `doPlugins` セクションで呼び出します。このプラグインは意図的に s オブジェクトのメソッドとして定義されていません。s オブジェクトのメソッドとして定義した場合には、算出されるページ読み込み時間が長くなってしまうためです。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_968AC379C3004C359A85AFED5A48D5AE}

**関数の追加**

`s_getLoadTime` 関数の以下の定義を、[!DNL s_code.js] 内の「DO NOT ALTER ANYTHING BELOW THIS LINE」セクションより前の任意の場所に追加します。

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**最初の関数呼び出し**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**最後の関数呼び出し**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

使用例 1 - ページ読み込み時間を prop10 および eVar20 に保存する

```js
s.eVar20=s.prop10=s_getLoadTime();
```

使用例 2 - ページ読み込み時間を数値イベント event99 に保存する

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**（オプション）古いブラウザーのサポートの追加**

[window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/) プロパティのない古いブラウザーをサポートするには、ページの HTML の冒頭部にある HEAD セクション、または .js、.css などのファイルを呼び出している箇所の前に、以下の行を含めます。

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

