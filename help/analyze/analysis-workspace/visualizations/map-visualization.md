---
description: マップ ビジュアライゼーションを使用して、地理マップ ビジュアライゼーションにデータをプロットします。
title: マップ
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
TQID: https://experienceleague.adobe.com/x5ln-HzjHf2kK-mmCJxoLHxbkzox7BpN2i-G5-oAsc8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 727
ht-degree: 60%

---

# マップ {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="マップ"
>abstract="このビジュアライゼーションでは、指標をマップにオーバーレイして表示します。 このビジュアライゼーションは、様々な地域にまたがるデータを識別する場合に役立ちます。"

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

_この記事では、この記事の_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**_<br/>_のマップビジュアライゼーションについて説明します。_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版の[Map](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/map)を参照してください。_

>[!ENDSHADEBOX]



Analysis Workspace の ![地球儀](/help/assets/icons/Globe.svg) **[!UICONTROL マップ]**&#x200B;ビジュアライゼーション

* 任意の指標（計算指標を含む）のビジュアルマップを作成できます。
* 様々な地域にまたがる指標データを識別および比較する場合に役立ちます。
* モバイルの使用状況からの緯度／経度または web の使用状況の地理的ディメンションの 2 つのデータソースをサポートできます。
* PDF の書き出しをサポートします。
* グラフィックの表示に WebGL を活用します。 お使いのグラフィックドライバーが WebGL レンダリングをサポートしていない場合、ドライバーの更新が必要になる可能性があります。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のマップビジュアライゼーション](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/map-visualization){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 使用

1. ![マップ](/help/assets/icons/Globe.svg) [!UICONTROL マップ]ビジュアライゼーションを追加します。 [パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。 マップビジュアライゼーションは、フリーフォームテーブルの上にのみドラッグできます。

   ![マップ設定](assets/map-configuration.png){width="50%"}

1. ドロップダウンリストから、指標を選択します。 または、指標のリスト（計算指標を含む）から指標にドラッグします。
1. 描画するデータソースを指定します。 このダイアログは、モバイルアプリデータの場所のトラッキングを有効にしている場合にのみ表示されます。

   | ソース | 説明 |
   | --- | --- |
   | **[!UICONTROL モバイルの緯度／経度]** | このオプションは、モバイルアプリデータを表します。 このオプションが表示されるのは、 [!UICONTROL Analytics]／[!UICONTROL 管理者]／[!UICONTROL レポートスイート]／（レポートスイートを選択）／[!UICONTROL 設定を編集]／[!UICONTROL モバイル管理]／[!UICONTROL 位置追跡を有効にする] で、レポートスイートに対して有効にした場合のみです。 この設定はデフォルトです（場所のトラッキングが有効な場合）。 |
   | **[!UICONTROL 地理的ディメンション]** | このオプションは、訪問者の IP アドレスに基づいた訪問者の場所に関する地理セグメンテーションデータを表します。 このデータは、 [!UICONTROL 国]、 [!UICONTROL 地域] および [!UICONTROL 市区町村] に変換されます。 DMA または郵便番号レベルには変換されません。 ほとんどすべてのレポートスイートで、このディメンションが有効になっています。 お客様が使用していない場合は、Adobe カスタマーケアに連絡して、地理的レポートを有効にしてもらいます。 |

1. 「**[!UICONTROL 作成]**」を選択します。

   バブルを使用した世界マップビジュアライゼーションが生成されます。

   ![](assets/bubble-world-view.png)

1. 次のことができるようになりました。

   * このマップに&#x200B;**ズーム**&#x200B;して、マップをダブルクリックするか、スクロールホイールを使用して特定の領域を拡大します。 マップは、カーソルを配置した場所に応じてズームされます。 ズームインタラクションを使用すると、ズームレベルに基づいて、必要なディメンション（国/州/都市）が自動的に更新されます。
   * 同じプロジェクトの 2 つ以上のマップのビジュアライゼーションを横に並べて **比較** します。
   * **期間ごとの比較（前年比など）を表示**:

      * 負の数値を表示：例えば、前年比指標をプロットする場合、マップはニューヨークよりも–33%表示されます。
      * *パーセント*&#x200B;タイプの指標では、クラスタリングでパーセンテージがまとめて平均化されます。
      * 緑/赤の配色：肯定的/否定的

   * **Ctrl] キーを押しながらマップを移動すると、マップを2Dまたは3Dで**&#x200B;回転できます。[!UICONTROL 

   * **以下に説明する[設定](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)を使用して、ヒートマップなどの別のビューに**&#x200B;切り替えます。 バブル表示がデフォルト設定であることに注意してください。

1. **すべてのマップ設定（座標、ズーム、回転）を保存するプロジェクトを**&#x200B;保存します。
1. ビジュアライゼーションの下にあるフリーフォームテーブルには、左側のパネルから場所のディメンションと指標をドラッグしてデータを入力できます。



## 設定

マップビジュアライゼーションを再設定するには、「![編集](/help/assets/icons/Edit.svg)」を選択します。


## 設定

ビジュアライゼーションの設定を定義するには、「![設定](/help/assets/icons/Setting.svg)」を選択します。

| 設定 | 説明 |
|--- |--- |
| **[!UICONTROL マップタイプ]** | |
| **[!UICONTROL 吹き出し] | バブルを使用してイベントをプロットします。 バブルチャートとは、散布図とプロポーショナルエリアチャートの間のクロス図である多変数グラフです。 この表示はデフォルトです。 |
| [!UICONTROL  ヒートマップ ] | ヒートマップを使用してイベントをプロットします。 ヒートマップとは、マトリックスに含まれる個々の値が色で表されるデータのグラフィック表現です。 |
| **[!UICONTROL スタイル]** | |
| [!UICONTROL カラーテーマ] | ヒートマップと泡のカラースキームを表示します。 Coral、Reds、Greens、Bluesから選択できます。 デフォルトはコーラルです。 |
| [!UICONTROL マップスタイル] | 「ベーシック」、「ストリート」、「ブライト」、「ライト」、「ダーク」、「サテライト」から選択できます。 |
| **[!UICONTROL クラスター半径]** | 指定したピクセル数内にあるデータポイントをグループ化します。 デフォルトは 50 です。 |
| **[!UICONTROL カスタム最大値]** | マップの最大値のしきい値を変更できます。この値を調節すると、カスタム最大値セットに対してバブル／ヒートマップの値（色とサイズ）を調整します。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/build-a-time-parting-heatmap)

-->

