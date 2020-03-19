---
title: referrer
description: ヒットに対して自動的に収集されたリファラーを上書きします。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referrer

この変数は、 `referrer` レポートで自動的に収集されたリファラーよりも優先されます。 この変数は、リダイレクト中や一時的に訪問者を支払いプロセッサに転送するなど、リファラーが失われる可能性がある状況で役立ちます。 この変数は、「リファラー」ディメンションと「参照ドメイン」ディメンションの入力に役立ちます。

## Adobe Experience Platform Launchのリファラー

リファラーは、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Referrer] section.

referrerは、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.referrerおよびカスタムコードエディターの起動

変数 `s.referrer` は、前のページのURLを含む文字列です。 この変数には、最大255バイトを格納できます。255バイトを超える値は切り捨てられます。 AppMeasurementは、この変数を自動的に次の値に設定しま `document.referrer`す。自動的に収集された値を上書きする場合を除き、この変数を設定する必要はありません。

```js
s.referrer = "https://example.com";
```

この変数をURL以外の値に設定しないでください。

## 例   

多くの組織では、リダイレクトに関する実装を扱っています。 このユーティリティを使用 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) して、サイトでリファラーが設定されている場合にURLからリファラーを取得できます。 クエリ文字列に含まれる値はURLエンコードしてください。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
