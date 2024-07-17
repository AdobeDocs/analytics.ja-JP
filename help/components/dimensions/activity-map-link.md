---
description: クリックされたリンク名。
title: Activity Map リンク
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Activity Map リンク

「Activity Mapリンク」 [ ディメンション ](overview.md) には、クリックされた最も人気のあるリンクが表示されます。 このディメンションを使用すると、リンクがクリックされた場所に関係なく、サイト上のどのリンクが最も使用されているかを比較できます。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)`c.a.activitymap.link` からデータを取得します。 実装で [ 変数を使用している場合 ](/help/analyze/activity-map/overview.md) このコンテキストActivity Mapは、リンクがクリックされると、データを自動的に収集します。

クリックされた特定のリンクに対して、Activity Mapは（順に）以下を検索します。

1. `s_objectID` 変数
1. リンクの内部テキスト
1. 画像の `alt` 属性
1. `title` 属性
1. 画像の `src` 属性
1. フォームの `action` 属性

クリックされた要素に上記の条件がいずれも含まれていない場合、Activity Mapはそのクリックのデータを収集しません。

## ディメンション項目

Dimension項目には、訪問者がクリックしたリンクテキストまたはその他のリンク属性が含まれます。 組織のサイト構造と実装によって、収集される正確な値が決まります。
