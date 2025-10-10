---
title: Activity Map ページ
description: リンクがクリックされたときのページ名。
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Activity Map ページ

「Activity Mapページ」 [ ディメンション ](overview.md) は、リンクがクリックされたときに訪問者が閲覧していたページを表示します。 このディメンションを使用して、最もクリックされたリンクを含むページを決定できます。 このディメンションは、Activity Map オーバーレイでも表示するリンクを決定するために使用されます。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)`c.a.activitymap.page` からデータを取得します。 実装で [Activity Map](/help/analyze/activity-map/overview.md) を使用している場合、リンクがクリックされると、このコンテキストデータ変数が自動的にデータを収集します。

このコンテキストデータ変数は、クリックされた特定のリンクに関して [ ページ ](page.md) ディメンションの値を収集します。 ページディメンションに値が含まれていない場合は、代わりに [ ページ URL](page-url.md) ディメンションが使用されます（ページディメンションで使用されるフォールバックと同様です）。 Activity Map データは、通常、リンクをクリックした後の次のヒットで送信されます。 このディメンションを使用すると、データ送信時のページ値ではなく、リンクがクリックされた際のページ値を特定できます。

## ディメンション項目

Dimension項目には、「ページ [ ディメンションで見つかったすべての値が含まれ ](page.md) す。
