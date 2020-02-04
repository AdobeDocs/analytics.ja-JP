---
title: server
description: '''Servers''ディメンションを設定します。'
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

この変 `server` 数は通常、サイトのホスト名を保存します。 これは、複数のドメインのデータを含むレポートスイートで一般的に使用されます。 機能的にはpropと同じです。

## Adobe Experience Platform Launchのサーバー

サーバーは、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL Server] 」セクションを探します。

serverは任意の文字列値またはデータ要素に設定できます。

## AppMeasurementのs.serverおよびカスタムコードエディターの起動

変数 `s.server` は、通常、サイトのホスト名を含む文字列です。 最大値は100バイトです。より長い値は切り捨てられます。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
