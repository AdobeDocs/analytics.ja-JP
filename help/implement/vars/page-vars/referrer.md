---
title: リファラー
description: 自動的に収集されたヒットのリファラーを上書きします。
feature: Appmeasurement Implementation
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YsYfgjFNDiJoQbvPU-XoB6bQt2IAriP1qmkOqc2lFDk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 85%

---

# リファラー

`referrer` 変数は、レポートで自動的に収集されたリファラーよりも優先されます。 この変数は、リダイレクト中や、訪問者を一時的に支払いプロセッサーに転送するなど、リファラーが失われる可能性がある状況で役立ちます。 この変数は、「リファラー」ディメンションと「参照ドメイン」ディメンションの入力に役立ちます。

## Web SDKを使用するリファラー

リファラーは次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

Web SDKには、使用可能な場合、送信されたすべてのイベントに`web.webReferrer.URL`が自動的に含まれます。

## Adobe Analytics拡張機能を使用したリファラー

referrer は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL リファラー]セクションを見つけます。

referrer は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.referrerとAnalytics拡張機能のカスタムコードエディター

`s.referrer` 変数は、前のページの URL を含む文字列です。 この変数には最大 255 バイトを格納できます。255 バイトを超える値は切り捨てられます。 AppMeasurement は、この変数を自動的に `document.referrer` に設定します。自動収集された値を上書きする場合を除き、この変数を設定する必要はありません。

```js
s.referrer = "https://example.com";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>この変数を URL 以外の値に設定しないでください。 URL のプロトコルを削除しないでください。

## 例

多くの組織では、リダイレクトに関する実装を扱っています。 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) ユーティリティを使用して、サイトでリファラーを受け入れる場合に URL からリファラーを取得できます。 クエリ文字列に含まれる値は URL エンコードしてください。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
