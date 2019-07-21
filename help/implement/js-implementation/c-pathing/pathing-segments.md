---
description: 一般に、ユーザータイプによるパスのセグメント化は、サイト上で特定のユーザータイプのパスがどのようなものであるかを把握する場合に必要となります。
keywords: Analytics の導入
seo-description: 一般に、ユーザータイプによるパスのセグメント化は、サイト上で特定のユーザータイプのパスがどのようなものであるかを把握する場合に必要となります。
seo-title: ユーザータイプ別のセグメントパス
solution: Analytics
title: ユーザータイプ別のセグメントパス
topic: 開発者と導入
uuid: 5c298f39-381d-453b- a608-109e3276b361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# ユーザータイプ別のセグメントパス

一般に、ユーザータイプによるパスのセグメント化は、サイト上で特定のユーザータイプのパスがどのようなものであるかを把握する場合に必要となります。

ユーザータイプとページ名を [!UICONTROL sprop] に連結して、その [!UICONTROL sprop] に対してパスを有効化できます。

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. 各ページでこれら 2 つのユーザータイプを区別し、これらのユーザーの値を目的の [!UICONTROL sprop] に入力する必要があります。prop に入力すると、次のように表示されます。

```js
 s.prop1=”Registered : “ + s.pageName;
```

ユーザーが登録済みユーザーであり、ホームページにアクセスした場合、prop の値は次のように表示されます。

```js
 “Registered : Home Page”
```

このユーザーが「Page 2」という別のページにクリックして移動すると、そのページでの値は次のように表示されます。

```js
 “Registered : Page 2”
```

[!UICONTROL パス]を有効にすると、これら 2 つの値が連続して表示されます。登録済みユーザーがどのようにしてホームページから移動したかを把握したい場合、いずれかのパスレポートで「Registered : Home Page」という値を探し、それらのユーザーがアクセスした次のページを確認します。この例の場合、登録済みユーザーは「Page 2」に移動しています。
