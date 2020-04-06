---
title: pageName
description: サイトのページの名前。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# pageName

`pageName` 変数は通常、特定のページの名前を保存します。最も人気のある個々のページを判断すると役立ちます。この変数は、「ページ名」ディメンションを設定します。

>[!NOTE] このディメンションは、常にリンクトラッキングコールから削除されます。リンクが追跡されたページ名を確認する場合は、この変数を eVar にコピーすることを検討してください。

この変数が特定のページトラッキングコールで定義されていない場合は、代わりに [`pageURL`](pageurl.md) 変数が使用されます。

## Adobe Experience Platform Launch のページ名

ページ名は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Page name] section.

ページ名は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.pageName

`s.pageName` 変数は、通常、ページの名前を含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。この切り捨てには、この変数が空白の場合に `pageURL` にフォールバックされるインスタンスが含まれます。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
