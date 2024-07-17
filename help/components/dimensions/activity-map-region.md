---
title: Activity Map 地域
description: サイトでクリックされた地域。
feature: Dimensions
role: User, Admin
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Activity Map 地域

「Activity Map地域」 [ ディメンション ](overview.md) には、最もクリックされたサイトの地域が表示されます。 このディメンションは、個々のリンクではなく、サイトの包括的な領域にわたるクリック数を比較する場合に役立ちます。 また、動的コンテンツを提供するサイトの領域にも役立ちます。 例えば、ニュース記事が回転しているフロントページがある場合、[Activity Mapリンク ](activity-map-link.md) のディメンションを使用すると、リンクテキストが常に変化するので困難です。 ただし、これらのリンクは同じ領域を使用するので、個々のリンクが毎日変更される可能性がある場合でも、その領域のパフォーマンスを分析できます。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)`c.a.activitymap.region` からデータを取得します。 実装で [ 変数を使用している場合 ](/help/analyze/activity-map/overview.md) このコンテキストActivity Mapは、リンクがクリックされると、データを自動的に収集します。

クリックされた特定のリンクに対して、以下の項目で親 DOM 要素を（順に）確認します。

* [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) で設定された属性の値 – デフォルトで `id` 属性に設定されます
* 属性が `role="region"` の場合の `aria-label` 属性の値
* セマンティック要素 `<header>`、`<main>`、`<footer>`、`<nav>` （Web SDK のみ）

親 DOM 要素が上記の条件のいずれも満たさない場合、検索は DOM 階層の上に再帰的に続行されます。 一致する要素が見つからない場合は、値 `BODY` が返されます。

## ディメンション項目

Dimension項目には、サイトでラベルを付けたリージョンが含まれます。 特定のリージョン値は、使用される属性と、セマンティックHTML要素が存在するかどうかによって異なります。
