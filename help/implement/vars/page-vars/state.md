---
title: 都道府県
description: Reports and Analytics で「訪問者の州レポート」を設定します。
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 87%

---

# 都道府県

>[!IMPORTANT]
>
> この変数は廃止され、Analysis Workspace で使用できるディメンションではありません。代わりに、「米国の州」ディメンションを使用します。このディメンションは、AppMeasurement によって訪問者の場所に基づいて自動的に収集されます。

以前のバージョンの Adobe Analytics では、訪問者が小売サイトの配送先情報を入力したときに `state` 変数が使用されていました。機能的には prop と同じですが、Analysis Workspace では使用できません。

## Adobe Analytics拡張機能を使用した状態

state は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL state] セクションを見つけます。

state は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.state

`s.state` 変数は、通常、訪問者の州または郡を含む文字列です。州名と 2 文字の州コードはどちらも有効です。最大値は 50 バイトです。より長い値は切り捨てられます。デフォルト値は空の文字列です。

```js
s.state = "Utah";
```
