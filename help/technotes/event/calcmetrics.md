---
title: イベントの影響を受けたデータの取得
description: 計算指標を使用して、イベントの影響を受けるトレンドデータを修正します。
exl-id: 0fe70c8b-fa07-47e4-b6b3-b55eebad1fef
feature: Curate and Share, Calculated Metrics
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 3%

---

# イベントの影響を受けたデータの取得

データ [ イベントの影響を受ける ](overview.md) がある場合は、計算指標を使用して、イベントの期間について予測値を導き出すことができます。 例えば、データが 25% 低下するイベントがあった場合、それを計算指標の乗数として使用できます。

これらの手順は、セグメント化と日付比較の両方の観点からイベントの影響を理解する場合に最適です。 このページに従う前に、[ イベントの影響を受ける日付を以前の範囲と比較する ](compare-dates.md) および [ 分析で特定の日付を除外する ](segments.md) に従ってください。

>[!NOTE]
>
>このアプローチは、特定の入力セットと日付範囲に基づく予測です。 すべてのユースケースやデータスライスに対する包括的なソリューションではありません。 さらに、このアプローチでは、影響を受ける日付範囲に、計算するヒットが少なくとも 1 つ必要です。

影響を受ける期間の推定計算指標を作成するには：

1. [ 分析の特定の日付の除外 ](segments.md) で説明されているように、「影響を受ける日」と「影響を受ける日を除外」の 2 つのセグメントを作成します。
2. **[!UICONTROL コンポーネント]**/**[!UICONTROL 計算指標]** に移動します。
3. 「**[!UICONTROL 追加]**」をクリックします。
4. 上記の両方のセグメントを定義キャンバスにドラッグします。 それらの間の演算子を `+` に変更して、合計を求めます。
5. 両方のセグメント内に目的の指標を追加します。 例えば、「訪問回数」指標を使用できます。

   ![ セグメントビルダー ](assets/event_segment_builder.png)

6. 「影響を受けた日数 **コンテナの右上にある「** 追加 **[!UICONTROL をクリックし、「静的な数値]** をクリックします。 [ イベントの影響を受ける日付を以前の範囲と比較する ](compare-dates.md) で説明されているように、静的な数値をデータのオフセットに対する割合に設定します。 この例では、オフセットは 25%、つまり 1.25 です。

   ![ 静的な数値 ](assets/event_static_number.png)

7. トレンドのフリーフォームテーブルに「修正済み」指標を並べて適用します。 イベント外のすべての日は通常の指標数を反映し、影響を受けるすべての日は乗数オフセットを使用します。

   ![ 修正された指標 ](assets/event_corrected.png)

8. 折れ線グラフのビジュアライゼーションにデータを表示して、修正された指標の効果を確認します。

   ![ 修正された行 ](assets/event_line.png)
