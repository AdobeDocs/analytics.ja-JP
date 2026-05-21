---
description: Activity Map拡張機能とそのインターフェイスのナビゲーション方法について説明します。
title: Activity Map拡張機能インターフェイス
uuid: f6734b60-0b77-4f50-a45a-6a6936d1524e
feature: Activity Map
role: User, Admin
exl-id: 461abda1-3238-4a32-b9d3-5a57b00cf0d3
TQID: https://experienceleague.adobe.com/d62-fefaDOC5lOHBnGKgrTzD4euEMcnMlBArhi8RfMc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 2%

---

# Activity Map拡張機能インターフェイス

Activity Mapの拡張機能を使用すると、web サイト上に重ねられたクリックデータを表示できます。 拡張機能をダウンロードするには、次のページに移動します。このページには、web ストアへのリンクが表示されます。

**[!UICONTROL ツール]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map をダウンロード]**

インストールして有効にすると、インターフェイスはいくつかの部分で構成されます。

* 拡張機能とレポートを設定できる上部パネル
* 一番人気のあるリンクを表示するオーバーレイ
* 最も人気のあるリンクの指標を表示する下部パネル

## トップパネル

上部パネルには、Activity Map オーバーレイの基本的なコントロールが含まれています。

![&#x200B; オーバーレイ &#x200B;](../assets/overlay.png)

次の設定が用意されています。

* **標準/ライブビュー**：標準ビューとライブビューを切り替えます。
   * 標準ビュー：履歴データに基づいてオーバーレイを表示します。
   * ライブビュー：ライブデータに基づいてオーバーレイを表示します。 日付セレクターは、ライブデータの精度を変更できるドロップダウンメニューに変わります。
* **指標セレクター**: オーバーレイがレポートする指標を変更できます。 ライブビューを選択している場合は、[!UICONTROL &#x200B; リンククリック &#x200B;]のみが使用できます。
* **セグメントセレクター**: [&#x200B; セグメント &#x200B;](/help/components/segmentation/seg-overview.md)を選択し、オーバーレイ内のデータのサブセットを表示できます。 セグメントはライブビューでは使用できません。
* **オーバーレイ ビジュアライゼーションの種類**: オーバーレイでリンクのランキングを表示する方法を変更できます。
   * **[!UICONTROL バブル]**：上位リンクには、レポート期間中の数値ランクを示す緑のバブルが表示されます。 バブルの色は[設定](settings.md)で変更できます。
   * **[!UICONTROL グラデーション]**：上のリンクが透明な赤で網掛けされて表示されます。 最も人気のあるリンクは最も暗い赤です。 グラデーションカラーは、[設定](settings.md)で変更できます。
   * **[!UICONTROL オフ]**: リンクオーバーレイを無効にします。
* **日付セレクター**: レポート期間を変更できます。

このパネルのヘッダーには、次の設定が含まれます。

* **トップパネルを展開/折りたたむ**：トップパネルを切り替えて、設定を水平方向または垂直方向（二重矢印アイコン）に表示します。
* **[!UICONTROL ページの詳細を切り替え]**：下部パネル（目のアイコン）の表示と非表示を切り替えます。
* **[!UICONTROL 設定を表示]**：変更できる設定（歯車アイコン）のメニューを開きます：
   * **[!UICONTROL 設定]**：拡張機能の[設定](settings.md)を開きます。
   * **[!UICONTROL ヘルプ]**: Experience Leagueへのドキュメントを開きます（このページ）。
   * **[!UICONTROL Adobe コミュニティ]**: [Experience League コミュニティ &#x200B;](https://experienceleaguecommunities.adobe.com/?profile.language=ja)を開きます。
   * **[!UICONTROL バージョン情報]**：拡張機能のバージョンを表示します。
   * **[!UICONTROL ログアウト]**：拡張機能からログアウトするため、再度ログインする必要があります。
* **[!UICONTROL Activity Mapを終了]**：拡張機能（X アイコン）のすべてのオーバーレイを閉じます。

## ページオーバーレイ

ページオーバーレイには、レポート期間中にクリックされた最も人気のあるリンクの場所を示すオーバーレイ付きのサイトコンテンツが含まれます。 これらのリンクオーバーレイを、上部パネルの&#x200B;**[!UICONTROL オーバーレイビジュアライゼーションタイプ]**&#x200B;でバブルまたはグラデーションとして表示するように設定できます。

バブルまたはグラデーションをクリックすると、その特定のリンクの詳細を表示できます。

![&#x200B; バブルをリンク &#x200B;](../assets/link-bubble.png)

## 下部パネル

下部のパネルには、オーバーレイに表示されるリンクの集計表示が表示されます。

* **レポートタイプ**：一番下のパネルを切り替えて、**[!UICONTROL ページのリンク]** レポートまたは&#x200B;**[!UICONTROL ページの詳細]** レポートを表示します。
* **[!UICONTROL ページ名]**：現在の[&#x200B; ページ &#x200B;](/help/components/dimensions/page.md) ディメンション名。
* **[!UICONTROL 検索]**：入力したテキストに一致するリンク名のみを表示するようにレポートをフィルター処理します。
* **[!UICONTROL ダウンロード]**: レポートをCSVに書き出します。 [!UICONTROL &#x200B; ページのリンク &#x200B;] レポート、[!UICONTROL &#x200B; ページ &#x200B;] レポート、および[!UICONTROL &#x200B; ページフロー] レポートを同じダウンロードファイルに含めることができます。
* **[!UICONTROL レポートのドッキング位置を変更]**：このパネルの位置をブラウザーウィンドウの下部または上部に表示するように切り替えます。
* **[!UICONTROL レポートを閉じる]**：このパネルを閉じます。 上部パネル（目のアイコン）の「**[!UICONTROL ページの詳細を切り替え]**」ボタンを使用して、パネルを再度開くことができます。

**[!UICONTROL ページ上のリンク]** レポートには、次の設定を含む基本的なワークスペースレポートが表示されます。

* [Activity Map リンク &#x200B;](/help/components/dimensions/activity-map-link.md) ディメンション
* [発生回数](/help/components/metrics/occurrences.md)指標（**[!UICONTROL リンククリック]**&#x200B;というラベル付き）
* セグメントとして適用された現在の[&#x200B; ページ &#x200B;](/help/components/dimensions/page.md)値

![&#x200B; ページパネル上のリンク &#x200B;](../assets/links-on-page.png)

**[!UICONTROL ページの詳細]** レポートには、[&#x200B; ページ &#x200B;](/help/components/dimensions/page.md) ディメンションを使用して、現在のページに焦点を当てた[&#x200B; フロー](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)のビジュアライゼーションが表示されます。 現在のページの次の指標が左側に表示されます。

* 合計[&#x200B; ページビュー](/help/components/metrics/page-views.md)
* すべてのページビューの[!UICONTROL %]
* [&#x200B; エントリ &#x200B;](/help/components/metrics/entries.md)件
* [終了](/help/components/metrics/exits.md) カウント
* [直帰数](/help/components/metrics/single-page-visits.md)
* [!UICONTROL 平均クリック数]
* 平均[&#x200B; ページに費やした時間](/help/components/metrics/time-spent.md)
* [再読み込み回数](/help/components/metrics/reloads.md)
* [バウンス率](/help/components/metrics/bounce-rate.md)
* [!UICONTROL &#x200B; リンククリック &#x200B;]

![ページの詳細](../assets/page-details.png)
