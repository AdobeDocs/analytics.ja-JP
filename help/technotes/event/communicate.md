---
title: ユーザーへの影響の伝達
description: 組織内のイベントの影響を効果的に伝える方法を学びます。
translation-type: tm+mt
source-git-commit: 022d9cbfdae11d7efe1efb7fe503f4fdaa785be1

---


# イベントへの影響をユーザーに伝える

イベントの [影響を受けるデータがある場合は](overview.md)、そのイベントを組織内のユーザーに伝えることが重要です。

* 一貫性を保つために、通信で使用できる一般的な免責事項を作成する
* イベント中およびその後も、Analyticsのユーザーと主な関係者に継続的に連絡を取る
* 次の月や年など、以降のマイルストーンに対してカレンダーリマインダーを設定します。 将来的には、このコミュニケーションにより、前月比または前年比のレポートでの影響をユーザーに示すことができます。

Adobe Analytics内で、以下の各節で、組織内のユーザーと通信する様々な方法を示します。 電子メールなど、Adobe Analytics以外の他の方法を使用して、ユーザーと通信することもできます。

## パネルまたはビジュアライゼーションの説明を通じて通信する

組織内のユーザー間でWorkspaceプロジェクトを共有している場合、パネルまたはビジュアライゼーションの説明を通じて、イベントの影響を伝えることができます。 パネルまたはビジュアライゼーションのヘッダーを右クリックし、選択し **[!UICONTROL Edit description]**&#x200B;ます。

![パネルの説明](assets/panel_description.png)

## テキストのビジュアライゼーションを通じた通信

また、専用のテキストビジュアライゼーションを通じて、イベントの影響を伝えることもできます。 See [Text visualizations](/help/analyze/analysis-workspace/visualizations/text.md) in the Analyze user guide.

![テキストの視覚化](assets/text_visualization.png)

## Workspaceのトレンドに対する追加カスタムカレンダーイベント

Workspaceの任意のトレンドビジュアライゼーションに対して、影響を受けた日付範囲を表すシリーズを追加できます。

1. 「分析内の特定の日付を [除外する」に従って、「影響を受ける日」セグメントを使用して計算指標を作成します](segments.md)。
1. 計算指標キャンバス追加に表示する指標です。

   ![指標](assets/calcmetric_event.png)

1. ユ追加ーザーに影響を知らせるタイトルと説明です。 必要に応じて、この指標にカレンダー注釈のタグを付けることもできます。

   ![タイトルと説明](assets/calcmetric_title_description.png)

1. フリーフォームテーブルに、「日」ディメンションを追加します。 「追加訪問回数」と計算指標を列として並べて表示します。

   ![フリーフォームテーブル](assets/calcmetric_freeform.png)

1. 計算指標の列設定の歯車アイコンをクリックし、有効にし **[!UICONTROL Interpret zero as no value]**&#x200B;ます。

   ![計算指標の設定](assets/calcmetric_zero_no_value.png)

1. 線追加のビジュアライゼーション。 影響を受ける日は、異なる色で表されます。 詳細については、計算指標の「情報」アイコンをクリックすることもできます。

   ![情報アイコン](assets/calcmetric_infoicon.png)

## Reports &amp; Analyticsでのカレンダーイベントの使用

Reports &amp; Analyticsを使用する場合は、 [カレンダーイベント](/help/components/t-calendar-event.md) を使用して、任意のトレンドレポートで影響を受ける日を強調表示できます。 このメソッドは、分析ワークスペースには適用されません。

1. /に移動し **[!UICONTROL Components]** ま **[!UICONTROL Calendar events]**&#x200B;す。
2. 目的のタイトル、日付範囲、メモのテキストを入力します。
3. クリック **[!UICONTROL Save]**.

![カレンダーイベント](assets/exclude_calendar_event.png)
