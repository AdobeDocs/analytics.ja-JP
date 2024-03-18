---
title: pageName
description: サイトのページの名前。
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 80%

---

# pageName

`pageName` 変数は通常、特定のページの名前を保存します。最も人気のある個々のページを判断すると役立ちます。この変数は、[ページ](/help/components/dimensions/page.md)ディメンションを設定します。

この変数が特定のページトラッキングコールで定義されていない場合は、代わりに [`pageURL`](pageurl.md) 変数が使用されます。

>[!NOTE]
>
>アドビのデータ収集サーバーは、すべての[リンクトラッキング](/help/implement/vars/functions/tl-method.md)イメージリクエストからこのディメンションを除外します。 このディメンションをリンクトラッキングのヒットで表示する場合は、このディメンションを [eVar](evar.md) にコピーすることを検討してください。

## Web SDK を使用したページ名

ページ名は次の変数にマッピングされます。

* [XDM オブジェクト](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [データオブジェクト](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Adobe Analytics拡張機能を使用したページ名

ページ名は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. を設定します。 [!UICONTROL 拡張] Adobe Analyticsのドロップダウンリスト、 [!UICONTROL アクションタイプ] から [!UICONTROL 変数を設定].
6. [!UICONTROL ページ名]セクションを見つけます。

ページ名は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.pageName

`s.pageName` 変数は、通常、ページの名前を含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。この切り捨てには、この変数が空白の場合に `pageURL` にフォールバックされるインスタンスが含まれます。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
