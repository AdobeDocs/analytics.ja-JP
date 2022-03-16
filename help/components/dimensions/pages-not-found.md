---
title: エラーページ（ディメンション）
description: サイトでエラーを返した URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 98%

---

# エラーページ（404）

*このヘルプページでは、「エラーページ（404）」がディメンションとして機能する方法を説明します。詳しくは、[エラーページ（404）](../metrics/pages-not-found.md)指標を参照してください。*

エラーを含む URL を示す「エラーページ（404）」ディメンション。このディメンションは、訪問者がサイトで発生するエラーの数を減らす場合に役立ちます。

* このディメンションを[フロービジュアライゼーション](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)で使用して、訪問者がエラーに到達するためにクリックスルーしたページを確認できます。その後、組織の開発チームと協力して各ページのリンクを修正できます。
* このディメンションを[リファラー](referrer.md)ディメンションと共に使用して、外部リンクから訪問者がサイトに到達した場所を確認できます。その後、目的の場所にリダイレクトを実装するか、サードパーティと協力してリンクを修正します。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの [`pageType` クエリ文字列と `g` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。`pageType` クエリ文字列が `errorPage` に等しい場合、`g` クエリ文字列（ページ URL）が記録されます。AppMeasurement は、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数を使用してこのデータを収集します。`pageType` 変数が定義されていない場合、または `errorPage` 以外の値に設定された場合、このディメンションのデータは収集されません 。

## ディメンション項目

ディメンション項目には、エラーが発生したサイト上のページの URL が含まれます。
