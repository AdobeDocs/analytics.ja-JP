---
title: pageURL
description: 自動的に収集されたページのURLをサイトで上書きします。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageURL

AppMeasurementは、各ヒットでページURLを自動的に収集します。 AppMeasurementによって自動的に収集されたページURLを上書きする場合は、この変数を使用できます。 ほとんどの場合、この変数を設定する必要はありません。

> [!NOTE] この変数は、Analysis Workspaceでは使用できないディメンションです。 Data Warehouseおよびデータフィードでのみ使用できます。 ページURLをAnalysis Workspaceのディメンションとして使用する場合は、ヒットのたびにeVarに変 `pageURL` 数を渡すことを検討してください。

URLが255バイトを超える場合があります。 AppMeasurementは、イメージリク `g` エストのURLの最初の255バイトに対してクエリ文字列パラメーターを使用します。 URLが255バイトを超える場合、残りのURLはクエリ文字列パラメーターに保 `-g` 存されます。 URL内のプロトコルとクエリ文字列がこの変数に含まれます。

## Adobe Experience Platform LaunchのページURL

「起動」はページURLを自動的に設定します。 ただし、Analytics拡張機能（グローバル変数）の設定時またはルールで、ページURLの上書きを設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「ページURL [!UICONTROL 」セクションを見つ] けます。

ページURLは任意の文字列値に設定できます。

## AppMeasurementおよび起動のカスタムコードエディターでのs.pageURL

変数 `s.pageURL` は、ページのURLを含む文字列です。 AppMeasurementはこの変数を自動的に収集しますが、必要に応じてその値を上書きできます。

```js
s.pageURL = "https://example.com";
```

ページURLをレポートのディメンションとして使用する場合は、実装で次の使用を検討してください。

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
