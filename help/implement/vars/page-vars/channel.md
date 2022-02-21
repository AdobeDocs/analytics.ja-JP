---
title: チャネル
description: 「サイトセクション」ディメンションを設定します。
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 100%

---

# チャネル

`channel` 変数は、通常、特定のページが存在するサイトのセクションを格納します。サイトで最も人気のあるグループを判断すると役立ちます。この変数は、「サイトセクション」ディメンションを入力します。

## Adobe Experience Platform のタグを使用したチャネル

チャネルは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL チャネル]セクションを見つけます。

channel は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および カスタムコードエディターの s.channel

`s.channel` 変数は、通常、ページのサイトセクションを含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.channel = digitalData.page.category.primaryCategory;
```
