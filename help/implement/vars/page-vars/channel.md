---
title: channel
description: 「サイトセクション」ディメンションを設定します。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# channel

この変 `channel` 数は、通常、特定のページが存在するサイトのセクションを格納します。 サイトで最も人気のあるグループを判断すると役立ちます。 この変数は、「サイトセクション」ディメンションを入力します。

## Adobe Experience Platform Launchのチャネル

チャネルは、Analytics拡張機能（グローバル変数）の設定中に、またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. [チャネル  ]セクションを見つけます。

channelは任意の文字列値またはデータ要素に設定できます。

## AppMeasurementのs.channelとカスタムコードエディターの起動

変数 `s.channel` は、通常、ページのサイトセクションを含む文字列です。 最大値は100バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```
