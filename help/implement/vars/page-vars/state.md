---
title: state
description: （撤回済み）「訪問者の州レポート」が入力されましたが、これは使用できなくなりました。
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 80%

---

# state

>[!IMPORTANT]
>
>この変数は廃止されており、Analysis Workspace で使用できるディメンションではありません。代わりに、[ 米国の州 ](/help/components/dimensions/us-states.md) ディメンションを使用します。このディメンションは、訪問者の場所に基づいてAppMeasurementによって自動収集されます。

以前のバージョンの Adobe Analytics では、訪問者が小売サイトの配送先情報を入力したときに `state` 変数が使用されていました。機能的には prop と同じですが、Analysis Workspace では使用できません。

## Adobe Analytics 拡張機能を使用した state

state は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;]」を [!UICONTROL &#x200B; 変数を設定 &#x200B;] に設定します。
6. [!UICONTROL state] セクションを見つけます。

state は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.state

`s.state` 変数は、通常、訪問者の州または郡を含む文字列です。州名と 2 文字の州コードはどちらも有効です。最大値は 50 バイトです。より長い値は切り捨てられます。デフォルト値は空の文字列です。

```js
s.state = "Utah";
```
