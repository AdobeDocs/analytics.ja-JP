---
title: サイトセクション
description: サイトセクションの名前。
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---

# サイトセクション

「サイトセクション」ディメンションは、サイトのサイトセクションの名前をリストします。大規模なサイトでは、ページをセクションにグループ化すると便利です。このディメンションは、最も多く閲覧されたサイトセクションやパフォーマンスの高いサイトセクションを見るのに役立ちます。

このディメンションは、[ページ](page.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`ch`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、[`channel`](/help/implement/vars/page-vars/channel.md) 変数を使用してこのデータを収集します。

## ディメンション項目

ディメンション項目には、サイトのサイトセクションの名前が含まれます。組織は、使用する特定のディメンション項目を決定します。どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。
