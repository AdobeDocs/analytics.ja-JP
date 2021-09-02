---
title: 内部検索用語の取り込み
description: カスタム変数を使用して内部検索用語を取り込みます。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# 内部検索用語の取り込み

内部検索レポートは多くの組織にとって不可欠で、Adobe Analytics の標準のディメンションではありません。ただし、最小限の実装の労力で、内部検索キーワードレポートを簡単に取り込むことができます。

## 前提条件 

[開発実装の検証と実稼動環境への公開](../launch/validate-publish-prod.md)：このページは、基本的な実装が正常に動作し、Adobe デバッガーに Adobe Analytics イメージリクエストが表示されることを前提としています。

## 内部検索に対応する eVar の作成

[コンバージョン変数 admin](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) を使用して、内部検索専用の新しい eVar を作成します。eVar にわかりやすい名前（「内部検索キーワード」など）を付け、組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)に新しい eVar を記録します。

## 内部検索キーワードの決定

ほとんどの内部検索では、クエリ文字列を使用してページ間でキーワードデータを渡します。サイトの内部検索を使用して、検索結果ページの URL をメモします。

`https://example.com/search.html?q=kittens`

サイトの内部検索でこの URL が使用されない場合は、データレイヤーや Cookie など、他の場所で検索語句を探します。内部検索キーワードの見つけ方が不明な場合は、サイト開発チームに相談してください。

## クエリ文字列パラメーターのデータ要素への割り当て

[データレイヤーオブジェクトのデータ要素へのマッピング](../launch/layer-to-elements.md)に従ってください。**[!UICONTROL データ要素のタイプ]**&#x200B;を選択する場合は、**[!UICONTROL JavaScript 変数]**&#x200B;の代わりに&#x200B;**[!UICONTROL クエリ文字列パラメーター]**&#x200B;を選択します。目的のクエリ文字列パラメーター（通常は `q`）をテキストフィールドに入れます。

## データ要素の eVar へのマッピング

[データ要素の Analytics 変数へのマッピング](../launch/elements-to-variable.md)に従ってください。必ず、レポートスイート設定で作成した eVar と同じデータを選択します。

## タグのデプロイの開始

[開発環境への Analytics 実装のデプロイ](../launch/deploy-dev.md)に従ってください。開発環境で動作していることを確認したら、[開発実装を検証し、実稼動環境に公開](../launch/validate-publish-prod.md)できます。

## Workspace のレポート

実装にデータを収集する時間を与えると、Analysis Workspace でディメンションの使用を開始できます。

1. Adobe ID の認証情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. Adobe Analytics に自動的にログインしていない場合は、右上の 9 グリッドアイコンをクリックし、「**[!UICONTROL Analytics]**」を選択します。
3. 「**[!UICONTROL Workspace]**」タブをクリックし、新しいプロジェクトを作成します。
4. 「ディメンション」の下で作成した eVar の名前を探し、ワークスペースキャンバスにドラッグします。
