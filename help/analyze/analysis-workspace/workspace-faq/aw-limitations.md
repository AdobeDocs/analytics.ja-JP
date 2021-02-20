---
description: Adobe Analysis Workspace とその関連コンポーネントに関する既知の制限のリスト
title: Analysis Workspace の既知の制限
translation-type: tm+mt
source-git-commit: 00f36d8583ec9224337404cfd7fa020502d89c2d
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 100%

---


# Analysis Workspace の既知の制限

以下に、Analysis Workspace とその関連コンポーネントに関する既知の制限を示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合は、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、「選択から指標を作成」が無効になります。また、「選択から指標を作成」は、日付順の列には適用しないでください。
* 分類行の条件付き書式では、カスタム範囲を使用することはできません。
* 行の値を合計して合計を計算する設定が適用されている場合は、テーブルの合計行をトレンド表示できません（通常は静的な行項目で使用されます）。
* [!UICONTROL 貢献度分析]は、[!UICONTROL 毎日]の精度でのみ&#x200B;_実行_&#x200B;できます。[!UICONTROL 時間別]、[!UICONTROL 週別]などのデータに対して実行することはできません。

## ビジュアライゼーション

* セグメント化（[!UICONTROL フォールアウト]、[!UICONTROL フロー]、[!UICONTROL コホート]、[!UICONTROL ヒストグラム]など）を利用するビジュアライゼーションでは、計算指標を入力として使用することはできません。
* [!UICONTROL フロー]：入口／出口ディメンション（例：[!UICONTROL 入口ページ]）は、フローでは使用できません。
* [!UICONTROL コホート]：整数以外の値をコホート条件として使用することはできません。

## パネル

* セグメント比較：最初のドロップゾーンでセグメントテンプレートが使用されている場合、[!UICONTROL 他の全員]セグメントは作成されません。

## コンポーネント／セグメント

* 指標やディメンションには、セグメント化できないものがあります（[!UICONTROL 回数]、[!UICONTROL 個別訪問者数]など）。
* [パネルのドロップゾーン](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja-JP)で作成されたアドホックセグメントは、公開されない限り、Workspace の左パネルまたはセグメントコンポーネントマネージャーに表示されません。これは、セグメントを編集し、「**[!UICONTROL このセグメントを公開する]**」を選択することで実行できます。

## コンポーネント／計算指標

* 計算指標は、一部のビジュアライゼーションでは使用できません。上記の「ビジュアライゼーション」を参照してください。
* 計算指標自体に別々のアトリビューションモデルを含めることができるので、[!UICONTROL アトリビューションパネル]で計算指標を使用することはできません。
* 計算指標が Workspace から作成される場合（[!UICONTROL コンポーネント／セグメント]から作成される場合とは異なり）、使用できないコンポーネントや演算子があります。例：[!UICONTROL IP アドレス]。

## コンポーネント／日付範囲

* カスタム日付範囲では、[!UICONTROL 昨年の今日]、[!UICONTROL 先月の今日]などはサポートされません。

## コンポーネント／仮想レポートスイート

* レポート時間処理が有効な場合、一部のコンポーネントはサポートされません。完全なリストについては、[レポート時間処理](/help/components/vrs/vrs-report-time-processing.md)を参照してください。

## コンポーネント／レポート設定

* 「[!UICONTROL レポート設定]」ページの一部の設定は適用されません。Analysis Workspace では、一番下の「[!UICONTROL 言語 / 通貨 / エンコード]」設定（[!UICONTROL 千単位区切り文字]、[!UICONTROL 予定レポートのエンコード]、[!UICONTROL CSV 区切り文字]）のみが使用されます。

## Attribution IQ

* 指標のサブセットは、[!UICONTROL Attribution IQ] ではサポートされません。完全なリストについては、[Attribution IQ に関する FAQ](../attribution/faq.md) を参照してください。
