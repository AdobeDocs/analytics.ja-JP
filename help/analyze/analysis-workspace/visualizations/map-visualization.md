---
description: マップビジュアライゼーションを使用すると、地理的マップビジュアライゼーションにデータをプロットできます
title: マップ
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 97%

---

# マップ {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="マップ"
>abstract="このビジュアライゼーションでは、指標をマップにオーバーレイして表示します。このビジュアライゼーションは、様々な地域にまたがるデータを識別する場合に役立ちます。"

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
>abstract="ヒートマップを使用してイベントをプロットします。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** のマップビジュアライゼーションについて説明します。_<br/>_現在、_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** で使用できるマップビジュアライゼーションはありません。_

>[!ENDSHADEBOX]



Analysis Workspace の ![地球儀](/help/assets/icons/Globe.svg) **[!UICONTROL マップ]**&#x200B;ビジュアライゼーション

* 任意の指標（計算指標を含む）のビジュアルマップを作成できます。
* 様々な地域にまたがる指標データを識別および比較する場合に役立ちます。
* モバイルの使用状況からの緯度／経度または web の使用状況の地理的ディメンションの 2 つのデータソースをサポートできます。
* PDF の書き出しをサポートします。
* グラフィックの表示に WebGL を活用します。お使いのグラフィックドライバーが WebGL レンダリングをサポートしていない場合、ドライバーの更新が必要になる可能性があります。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のマップビジュアライゼーション](https://video.tv.adobe.com/v/41505/?quality=12&captions=jpn){target=&#34;_blank&#34;}を参照してください。

>[!ENDSHADEBOX]


## 使用

1. ![マップ](/help/assets/icons/Globe.svg) [!UICONTROL マップ]ビジュアライゼーションを追加します。[パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。マップビジュアライゼーションは、フリーフォームテーブルの上にのみドラッグできます。

   ![マップ設定](assets/map-configuration.png){width="50%"}

1. ドロップダウンリストから、指標を選択します。または、指標のリスト（計算指標を含む）から指標にドラッグします。
1. 描画するデータソースを指定します。このダイアログは、モバイルアプリデータの場所のトラッキングを有効にしている場合にのみ表示されます。

   | ソース | 説明 |
   | --- | --- |
   | **[!UICONTROL モバイルの緯度／経度]** | このオプションは、モバイルアプリデータを表します。このオプションが表示されるのは、 [!UICONTROL Analytics]／[!UICONTROL 管理者]／[!UICONTROL レポートスイート]／（レポートスイートを選択）／[!UICONTROL 設定を編集]／[!UICONTROL モバイル管理]／[!UICONTROL 位置追跡を有効にする] で、レポートスイートに対して有効にした場合のみです。この設定はデフォルトです（場所のトラッキングが有効な場合）。 |
   | **[!UICONTROL 地理的ディメンション]** | このオプションは、訪問者の IP アドレスに基づいた訪問者の場所に関する地理セグメンテーションデータを表します。このデータは、 [!UICONTROL 国]、 [!UICONTROL 地域] および [!UICONTROL 市区町村] に変換されます。DMA または郵便番号レベルには変換されません。このディメンションは、ほぼすべてのレポートスイートで有効になっています。有効になっていない場合は、アドビカスタマーケアに連絡して、地域レポートを有効にしてもらってください。 |

1. 「**[!UICONTROL 作成]**」を選択します。

   バブルを使用した世界マップビジュアライゼーションが生成されます。

   ![](assets/bubble-world-view.png)

1. 次のことができるようになりました。

   * マップをダブルクリックするか、スクロールホイールを使用して、このマップを&#x200B;**ズーム**&#x200B;し、特定の領域を拡大します。マウスポインターのある場所に従って、マップがズームします。ズーム操作の間、ズームレベルに基づいて必要なディメンション（国／都道府県／市区町村）が自動的に更新されます。
   * 同じプロジェクトの 2 つ以上のマップのビジュアライゼーションを横に並べて **比較** します。
   * **対前年比などの前期比を表示します**。

      * 例えば、前年比指標のグラフを表示するときに、ニューヨークの上に -33% と表示することができます。
      * *パーセント*&#x200B;タイプの指標では、クラスタリングでパーセンテージがまとめて平均化されます。
      * 緑／赤の色スキーム：ポジティブ／ネガティブ

   * [!UICONTROL Ctrl] キーを押しながらマップを動かし、2D または 3D のマップを&#x200B;**回転**&#x200B;します。

   * 後述の[設定](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)を使用して、ヒートマップなど、別の表示に&#x200B;**切り替え**&#x200B;ます。バブル表示がデフォルト設定です。

1. プロジェクトを&#x200B;**保存**&#x200B;して、すべてのマップ設定（座標、ズーム、回転）を保存します。
1. ビジュアライゼーションの下にあるフリーフォームテーブルには、左側のパネルから場所のディメンションと指標をドラッグしてデータを入力できます。



## 設定

マップビジュアライゼーションを再設定するには、「![編集](/help/assets/icons/Edit.svg)」を選択します。


## 設定

ビジュアライゼーションの設定を定義するには、「![設定](/help/assets/icons/Setting.svg)」を選択します。

| 設定 | 説明 |
|--- |--- |
| **[!UICONTROL マップタイプ]** | |
| **[!UICONTROL &#x200B; バブル &#x200B;] | バブルを使用してイベントのグラフを描画します。バブルチャートは、散布図と比例する面グラフの中間の複数変数のグラフです。この表示はデフォルトです。 |
| [!UICONTROL &#x200B; ヒートマップ &#x200B;] | ヒートマップを使用してイベントのグラフを描画します。ヒートマップは、データのグラフィカル表示で、マトリックスに含まれる個々の値が色で表されます。 |
| **[!UICONTROL スタイル]** | |
| [!UICONTROL カラーテーマ] | ヒートマップおよびバブルのカラースキームを表します。コーラル、赤、緑または青から選択できます。デフォルトはコーラルです。 |
| [!UICONTROL マップスタイル] | 「ベーシック」、「ストリート」、「ブライト」、「ライト」、「ダーク」、「サテライト」から選択できます。 |
| **[!UICONTROL クラスター半径]** | 指定したピクセル数内にあるデータポイントをグループ化します。デフォルトは 50 です。 |
| **[!UICONTROL カスタム最大値]** | マップの最大値のしきい値を変更できます。この値を調節すると、カスタム最大値セットに対してバブル／ヒートマップの値（色とサイズ）を調整します。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/35203/?quality=12&captions=jpn)

-->

