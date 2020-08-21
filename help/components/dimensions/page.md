---
title: ページ
description: ページの名前。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 88%

---


# ページ

「ページ」ディメンションは、サイトのページ名をリストします。これは、Adobe Analytics で最も一般的なディメンションの 1 つで、サイトのどのページのパフォーマンスが最も高いかに関する洞察を提供します。

このディメンションは、[サイトセクション](site-section.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`pageName`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、`pageName` 変数を使用してこのデータを収集します。`pageName` 変数が定義されていない場合は、ページの URL を使用してフォールバックします。

## Dimension項目

Dimension項目には、サイトのページ名が含まれます。 組織によって、使用する特定のディメンション項目が決まります。 組織によって、`document.title`値を使用する場合と、カスタム値を作成する場合があります。どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。

>[!NOTE]
>
>Reports &amp; Analytics では、コンバージョン指標はこのディメンションに線形アトリビューションを使用します。例えば、売上高は、`purchase` イベント前に表示されたすべてのページ間で分割されます。Analysis Workspace はデフォルトで最後のアトリビューションを使用し、任意のアトリビューションモデルを使用するオプションがあります。
