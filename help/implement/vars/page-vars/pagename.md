---
title: pageName
description: サイト上のページの名前。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# pageName

この変 `pageName` 数は通常、特定のページの名前を保存します。 最も人気のある個々のページを判断すると役立ちます。 この変数は、「ページ名」ディメンションを設定します。

> [!NOTE] このディメンションは、常にリンクトラッキングコールから削除されます。 リンクが追跡されたページ名を確認する場合は、この変数をeVarにコピーすることを検討してください。

この変数が特定のページトラッキングコールで定義されていない場合は、代わりに変 `pageURL` 数が使用されます。

## Adobe Experience Platform Launchのページ名

ページ名は、Analytics拡張機能（グローバル変数）の設定時にも、ルールでも設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「ページ名 [!UICONTROL 」セクション] 。

ページ名は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.pageNameとカスタムコードエディターの起動

変数 `s.pageName` は、通常、ページの名前を含む文字列です。 最大値は100バイトです。より長い値は切り捨てられます。 この切り捨てには、この変数が空白の場合にフォールバックさ `pageURL` れるインスタンスが含まれます。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
