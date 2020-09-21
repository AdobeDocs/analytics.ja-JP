---
title: ページ
description: ページの名前。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 82%

---


# ページ

「ページ」ディメンションは、サイトのページ名をリストします。これは、Adobe Analytics で最も一般的なディメンションの 1 つで、サイトのどのページのパフォーマンスが最も高いかに関する洞察を提供します。

このディメンションは、[サイトセクション](site-section.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、 [`pageName` ページ表示呼び出しの](/help/implement/validate/query-parameters.md) クエリ列 [(`t()`)からデータを取得します](/help/implement/vars/functions/t-method.md)。 [リンクトラッキングコール(`tl()`)](/help/implement/vars/functions/tl-method.md) 。 `pageName` クエリ文字列が存在する場合でも、常にこのディメンションを除去します。

AppMeasurement は、[`pageName`](/help/implement/vars/page-vars/pagename.md) 変数を使用してこのデータを収集します。If the `pageName` variable is not defined, it falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## ディメンション項目

ディメンション項目には、サイトのページ名が含まれます。組織は、使用する特定のディメンション項目を決定します。組織によって、`document.title`値を使用する場合と、カスタム値を作成する場合があります。どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。

>[!NOTE]
>
>Reports &amp; Analytics では、コンバージョン指標はこのディメンションに線形アトリビューションを使用します。例えば、売上高は、`purchase` イベント前に表示されたすべてのページ間で分割されます。Analysis Workspace はデフォルトで最後のアトリビューションを使用し、任意のアトリビューションモデルを使用するオプションがあります。
