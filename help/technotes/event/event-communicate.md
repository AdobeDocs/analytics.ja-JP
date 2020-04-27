---
title: ユーザーへの影響の伝達
description: 組織内でのイベントの影響を効果的に伝える方法。
translation-type: tm+mt
source-git-commit: ddf1d9593881e11d40fd872217ad83fa48a0d3c3

---


# ユーザーへの影響の伝達

イベントの影響を受け [たデータがある場合](../event-impacted.md)、組織内のユーザーにそのイベントを伝えることが重要です。

* 一貫性を保つために通信で使用できる一般的な免責事項を作成する
* イベント中およびその後、Analyticsユーザーと主要関係者に継続的な連絡を提供
* 次の月や年など、以降のマイルストーンに対するカレンダーリマインダーを配置します。 今後、このコミュニケーションを行うと、月々レポートや年次レポートでの影響をユーザーに通知するのに役立ちます。

Adobe Analytics内で、以下の節では、組織内のユーザーと通信する様々な方法を示します。 電子メールなど、Adobe Analytics以外の他の方法を使用して、ユーザーとの通信を行うこともできます。

## パネルまたはビジュアライゼーションの説明を通じて通信する

Workspaceプロジェクトを組織内のユーザー間で共有している場合、パネルやビジュアライゼーションの説明を通じてイベントの影響を伝えることができます。 パネルまたはビジュアライゼーションヘッダーを右クリックし、を選択しま **[!UICONTROL Edit description]**&#x200B;す。

![パネルの説明](../assets/panel_description.png)

## テキストのビジュアライゼーションを通じた通信

また、専用のテキストビジュアライゼーションを通じて、イベントの影響を伝えることもできます。 See [Text visualizations](/help/analyze/analysis-workspace/visualizations/text.md) in the Analyze user guide.

![テキストの視覚化](../assets/text_visualization.png)

## Workspaceのトレン追加ドに対するカスタムカレンダーイベント

Workspaceの任意のトレンドビジュアライゼーションに対して、影響を受けた日付範囲を表すシリーズを追加できます。

1. 「影響を受ける日」セグメントを使用して計算指標を作成します。作成するには、「 [分析内の特定の日付を除外](/help/components/c-segmentation/use-cases/exclude-date-range.md)」
1. 計追加算指標キャンバスに対する目的の指標。

   ![指標](../assets/calcmetric_event.png)

1. ユー追加ザーに影響を知らせるタイトルと説明。 必要に応じて、この指標にカレンダー注釈のタグを付けることもできます。

   ![タイトルと説明](../assets/calcmetric_title_description.png)

1. フリーフォームテーブルで、「日」ディメンションを追加します。 「訪追加問回数」と、列を並べて表示した計算指標。

   ![フリーフォームテーブル](../assets/calcmetric_freeform.png)

1. 計算指標の列設定の歯車アイコンをクリックし、有効にしま **[!UICONTROL Interpret zero as no value]**&#x200B;す。

   ![計算指標の設定](../assets/calcmetric_zero_no_value.png)

1. 線のビ追加ジュアライゼーション。 影響を受ける日は、異なる色で表示されます。 詳細については、計算指標の「情報」アイコンをクリックすることもできます。

   ![情報アイコン](../assets/calcmetric_infoicon.png)

## Reports &amp; Analyticsでのカレンダーイベントの使用

Reports &amp; Analyticsを使用する場合、カレンダーイベントを使用して [](/help/components/t-calendar-event.md) 、任意のトレンドレポートで影響を受ける日を強調表示できます。 このメソッドは、Workspaceには適用されません。分析ワークスペース

1. /に移動 **[!UICONTROL Components]** します **[!UICONTROL Calendar events]**。
2. 目的のタイトル、日付範囲、メモのテキストを入力します。
3. クリック **[!UICONTROL Save]**.

![カレンダーイベント](../assets/exclude_calendar_event.png)
