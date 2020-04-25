---
description: 入口は、訪問の最初の値として特定の値が取得された回数を表します。入口は 1 回の訪問で一度しか生じません。ただし、変数を定義していない場合、必ずしも初回ヒットではありません。
title: 入口
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# 入口

「入口」は、訪問の最初の値として特定の値が取り込まれた回数を表します。 入口は 1 回の訪問で一度しか生じません。ただし、変数を定義していない場合、必ずしも初回ヒットではありません。

2020 年 3 月の時点で、Analysis Workspace における「なし」の値と入口／出口との相互作用を変更しました。分析ワークスペースで「なし」のオン/オフを切り替えられるようになったので、入口または出口の後に「なし」を適用します。以前は（eVarの場合）「なし」を適用していました。  例えば、訪問の最初のヒットにeVar21の値がなく、2番目のヒットに値がないとします。 Reports &amp; Analytics では、そのエントリに対して「未指定」と表示されますが、Analysis Workspace では 2 回目のヒットの値が表示されます。

入口ページは、訪問を分類する基準となります。つまり、訪問のすべてのヒットに対して持続性を持ちます。詳しくは、[分類とセグメント化コンテナ](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html)を参照してください。
