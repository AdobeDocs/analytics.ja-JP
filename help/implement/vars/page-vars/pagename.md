---
title: pageName
description: サイト上のページの名前。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# pageName

この変 `pageName` 数は、通常、特定のページの名前を格納します。 最も人気のある個々のページを判断すると役に立ちます。 この変数は、「ページ名」ディメンションを設定します。

> [!NOTE] このディメンションは、常にリンクトラッキングの呼び出しから削除されます。 リンクが追跡されたページ名を確認する場合は、この変数をeVarにコピーすることを検討してください。

この変数が特定のページトラッキングコールで定義されていない場合、代わりに変 [`pageURL`](pageurl.md) 数が使用されます。

## Adobe Experience Platform Launchのページ名

ページ名は、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Page name] section.

ページ名は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.pageNameとカスタムコードエディターの起動

変数 `s.pageName` は、通常、ページの名前を含む文字列です。 最大値は100バイトです。より長い値は切り捨てられます。 この切り捨てには、この変数が空白の場合にフォールバッ `pageURL` クされるインスタンスが含まれます。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
