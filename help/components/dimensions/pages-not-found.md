---
title: エラーページ（404）
description: サイトでエラーを返したURL。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# エラーページ（404）

*このヘルプページでは、「ページが見つかりません」がディメンションとして機能する方法を説明します。 詳しくは、「[ページが見つかりません](../metrics/pages-not-found.md)」指標を参照してください。*

エラーを含むURLを示す「ページが見つかりません」ディメンション。 このディメンションは、訪問者がサイトで発生するエラーの数を減らす場合に役立ちます。

* このディメンションを [フロービジュアライゼーションで使用して](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) 、訪問者がエラーに到達するためにクリックスルーしたページを確認できます。 その後、組織の開発チームと協力して各ページのリンクを修正できます。
* このディメンションを「 [](referrer.md) 転送者」ディメンションと共に使用して、外部リンクから訪問者がサイトに到達した場所を確認できます。 その後、目的の場所にリダイレクトを実装するか、サードパーティと協力してリンクを修正します。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの文字列 [`pageType` と `g` クエリ文字列](/help/implement/validate/query-parameters.md) からデータを取得します。 `pageType` クエリ文字列が等しい場合 `errorPage`、 `g` クエリ文字列（ページURL）が記録されます。 AppMeasurementは、この [`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数を使用してこのデータを収集します。 変数を定義しない場合、または `pageType` 変数を以外の値に設定した場合、このディメンションのデータは収集されません `errorPage`。

## 分析コード値

ディメンション値には、エラーが発生したサイト上のページのURLが含まれます。
