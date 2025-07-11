---
title: 分析内の特定の日付を除外する
description: 日付や日付範囲をレポートに含めない場合に、除外するためのヒントです。
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
feature: Curate and Share, Segmentation
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 2%

---

# 分析内の特定の日付を除外する

データ [ イベントの影響 ](overview.md) がある場合は、セグメントを使用して、レポートに含めない日付範囲を除外できます。 イベントの影響を受ける日付をセグメント化すると、組織が部分的なデータに基づいて決定することを防ぐのに役立ちます。

## 影響を受けた日数を分離 {#isolate}

影響を受ける日付または日付範囲を分離するセグメントを作成します。 このセグメントは、問題発生日のみに焦点を当てて、その影響に関する詳細を確認する場合に役立ちます。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL セグメント]** に移動してセグメントビルダーを開き、「**[!UICONTROL 追加]**」をクリックします。
2. 「日」ディメンションを定義キャンバスにドラッグし、分離する日と等しく設定します。
3. レポートで分離する日ごとに上記の手順を繰り返します。

![ 影響を受ける日数セグメント ](assets/affected_days.jpg)

>[!TIP]
>
>OR ステートメントを AND ステートメントに変更するには、[OR] の横の下向き矢印をクリックし、[AND] を選択します。

Adobeでは、紫色の日付範囲コンポーネントではなく、オレンジ色のディメンションコンポーネントを使用することをお勧めします。 紫色の日付範囲コンポーネントを使用すると、プロジェクトのカレンダー範囲が上書きされます。

![ セグメント日タイプを除外 ](assets/exclude_segment_day_type.jpg)

## 影響を受ける日数を除外 {#exclude}

影響を受ける日付または日付範囲を除外するセグメントを作成します。 このセグメントは、問題が発生した日数を除外して、レポート全体への影響を最小限に抑えたい場合に役立ちます。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL セグメント]** に移動してセグメントビルダーを開き、「**[!UICONTROL 追加]**」をクリックします。
2. セグメント定義キャンバスの右上で、**[!UICONTROL オプション]** > **[!UICONTROL 除外]** をクリックします。
3. 「日」ディメンションを定義キャンバスにドラッグし、削除する日と等しく設定します。
4. レポートから削除する日ごとに上記の手順を繰り返します。

![ 影響を受ける日数を除外 ](assets/exclude_affected_days.jpg)

## レポートでのこれらのセグメントの使用

除外セグメントを作成したら、他のセグメントを使用するときとまったく同じように使用できます。

### トレンドレポートでのセグメントの比較 {#compare}

レポートで「影響を受ける日」セグメントと「影響を受ける日を除外」セグメントの両方を適用して、並べて比較できます。 両方のセグメントを 1 つの指標の上または下にドラッグして、比較します。

![ 両方のセグメント ](assets/affected_and_exclude.png)

テーブルまたはビジュアライゼーションにゼロを表示しない場合（ディップの原因となる）は、列設定の **[!UICONTROL ゼロを値なしで解釈]** を有効にします。

![ ゼロの解釈 ](assets/interpret_zero.png)

テーブルまたはビジュアライゼーションにゼロを表示しない場合（ディップの原因となる）は、列設定の **[!UICONTROL ゼロを値なしで解釈]** を有効にします。

![ ゼロの解釈 ](assets/interpret_zero.png)

### 除外セグメントをプロジェクトに適用する {#apply}

「影響を受ける日を除外」セグメントをWorkspace プロジェクトに適用できます。 除外セグメントを「*セグメントをここにドロップ*」というラベルが付いたWorkspace キャンバスセクションにドラッグします。

>[!TIP]
>
>パネルの説明に、除外されたデータに関するメモを含めて、レポートを表示するのに役立ちます。 パネルのタイトルを右クリックし、「**[!UICONTROL 説明を編集]**」をクリックします。

![ パネルに適用されたセグメント ](assets/exclude_segment_panel.jpg)

### 仮想レポートスイートでの除外セグメントの使用 {#use-vrs}

セグメントを [ 仮想レポートスイート ](/help/components/vrs/vrs-about.md) で使用すると、より便利にデータを除外できます。 このオプションは、影響を受ける日付範囲を含む各レポートにセグメントを適用する必要がないという点で理想的です。 既に仮想レポートスイートをプライマリデータソースとして使用している場合は、既存の仮想レポートスイートにセグメントを追加できます。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL 仮想レポートスイート]** に移動します。
2. 「**[!UICONTROL 追加]**」をクリックします。
3. 仮想レポートスイートの名前と説明を入力します。
4. 除外セグメントを「セグメントを追加 **[!UICONTROL というラベルの付いた領域にドラッグ]** ます。
5. 右上の **[!UICONTROL 続行]** をクリックしてから、「**[!UICONTROL 保存]** をクリックします。

![ 仮想レポートスイートに適用されたセグメント ](assets/exclude_segment_vrs.png)
