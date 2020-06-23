---
title: channel
description: 「サイトセクション」ディメンションを設定します。
translation-type: ht
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# channel

`channel` 変数は、通常、特定のページが存在するサイトのセクションを格納します。サイトで最も人気のあるグループを判断すると役立ちます。この変数は、「サイトセクション」ディメンションを入力します。

## Adobe Experience Platform Launch のチャネル

チャネルは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL チャネル]セクションを見つけます。

channel は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.channel

`s.channel` 変数は、通常、ページのサイトセクションを含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```
