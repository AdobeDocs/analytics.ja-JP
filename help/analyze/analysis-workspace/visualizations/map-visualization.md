---
description: マップビジュアライゼーションを使用すると、地理的なマップビジュアライゼーションにデータをプロットできます。
title: マップ
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 64%

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

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** のマップビジュアライゼーションについて説明します。_<br/>_この記事の [](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/map) CustomerJourneyAnalytics_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) 版については、_**Map** を参照してください。_

>[!ENDSHADEBOX]



Analysis Workspace の ![地球儀](/help/assets/icons/Globe.svg) **[!UICONTROL マップ]**&#x200B;ビジュアライゼーション

* 任意の指標（計算指標を含む）のビジュアルマップを作成できます。
* 様々な地域にまたがる指標データを識別および比較する場合に役立ちます。
* モバイルの使用状況からの緯度／経度または web の使用状況の地理的ディメンションの 2 つのデータソースをサポートできます。
* PDF の書き出しをサポートします。
* グラフィックの表示に WebGL を活用します。お使いのグラフィックドライバーが WebGL レンダリングをサポートしていない場合、ドライバーの更新が必要になる可能性があります。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のマップビジュアライゼーション](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/map-visualization){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 使用

1. ![マップ](/help/assets/icons/Globe.svg) [!UICONTROL マップ]ビジュアライゼーションを追加します。[パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。マップビジュアライゼーションは、フリーフォームテーブルの上にのみドラッグできます。

   ![マップ設定](assets/map-configuration.png){width="50%"}

1. ドロップダウンリストから、指標を選択します。または、指標のリスト（計算指標を含む）から指標にドラッグします。
1. 描画するデータソースを指定します。このダイアログは、モバイルアプリデータの場所のトラッキングを有効にしている場合にのみ表示されます。

   | ソース | 説明 |
   | --- | --- |
   | **[!UICONTROL モバイルの緯度／経度]** | このオプションは、モバイルアプリデータを表します。このオプションが表示されるのは、 [!UICONTROL Analytics]／[!UICONTROL 管理者]／[!UICONTROL レポートスイート]／（レポートスイートを選択）／[!UICONTROL 設定を編集]／[!UICONTROL モバイル管理]／[!UICONTROL 位置追跡を有効にする] で、レポートスイートに対して有効にした場合のみです。この設定はデフォルトです（場所のトラッキングが有効な場合）。 |
   | **[!UICONTROL 地理的ディメンション]** | このオプションは、訪問者の IP アドレスに基づいた訪問者の場所に関する地理セグメンテーションデータを表します。このデータは、 [!UICONTROL 国]、 [!UICONTROL 地域] および [!UICONTROL 市区町村] に変換されます。DMA または郵便番号レベルには変換されません。ほとんどのレポートスイートでは、このディメンションが有効になっています。 まだ承認されていない場合は、Adobe カスタマーケアに連絡して、地理レポートを有効にしてもらってください。 |

1. 「**[!UICONTROL 作成]**」を選択します。

   バブルを使用した世界マップビジュアライゼーションが生成されます。

   ![](assets/bubble-world-view.png)

1. 次のことができるようになりました。

   * このマップを **ズーム** して、マップをダブルクリックするか、スクロール ホイールを使用して、特定の領域を拡大します。 カーソルを置いた場所に応じて、マップがズームされます。 ズーム操作により、必要なディメンション（国/州/市区町村）がズームレベルに基づいて自動的に更新されます。
   * 同じプロジェクトの 2 つ以上のマップのビジュアライゼーションを横に並べて **比較** します。
   * **期間ごとの比較（前年比など）を表示**:

      * 負の数を表示する：例えば、前年比の指標をプロットする場合、マップはニューヨークで–33% と表示できます。
      * *パーセント*&#x200B;タイプの指標では、クラスタリングでパーセンテージがまとめて平均化されます。
      * 緑/赤のカラースキーム：ポジティブ/ネガティブ

   * **回転**[!UICONTROL Ctrl] キーを押しながらマップを移動して、2D または 3D でマップを回転します。

   * 以下に説明する **設定** を使用して、ヒートマップなどの別のビューに [ 切り替え ](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) ます。 既定の設定は、通り名記号ビューです。

1. **保存** すべてのマップ設定（座標、ズーム、回転）を保存するプロジェクトです。
1. ビジュアライゼーションの下にあるフリーフォームテーブルには、左側のパネルから場所のディメンションと指標をドラッグしてデータを入力できます。



## 設定

マップビジュアライゼーションを再設定するには、「![編集](/help/assets/icons/Edit.svg)」を選択します。


## 設定

ビジュアライゼーションの設定を定義するには、「![設定](/help/assets/icons/Setting.svg)」を選択します。

| 設定 | 説明 |
|--- |--- |
| **[!UICONTROL マップタイプ]** | |
| **[!UICONTROL  バブル ] | バブルを使用してイベントをプロットします。 バブル チャートは、散布図と比例面グラフの間のクロスである多変数グラフです。 この表示はデフォルトです。 |
| [!UICONTROL  ヒートマップ ] | ヒートマップを使用してイベントをプロットします。 ヒートマップは、マトリックスに含まれる個々の値が色で表される、データのグラフィカルな表現です。 |
| **[!UICONTROL スタイル]** | |
| [!UICONTROL カラーテーマ] | ヒートマップと気泡のカラースキームを表示します。 あなたはサンゴ、レッズ、緑またはブルースの中から選ぶことができます。 デフォルトはコーラルです。 |
| [!UICONTROL マップスタイル] | 「ベーシック」、「ストリート」、「ブライト」、「ライト」、「ダーク」、「サテライト」から選択できます。 |
| **[!UICONTROL クラスター半径]** | 指定したピクセル数内にあるデータポイントをグループ化します。デフォルトは 50 です。 |
| **[!UICONTROL カスタム最大値]** | マップの最大値のしきい値を変更できます。この値を調節すると、カスタム最大値セットに対してバブル／ヒートマップの値（色とサイズ）を調整します。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/build-a-time-parting-heatmap)

-->

