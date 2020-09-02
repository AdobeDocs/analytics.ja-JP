---
title: pageName
description: サイトのページの名前。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 81%

---


# pageName

`pageName` 変数は通常、特定のページの名前を保存します。最も人気のある個々のページを判断すると役立ちます。This variable populates the [Page](/help/components/dimensions/page.md) dimension.

この変数が特定のページトラッキングコールで定義されていない場合は、代わりに [`pageURL`](pageurl.md) 変数が使用されます。

>[!NOTE]
>
>Adobeデータ収集サーバーは、このディメンションをすべての [リンクトラッキング](/help/implement/vars/functions/tl-method.md) イメージリクエストから除去します。 このディメンションをリンクトラッキングのヒットで表示する場合は、このディメンションを [eVarにコピーすることを検討してください](evar.md)。

## Adobe Experience Platform Launch のページ名

ページ名は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL ページ名]セクションを見つけます。

ページ名は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.pageName

`s.pageName` 変数は、通常、ページの名前を含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。この切り捨てには、この変数が空白の場合に `pageURL` にフォールバックされるインスタンスが含まれます。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

デー `digitalData` タレイヤーを使用する場合 [](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
