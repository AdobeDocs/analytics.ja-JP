---
title: サーバー
description: サーバーの名前。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# サーバー

「サーバー」ディメンションは、通常、サイトのホスト名をリストします。 複数のドメインまたはサブドメインを組み合わせたレポートスイートでは、このディメンションは、どのドメインまたはサブドメインのパフォーマンスが最も良いかを調べるのに役立ちます。

このディメンションは、 [Page](page.md) And [Site Section](site-section.md) Dimensionsに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの2つの間にあります。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`server` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、この [`server`](/help/implement/vars/page-vars/server.md) 変数を使用してこのデータを収集します。

## ディメンション項目

ディメンション項目には、サイトのサーバーが含まれます。 組織によって、使用する特定のディメンション項目が決まります。 組織によっては、カスタム値 `window.location.hostname`を使用する場合と、カスタム値を作成する場合があります。 どの方法を使用する場合でも、一貫性があり、 [ソリューションデザインドキュメントに記録する必要があります](/help/implement/prepare/solution-design.md)。
