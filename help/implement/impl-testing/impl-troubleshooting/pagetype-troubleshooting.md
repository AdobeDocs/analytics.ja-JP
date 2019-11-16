---
description: pageType 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: pageType 変数の間違った設定
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# pageType 変数の間違った設定

pageType 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。

指定可能な値は errorPage のみです。

```js
pageType="errorPage"
```

404 エラーページには、*`pageName`*&#x200B;変数を入力しないでください。*`pageType`* 変数は、指定した 404 エラーページでのみ設定してください。コンテンツを含むページでは、*`pageType`* 変数に値を含めないでください。コンテンツを含むページには、この変数を次のように設定できます。

```js
pageType=""
```

コンテンツを含むページからこの変数を完全に削除することを推奨します。完全に削除すれば、この変数の設定目的について混乱を招かずに済みます。
