---
title: 都道府県
description: Reports & Analyticsで「訪問者の州レポート」を設定します。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] この変数は廃止され、Analysis Workspaceで使用できるディメンションではありません。 代わりに、「米国の州」ディメンションを使用します。このディメンションは、AppMeasurementによって訪問者の場所に基づいて自動的に収集されます。

以前のバージョンのAdobe Analyticsでは、訪問者が `state` 小売サイトの配送先情報を入力したときにこの変数が使用されていました。 機能的にはpropと同じですが、Analysis Workspaceでは使用できません。

## Adobe Experience Platform Launchの状態

状態は、Analytics拡張の設定中（グローバル変数）またはルールの下で設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL State] 」セクション

stateは任意の文字列値またはデータ要素に設定できます。

## AppMeasurementのs.stateとカスタムコードエディターの起動

変数 `s.state` は、通常、訪問者の州または郡を含む文字列です。 フルステート名または2文字のコードはどちらも有効です。 最大値は50バイトです。より長い値は切り捨てられます。 デフォルト値は空の文字列です。

```js
s.state = "Utah";
```
