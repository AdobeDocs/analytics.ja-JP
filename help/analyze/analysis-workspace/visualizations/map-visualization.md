---
description: Workspace プロジェクトでマップのビジュアライゼーションを使用します。
title: マップ
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: e0d14f6dd7be438f3dad979abcfc279e710873e7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 58%

---

# マップ {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="マップ"
>abstract="このビジュアライゼーションでは、指標をマップにオーバーレイして表示します。 このビジュアライゼーションは、様々な地域のデータを識別する際に役立ちます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="バブル"
>abstract="バブルを使用してイベントをプロットします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="ヒートマップ"
>abstract="ヒートマップを使用したイベントのプロット。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)![4}Adobe Analytics **でのマップビジュアライゼーションについて説明します。_**_<br/>_で利用できるマップビジュアライゼーションは現在ありません_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**。_

>[!ENDSHADEBOX]



Analysis Workspaceの ![ グローブ ](/help/assets/icons/Globe.svg) **[!UICONTROL マップ]** ビジュアライゼーション

* を使用すると、任意の指標（計算指標を含む）の視覚的なマップを作成できます。
* は、様々な地域をまたいだ指標データを識別および比較する場合に役立ちます。
* モバイルでの使用に基づく緯度/経度、または web での使用に基づく地理的ディメンションの 2 つのデータソースをサポート可能
* は、PDFの書き出しをサポートします。
* は、グラフィックス表示に WebGL を使用します。 グラフィックドライバーが WebGL レンダリングをサポートしない場合、ドライバーを更新する必要がある可能性があります。


>[!BEGINSHADEBOX]

デモビデオについては、![Analysis Workspaceでの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ マップビジュアライゼーション ](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## 使用

1. ![Map](/help/assets/icons/Globe.svg) [!UICONTROL Map] ビジュアライゼーションを追加します。 [ パネルへのビジュアライゼーションの追加 ](freeform-analysis-visualizations.md#add-visualizations-to-a-panel) を参照してください。 マップのビジュアライゼーションは、フリーフォームテーブルの上にのみドラッグできます。

   ![ マップ設定 ](assets/map-configuration.png){width="50%"}

1. ドロップダウンリストから指標を選択します。 または、指標（計算指標を含む）のリストから指標をドラッグします。
1. 描画元のデータソースを指定します。 このダイアログは、モバイルアプリデータの位置追跡が有効になっている場合にのみ表示されます。

   | ソース | 説明 |
   | --- | --- |
   | **[!UICONTROL モバイルの緯度／経度]** | このオプションは、モバイルアプリデータを表します。このオプションが表示されるのは、 [!UICONTROL Analytics]／[!UICONTROL 管理者]／[!UICONTROL レポートスイート]／（レポートスイートを選択）／[!UICONTROL 設定を編集]／[!UICONTROL モバイル管理]／[!UICONTROL 位置追跡を有効にする] で、レポートスイートに対して有効にした場合のみです。これがデフォルトの設定です（位置追跡が有効な場合）。 |
   | **[!UICONTROL 地理的ディメンション]** | このオプションは、訪問者の IP アドレスに基づいた訪問者の場所に関する地理セグメンテーションデータを表します。このデータは、 [!UICONTROL 国]、 [!UICONTROL 地域] および [!UICONTROL 市区町村] に変換されます。DMA または郵便番号レベルには変換されません。このディメンションは、ほぼすべてのレポートスイートで有効になっています。有効になっていない場合は、アドビカスタマーケアに連絡して、地域レポートを有効にしてもらってください。 |

1. 「**[!UICONTROL 作成]**」を選択します。

   泡のあるワールド マップ ビジュアライゼーションが生成されます。

   ![](assets/bubble-world-view.png)

1. 次が可能になりました。

   * マップをダブルクリックするか、スクロールホイールを使用して、このマップを&#x200B;**ズーム**&#x200B;し、特定の領域を拡大します。マウスポインターのある場所に従って、マップがズームします。ズーム操作の間、ズームレベルに基づいて必要なディメンション（国／都道府県／市区町村）が自動的に更新されます。
   * 同じプロジェクトの 2 つ以上のマップのビジュアライゼーションを横に並べて **比較** します。
   * **対前年比などの前期比を表示します**。

      * 例えば、前年比指標のグラフを表示するときに、ニューヨークの上に -33% と表示することができます。
      * タイプ *パーセント* の指標の場合、クラスタリングでは割合が平均されて表示されます。
      * 緑／赤の色スキーム：ポジティブ／ネガティブ

   * [!UICONTROL Ctrl] キーを押しながらマップを動かし、2D または 3D のマップを&#x200B;**回転**&#x200B;します。

   * 後述の[設定](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)を使用して、ヒートマップなど、別の表示に&#x200B;**切り替え**&#x200B;ます。バブル表示がデフォルト設定です。

1. プロジェクトを&#x200B;**保存**&#x200B;して、すべてのマップ設定（座標、ズーム、回転）を保存します。
1. ビジュアライゼーションの下にあるフリーフォームテーブルは、左側のパネルから場所のディメンションと指標をドラッグして入力できます。



## 設定

マップのビジュアライゼーションを再設定するには、「![ 編集 ](/help/assets/icons/Edit.svg)」を選択します。


## 設定

ビジュアライゼーションの設定を定義するには、「![ 設定 ](/help/assets/icons/Setting.svg)」を選択します。

| 設定 | 説明 |
|--- |--- |
| **[!UICONTROL マップの種類]** | |
| [!UICONTROL  バブル ] | バブルを使用してイベントのグラフを描画します。バブルチャートは、散布図と比例する面グラフの中間の複数変数のグラフです。このビューがデフォルトです。 |
| ヒートマップ | ヒートマップを使用してイベントのグラフを描画します。ヒートマップは、データのグラフィカル表示で、マトリックスに含まれる個々の値が色で表されます。 |
| **[!UICONTROL スタイル]** | |
| [!UICONTROL  カラーテーマ ] | ヒートマップおよびバブルのカラースキームを表します。コーラル、赤、緑または青から選択できます。デフォルトは Coral です。 |
| [!UICONTROL  マップ スタイル ] | 「基本」、「通り」、「明るい」、「明るい」、「暗い」、「衛星」から選択できます。 |
| **[!UICONTROL クラスタの半径]** | 指定したピクセル数内にあるデータポイントをグループ化します。デフォルトは 50 です。 |
| **[!UICONTROL カスタムの最大値]** | マップの最大値のしきい値を変更できます。この値を調節すると、カスタム最大値セットに対してバブル／ヒートマップの値（色とサイズ）を調整します。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

