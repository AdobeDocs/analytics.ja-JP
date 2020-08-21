---
title: pageURL
description: 自動的に収集されたページの URL をサイトで上書きします。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '299'
ht-degree: 100%

---


# pageURL

AppMeasurement は、各ヒットでページ URL を自動的に収集します。AppMeasurement によって自動的に収集されたページ URL を上書きする場合は、この変数を使用できます。ほとんどの場合、この変数を設定する必要はありません。

>[!NOTE]
>
> この変数は、Analysis Workspace では使用できないディメンションで、Data Warehouse およびデータフィードでのみ使用できます。ページ URL を Analysis Workspace のディメンションとして使用する場合は、ヒットのたびに eVar に `pageURL` 変数を渡すことを検討してください。

URL が 255 バイトを超える場合があります。AppMeasurement は、イメージリクエストの URL の最初の 255 バイトに対して `g` クエリー文字列パラメーターを使用します。URL が 255 バイトを超える場合、残りの URL は `-g` クエリー文字列パラメーターに保存されます。URL 内のプロトコルとクエリー文字列がこの変数に含まれます。

## Adobe Experience Platform Launch のページ URL

Launch はページ URL を自動的に設定します。ただし、Analytics 拡張機能の設定時（グローバル変数）またはルールで、ページ URL の上書きを設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL ページ URL] セクションを見つけます。

ページ URL は任意の文字列値に設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.pageURL

`s.pageURL` 変数は、ページの URL を含む文字列です。AppMeasurement はこの変数を自動的に収集しますが、必要に応じてその値を上書きできます。

```js
s.pageURL = "https://example.com";
```

ページ URL をレポートのディメンションとして使用する場合は、実装で次の使用を検討してください。

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
