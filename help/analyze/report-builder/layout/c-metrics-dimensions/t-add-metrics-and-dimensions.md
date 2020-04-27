---
description: リクエストに指標およびディメンションを追加する手順です。
title: 指標およびディメンションの追加
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 指標およびディメンションの追加

リクエストに指標およびディメンションを追加する手順です。

1. [でデータリクエストを作成し](/help/analyze/report-builder/data-requests/data-requests.md) 、を [!UICONTROL Request Wizard: Step 1]クリックしま **[!UICONTROL Next]**&#x200B;す。
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![ステップ情報](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. 例えば、それぞれの値に加え、指標の小計を表示することができます。ただし、使用可能な指標のリストは、ディメンションの追加や削除のたびに変わります。

   You can add only metrics to the [!UICONTROL Metrics] layout section. 指標は、としてレイアウ [!UICONTROL Column Label] トに追加されま [!UICONTROL Metric Header]す。 If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   検索バーは、「指標」タブの、指標リストのすぐ上に表示されます。

   ![](assets/search_bar_metric.png)

   次の点に注意してください。

   * 検索語句を入力する途中でも、リストは自動的に更新され、名称が一致する指標だけが表示されます。
   * 一致の判定では、大文字と小文字が区別されません。また、「次を含む」の検索と等価になります。
   * 完全一致や検索フラグ（starts with、ends with、AND、OR など）には対応していません。

      リクエストウィザードを終了する（すなわち、「完了」または「キャンセル」をクリックする）か、リクエストウィザードの手順 1 に戻るか、または、指標カテゴリーを変更すると、検索語句がクリアされます。

      次の場合には、検索語句がクリアされません。

   * リストから指標項目の 1 つをドラッグ＆ドロップ（またはダブルクリック）して、その項目がピボットレイアウト／カスタムレイアウト指標パネルに追加される場合。
   * ピボットレイアウト／カスタムレイアウト指標パネルから指標項目を削除する場合。
   * 「ディメンション」タブをクリックしてから、「指標」タブに戻る場合。
   * 終了時にリクエストウィザードの手順 2 に戻る他のサブフォーム（モーダルかモードレスかを問わず）を起動する場合。以下のようなフォームがあります。

      * ディメンションフィルターフォーム
      * 期間書式設定フォーム
      * フォーマットオプションフォーム
      * 接頭辞／接尾辞フォーム
      * 出力範囲場所フォーム

1. （オプション）リクエストを指標で並べ替えるには、指標のラベルをクリックします。
1. 指標の追加時と同様にディメンションを追加します。

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. ディメンションをレイアウトグリッドにドロップすると、そのディメンションはツリービューから削除され、使用可能な残りのディメンションのリストが再計算されます。

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. （有効値は次のとおりです。

    *時間
    *日
    *週
    *月
    *年
    *日付範囲（精度が指定されていない場合）

1. [フォーマットオプション](/help/analyze/report-builder/layout/t-format-display-headers.md)とフィルターを設定して、指標とディメンションを変更します。
1. クリック **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. ここで、ディメンショ [!UICONTROL Referring Domain] ンはとの間に内訳レポートを [!UICONTROL Page] 作成しま [!UICONTROL Referring Domain]す。 The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)
