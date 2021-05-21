---
title: サーバー
description: サーバーの名前。
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---

# サーバー

「サーバー」ディメンションは、通常、サイトのホスト名をリストします。複数のドメインまたはサブドメインを組み合わせたレポートスイートでは、このディメンションは、どのドメインまたはサブドメインのパフォーマンスが最も良いかを調べるのに役立ちます。

このディメンションは、[ページ](page.md)および[サイトセクション](site-section.md)ディメンションに関連しています。ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`server`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、[`server`](/help/implement/vars/page-vars/server.md) 変数を使用してこのデータを収集します。

## ディメンション項目

ディメンション項目には、サイトのサーバーが含まれます。組織は、使用する特定のディメンション項目を決定します。組織によって、`window.location.hostname` 値を使用する場合と、カスタム値を作成する場合があります。どの方法を使用する場合でも、一貫性があり、[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録する必要があります。
