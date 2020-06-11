---
title: サイトセクション
description: サイトセクションの名前。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# サイトセクション

「サイトセクション」ディメンションは、サイトのサイトセクションの名前をリストします。 大規模なサイトでは、ページをセクションにグループ化すると便利です。 このディメンションは、最も多く閲覧されたサイトセクションやパフォーマンスの高いサイトセクションを見るのに役立ちます。

このディメンションは、 [Page](page.md) ディメンションと [Server](server.md) ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの2つの間にあります。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`ch` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、この [`channel`](/help/implement/vars/page-vars/channel.md) 変数を使用してこのデータを収集します。

## 分析コード値

ディメンション値には、サイトのサイトセクションの名前が含まれます。 組織は、使用する特定のディメンション値を決定します。 どの方法を使用する場合でも、一貫性があり、 [ソリューションデザインドキュメントに記録する必要があります](/help/implement/prepare/solution-design.md)。
