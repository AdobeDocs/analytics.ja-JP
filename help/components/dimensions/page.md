---
title: ページ
description: ページの名前。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# ページ

「ページ」ディメンションは、サイトのページ名をリストします。 これは、Adobe Analyticsで最も一般的に使用されるディメンションの1つで、サイトのどのページのパフォーマンスが最も高いかに関する洞察を提供します。

このディメンションは、 [Siteセクション](site-section.md) と [Server](server.md) ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの2つの間にあります。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`pageName` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、この `pageName` 変数を使用してこのデータを収集します。 変数が定義されていない場合は `pageName` 、ページのURLを使用して戻ります。

## 分析コード値

ディメンション値には、サイトのページ名が含まれます。 組織は、使用する特定のディメンション値を決定します。 組織によっては直接使用する場合 `document.title`と、カスタム階層リンクを作成する場合があります。 どの方法を使用する場合でも、一貫性があり、 [ソリューションデザインドキュメントに記録する必要があります](/help/implement/prepare/solution-design.md)。

>[!NOTE] Reports &amp; Analyticsでは、コンバージョン指標は、このディメンションに線形アトリビューションを使用します。 For example, revenue is split between all pages viewed in a visit before a `purchase` event. 分析ワークスペースでは、デフォルトで最後のアトリビューションが使用され、任意のアトリビューションモデルを使用するオプションがあります。
