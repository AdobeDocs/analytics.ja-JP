---
title: 利用者に影響を伝える
description: 組織内のイベントの影響を伝える効果的な方法について説明します。
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Curate and Share
TQID: https://experienceleague.adobe.com/Ku2Rgll0xTFejohK1gTwbQ6qY8IrneI0i0Ii5Tpycho
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 1%

---

# イベントの影響をユーザーに伝える

イベントの影響を受けるデータ [がある場合は、そのイベントを組織内のユーザーに伝えることが重要です。](overview.md)

* 一貫性を保つためのコミュニケーションで使用できる、共通の免責事項を作成する
* イベント中およびイベント後に、Adobe Analyticsのユーザーと主要な関係者に継続的なコミュニケーションを提供したい
* 次の月や年など、その後のマイルストーンのカレンダーのリマインダーを配置します。 今後のコミュニケーションにより、レポートを閲覧するユーザーに、前月比または前年比レポートでの影響を思い出してもらうことができます。

Adobe Analyticsでは、組織内のユーザーとコミュニケーションを取るための様々な方法を以下のセクションで説明します。 電子メールなど、Adobe Analytics以外の方法を使用して、オーディエンスとコミュニケーションを取ることもできます。

## パネルまたはビジュアライゼーションの説明を通じたコミュニケーション

Workspace プロジェクトを組織内のユーザー間で共有している場合は、パネルまたはビジュアライゼーションの説明を使用して、イベントの影響を伝えることができます。 パネルまたはビジュアライゼーションヘッダーを右クリックし、**[!UICONTROL 説明を編集]**&#x200B;を選択します。

![ パネルの説明](assets/panel_description.png)

## テキストビジュアライゼーションを通じたコミュニケーション

専用のテキストビジュアライゼーションを通じて、イベントの影響を伝えることもできます。 Analyze ユーザーガイドの[ テキストビジュアライゼーション ](/help/analyze/analysis-workspace/visualizations/text.md)を参照してください。

![ テキストビジュアライゼーション ](assets/text_visualization.png)

## Workspaceのトレンドにカスタムカレンダーイベントを追加する

Workspaceでトレンドのビジュアライゼーションを作成する場合は、影響を受ける日付範囲を表すシリーズを追加できます。

1. 次の「影響を受ける日数」セグメントを使用して計算指標を作成します。[分析で特定の日付を除外](segments.md)。
1. 目的の指標を計算指標キャンバスに追加します。

   ![指標](assets/calcmetric_event.png)

1. ユーザーに影響を通知するタイトルと説明を追加します。 必要に応じて、この指標をカレンダー注釈としてタグ付けすることもできます。

   ![タイトルと説明](assets/calcmetric_title_description.png)

1. フリーフォームテーブルに「日」ディメンションを追加します。 「訪問数」と計算指標を列として並べて追加します。

   ![フリーフォームテーブル](assets/calcmetric_freeform.png)

1. 計算指標の列設定の歯車アイコンをクリックし、**[!UICONTROL ゼロを値なしとして解釈]**&#x200B;を有効にします。

   ![計算指標の設定](assets/calcmetric_zero_no_value.png)

1. 線のビジュアライゼーションを追加します。 影響を受ける日は異なる色で表されます。 ユーザーは、計算指標の「情報」アイコンをクリックして詳細を確認することもできます。

   ![情報アイコン ](assets/calcmetric_infoicon.png)

