---
description: pageType 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。
keywords: Analytics の導入
seo-description: pageType 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。
seo-title: pageType変数の設定不正確
solution: Analytics
subtopic: トラブルシューティング
title: pageType変数の設定不正確
topic: 開発者と導入
uuid: eafaf58e- ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# pageType変数の設定不正確

pageType 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。

指定可能な値は errorPage のみです。

```js
pageType="errorPage"
```

404 エラーページには、*`pageName`*&#x200B;変数を入力しないでください。*`pageType`* 変数は指定した404エラーページでのみ設定する必要があります。Any page containing content should never have a value in the *`pageType`* variable. コンテンツを含むページには、この変数を次のように設定できます。

```js
pageType=""
```

コンテンツを含むページからこの変数を完全に削除することを推奨します。完全に削除すれば、この変数の設定目的について混乱を招かずに済みます。
