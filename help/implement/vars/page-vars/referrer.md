---
title: リファラー
description: 自動的に収集されたヒットのリファラーを上書きします。
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '262'
ht-degree: 100%

---

# リファラー

`referrer` 変数は、レポートで自動的に収集されたリファラーよりも優先されます。この変数は、リダイレクト中や、訪問者を一時的に支払いプロセッサーに転送するなど、リファラーが失われる可能性がある状況で役立ちます。この変数は、「リファラー」ディメンションと「参照ドメイン」ディメンションの入力に役立ちます。

## Adobe Experience Platform のタグを使用したリファラー

referrer は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL リファラー]セクションを見つけます。

referrer は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および カスタムコードエディターの s.referrer

`s.referrer` 変数は、前のページの URL を含む文字列です。この変数には最大 255 バイトを格納できます。255 バイトを超える値は切り捨てられます。AppMeasurement は、この変数を自動的に `document.referrer` に設定します。自動収集された値を上書きする場合を除き、この変数を設定する必要はありません。

```js
s.referrer = "https://example.com";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>この変数を URL 以外の値に設定しないでください。URL のプロトコルを削除しないでください。

## 例

多くの組織では、リダイレクトに関する実装を扱っています。[`Util.getQueryParam()`](../functions/util-getqueryparam.md) ユーティリティを使用して、サイトでリファラーを受け入れる場合に URL からリファラーを取得できます。クエリー文字列に含まれる値は URL エンコードしてください。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
