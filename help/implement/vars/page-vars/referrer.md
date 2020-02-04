---
title: referrer
description: 自動的に収集されたヒットのリファラーを上書きします。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# referrer

この変数は、 `referrer` レポートで自動的に収集されたリファラーよりも優先されます。 この変数は、リダイレクト中や、訪問者を一時的に支払いプロセッサーに転送するなど、リファラーが失われる可能性がある状況で役立ちます。 この変数は、「リファラー」ディメンションと「参照ドメイン」ディメンションの入力に役立ちます。

## Adobe Experience Platform Launchのリファラー

リファラーは、Analytics拡張機能（グローバル変数）の設定時にも、ルールでも設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「リファラー」セ [!UICONTROL クション] 。

referrerは、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.referrerおよびカスタムコードエディターの起動

変数 `s.referrer` は、前のページのURLを含む文字列です。 この変数には最大255バイトを格納できます。255バイトを超える値は切り捨てられます。 AppMeasurementは、この変数を自動的に次の値に設定しま `document.referrer`す。自動収集された値を上書きする場合を除き、この変数を設定する必要はありません。

```js
s.referrer = "https://example.com";
```

この変数をURL以外の値に設定しないでください。

## 例

多くの組織では、リダイレクトに関する実装を扱っています。 このユーティリティを使 [`getQueryParam`](../functions/util-getqueryparam.md) 用して、サイトでリファラーを受け入れる場合にURLからリファラーを取得できます。 クエリ文字列に含まれる値はURLエンコードしてください。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
