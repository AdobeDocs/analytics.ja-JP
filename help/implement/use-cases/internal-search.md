---
title: 内部検索用語を捕捉します。
description: 内部検索用語を取り込むには、カスタム変数を使用します。
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# 内部検索用語を捕捉します。

内部検索レポートは多くの組織にとって不可欠であり、Adobe Analyticsにとってすぐに使える次元ではありません。 ただし、実装を最小限に抑えれば、内部検索用語のレポートを簡単に捕捉できます。

## 前提条件

[開発実装の検証と実稼働環境への発行](../launch/validate-publish-prod.md):このページは、基本的な作業用の実装があり、AdobeデバッガにAdobe Analyticsのイメージリクエストが表示されることを前提としています。

## 内部検索に対応するeVarの作成

[コンバージョン変数admin](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)に従って、内部検索専用の新しいeVarを作成します。 簡単に認識できる名前（「内部検索用語」など）をeVarに付け、組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)に新しいeVarを記録します。

## 内部検索キーワードの特定

ほとんどの内部検索では、クエリ文字列を使用してページ間でキーワードデータを渡します。 サイトの内部検索を使用して、検索結果ページのURLをメモします。

`https://example.com/search.html?q=kittens`

サイトの内部検索でURLが使用されていない場合は、データレイヤーやcookieなど、他の場所で検索語句を探します。 サイト内検索用語の場所が不明な場合は、サイト開発チームに相談してください。

## クエリ文字列パラメーターをデータ要素に割り当てる

[データレイヤーオブジェクトをデータ要素](../launch/layer-to-elements.md)にマップするのに従います。 「**[!UICONTROL データ要素のタイプ]**」を選択する場合は、「**[!UICONTROL JavaScript変数]**」の代わりに「**[!UICONTROL クエリ文字列パラメーター]**」を選択します。 必要なクエリ文字列パラメータ（通常は`q`）をテキストフィールドに入力します。

## データ要素のeVarへのマッピング

[起動データ要素をAnalytics変数](../launch/elements-to-variable.md)にマップするのに従います。 レポートスイート設定で作成したeVarと同じデータを選択していることを確認します。

## 展開プロセスの開始の開始

[開発環境](../launch/deploy-dev.md)にAnalytics実装を導入するに従います。 開発環境での作業を確認したら、[開発実装の検証と実稼動環境への発行](../launch/validate-publish-prod.md)を行うことができます。

## Workspaceでのレポート

導入にデータ収集の時間を与えると、Analysis Workspaceでディメンションを使用して開始できます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 自動的にAdobe Analyticsにログインしない場合は、右上の9-gridアイコンをクリックし、「**[!UICONTROL Analytics]**」を選択します。
3. 「**[!UICONTROL ワークスペース]**」タブをクリックし、新しいプロジェクトを作成します。
4. Dimensionの下で作成したeVarの名前を見つけ、ワークスペースキャンバスにドラッグします。
