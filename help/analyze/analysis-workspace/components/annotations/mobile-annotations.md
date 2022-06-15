---
title: モバイルスコアカード注釈
description: モバイルスコアカードで注釈を表示する方法を説明します。
role: User, Admin
solution: Analytics
feature: Components
exl-id: d8212ab1-d639-41b5-b28e-da580a3628b0
source-git-commit: 43dc28d7c6b4560fd1b8397ce10cc8fbf8f5ca91
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 2%

---


# モバイルスコアカードでの注釈の共有

Workspace で作成された注釈をモバイルスコアカードに表示できます。 これにより、組織とキャンペーンに関するコンテキストデータのニュアンスやインサイトを、Mobile Scorecard プロジェクト内で直接共有でき、Analytics ダッシュボードモバイルアプリで表示できます。

## モバイルスコアカードでのサーフェス注釈

モバイルスコアカードで注釈を表示するには、まず Workspace プロジェクトから、またはコンポーネントメニューから注釈を作成します。

注釈の作成について詳しくは、 [注釈の作成](create-annotations.md). モバイルスコアカードでは、注釈はデフォルトで無効になっており、モバイルスコアカードで表示する各スコアカードに対して有効にする必要があります。

1. 注釈をオンにする。 注釈をオンにするには、 [注釈のオン/オフの切り替え](overview.md#on-off).

1. 注釈を作成し、すべてのプロジェクトで共有されていることを確認します。 Workspace で注釈を作成するには、 [注釈の作成](create-annotations.md).

1. 選択 **注釈を表示** 「モバイルスコアカード」に注釈を表示するには

   <img src="assets/show-annotations.png"  width="80%">

1. 注釈の表示が選択されていることを確認するには、に移動します。 **プロジェクト** > **プロジェクト情報と設定**.

   <img src="assets/project-info-settings.png" width="25%">

## モバイルスコアカードでの注釈の表示

注釈が有効な場合、スコアカードビルダーに注釈アイコンが表示されます。 注釈は、詳細ビューのグラフとテーブルにのみ表示されます。 注釈は、スコアカードのメインタイル表示には表示されません。

<img src="assets/view-annotations.png"  width="80%">

注釈アイコンが表示されている場合、ビルダーキャンバスで注釈を完全に表示したり操作したりすることはできません。 プレビューモードを使用すると、アプリに表示される注釈の表示と操作を行うことができます。 ![](assets/preview-icon.png)

注釈の色は、Workspace で注釈を作成する際に選択します。 グレーの注釈で、複数の注釈が表示されていました。 ![](assets/gray-annotations1.png) ![](assets/gray-annotations2.png)

## グラフの注釈の表示

| 日付 | 外観 |
| --- | --- |
| **1 日** | <img src="assets/single-day-mobile-annotations.png"  width="50%"><br></br> |
| **日付範囲** | <img src="assets/date-range.png"  width="50%"> |
| **重複する注釈** | <img src="assets/overlapping-annotations.png"  width="50%"><br></br>Analytics ダッシュボードアプリで注釈の詳細を表示するには、注釈アイコンをタップします。 <br></br>グラフで注釈を表示している場合は、左右にスワイプして、グラフに存在するすべての注釈に移動できます。 テーブルで注釈を表示している場合は、左右にスワイプして、テーブル内のその行項目に関連付けられているすべての注釈に移動します。 <br></br><img src="assets/swipe-multiple-annotations.png"  width="50%"> <br></br>時間に基づくグラフの場合 *x 軸*&#x200B;ドーナツグラフや横棒グラフなど、グラフに適用される注釈は、右下隅にあるアイコンをタップすると表示できます。<br></br> <img src="assets/charts-without-timebase.png"  width="50%"> |
