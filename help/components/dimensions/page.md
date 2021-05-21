---
title: ページ
description: ページの名前。
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '212'
ht-degree: 100%

---

# ページ

「ページ」ディメンションは、サイトのページ名をリストします。これは、Adobe Analytics で最も一般的なディメンションの 1 つで、サイトのどのページのパフォーマンスが最も高いかに関する洞察を提供します。

このディメンションは、[サイトセクション](site-section.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、[ページビュー呼び出し（`t()`）](/help/implement/vars/functions/t-method.md) の [`pageName` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 [リンクトラッキング呼び出し（`tl()`）](/help/implement/vars/functions/tl-method.md)は、`pageName`クエリ文字列が存在する場合でも、常にこのディメンションを削除します。

AppMeasurement は、[`pageName`](/help/implement/vars/page-vars/pagename.md) 変数を使用してこのデータを収集します。`pageName`変数が定義されていない場合は、[`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数の使用にフォールバックします。

## ディメンション項目

ディメンション項目には、サイトのページ名が含まれます。組織は、使用する特定のディメンション項目を決定します。組織によって、`document.title`値を使用する場合と、カスタム値を作成する場合があります。どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。

>[!NOTE]
>
>Reports &amp; Analytics では、コンバージョン指標はこのディメンションに線形アトリビューションを使用します。例えば、売上高は、`purchase` イベント前に表示されたすべてのページ間で分割されます。Analysis Workspace はデフォルトで最後のアトリビューションを使用し、任意のアトリビューションモデルを使用するオプションがあります。
