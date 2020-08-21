---
title: 最終訪問からの日数
description: 現在のヒットから最後のヒットまでの日数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 74%

---


# 最終訪問からの日数

「前回の訪問からの日数」ディメンションは、訪問者の現在のヒットと前回の訪問との間に経過した時間を測定します（存在する場合）。このディメンションは、サイトの訪問後に訪問者が実行する行動を把握するのに役立ちます。以下に例を示します。

* ユーザーはどのぐらいの頻度で自分のサイトを再訪問しているか。
* 再訪問頻度はコンバージョンとどう関連しているか。リピート購入者は頻繁に訪問するかどうか。
* キャンペーンでクリックスルーしたユーザーは頻繁に訪問するか。

初回訪問者は、このディメンションには含まれません。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

Dimension項目には、訪問者の最終訪問から現在のヒットまでの日数が含まれます。 Each number of days is a separate dimension item, with `"Same day"` occurring where a visitor&#39;s last visit and the current hit happened on the same day.
