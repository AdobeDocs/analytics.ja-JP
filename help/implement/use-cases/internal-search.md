---
title: 内部検索用語をキャプチャする
description: カスタム変数を使用して内部検索用語を取り込みます。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# 内部検索用語をキャプチャする

内部検索レポートは多くの組織にとって不可欠で、Adobe Analyticsの標準のディメンションではありません。 ただし、実装の労力を最小限に抑えれば、内部検索用語のレポートを簡単に取り込むことができます。

## 前提条件 

[開発実装の検証と実稼動環境への公開](../launch/validate-publish-prod.md):このページは、基本的な実装が正常に動作し、DebuggerにAdobe Analyticsイメージリクエストが表示されることを前提としています。

## 内部検索に対応するeVarの作成

[コンバージョン変数admin](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を使用して、内部検索専用の新しいeVarを作成します。 eVarにわかりやすい名前（「内部検索用語」など）を付け、組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)に新しいeVarを記録します。

## 内部検索キーワードの特定

ほとんどの内部検索では、クエリ文字列を使用してページ間でキーワードデータを渡します。 サイトの内部検索を使用して、検索結果ページのURLをメモします。

`https://example.com/search.html?q=kittens`

サイトの内部検索でこのURLが使用されない場合は、データレイヤーやcookieなど、他の場所で検索語句を探します。 内部検索用語の見つけ方が不明な場合は、サイト開発チームに相談してください。

## クエリー文字列パラメーターをデータ要素に割り当てる

[データレイヤーオブジェクトをデータ要素](../launch/layer-to-elements.md)にマッピングします。 **[!UICONTROL データ要素のタイプ]**&#x200B;を選択する場合は、**[!UICONTROL JavaScript変数]**&#x200B;の代わりに&#x200B;**[!UICONTROL クエリー文字列パラメーター]**&#x200B;を選択します。 目的のクエリー文字列パラメーター（通常は`q`）をテキストフィールドに入れます。

## データ要素をeVarにマッピングする

[Analytics変数](../launch/elements-to-variable.md)にデータ要素をマッピングします。 必ず、レポートスイート設定で作成したeVarと同じデータを選択してください。

## タグのデプロイの開始

[開発環境にAnalytics実装をデプロイする](../launch/deploy-dev.md)に従います。 開発環境で動作していることを確認したら、[開発実装を検証し、実稼動環境にパブリッシュ](../launch/validate-publish-prod.md)できます。

## Workspaceのレポート

実装でデータを収集する時間を指定すると、Analysis Workspaceでディメンションの使用を開始できます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. Adobe Analyticsに自動的にログインしていない場合は、右上の9グリッドアイコンをクリックし、「**[!UICONTROL Analytics]**」を選択します。
3. 「**[!UICONTROL Workspace]**」タブをクリックし、新しいプロジェクトを作成します。
4. 「Dimension」の下で作成したeVarの名前を探し、ワークスペースキャンバスにドラッグします。
