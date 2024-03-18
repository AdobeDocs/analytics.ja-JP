---
title: リファラー
description: 自動的に収集されたヒットのリファラーを上書きします。
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 80%

---

# リファラー

`referrer` 変数は、レポートで自動的に収集されたリファラーよりも優先されます。この変数は、リダイレクト中や、訪問者を一時的に支払いプロセッサーに転送するなど、リファラーが失われる可能性がある状況で役立ちます。この変数は、「リファラー」ディメンションと「参照ドメイン」ディメンションの入力に役立ちます。

## Web SDK を使用したリファラー

リファラーは次の変数にマッピングされます。

* [XDM オブジェクト](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [データオブジェクト](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

Web SDK は、次を自動的に含めます `web.webReferrer.URL` 送信されるイベントごと（可能な場合）に

## Adobe Analytics拡張機能を使用したリファラー

referrer は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. を設定します。 [!UICONTROL 拡張] Adobe Analyticsのドロップダウンリスト、 [!UICONTROL アクションタイプ] から [!UICONTROL 変数を設定].
6. [!UICONTROL リファラー]セクションを見つけます。

referrer は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementの s.referrer と Analytics 拡張機能のカスタムコードエディター

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

多くの組織では、リダイレクトに関する実装を扱っています。[`Util.getQueryParam()`](../functions/util-getqueryparam.md) ユーティリティを使用して、サイトでリファラーを受け入れる場合に URL からリファラーを取得できます。クエリ文字列に含まれる値は URL エンコードしてください。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
