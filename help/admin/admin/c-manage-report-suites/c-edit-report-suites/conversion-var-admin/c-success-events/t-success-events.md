---
description: 成功イベントを設定する方法について手順を説明します。
title: 成功イベントの設定
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---

# 成功イベントの設定

成功イベントを設定するには：

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. レポートスイートを選択します。
1. **[!UICONTROL 設定を編集]**／**[!UICONTROL コンバージョン]**／**[!UICONTROL 成功イベント]**&#x200B;の順にクリックします。

   ![手順の結果](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1.  「**[!UICONTROL 名前]**」列で編集を有効にする各項目の横にあるチェックボックスを選択し、名前を指定します。
1.  「**[!UICONTROL タイプ]**」列でドロップダウンリストを有効にする各項目の横にあるチェックボックスを選択し、タイプを選択します。

   >[!NOTE]
   >
   >イベントタイプを変更する前に、[イベントタイプを変更する](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)を参照してください。

   ここに挙げた要素について詳しくは、[成功イベントページ - 説明](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)を参照してください。

1. 「**[!UICONTROL 極性]**」列で、この指標の上昇傾向が良いのか悪いのかを指定します。
1. 「**[!UICONTROL 表示]**」列で、メニュー、指標セレクター、計算指標ビルダーおよびセグメントビルダー内の標準（組み込み）指標、カスタムイベントおよび組み込みイベントを非表示にできます。

   この設定は、指標やイベントのデータ収集には影響しません。以下のように、ユーザーインターフェイス内での表示にのみ影響します。


   | 設定 | 表示 | 非表示 |
   |---------|----------|---------|
   | [!UICONTROL **すべての場所で表示**] | <ul><li>Reports &amp; Analytics（メニューと指標セレクター）</li><li>Analysis Workspace</li><li>セグメントビルダー</li><li>計算指標ビルダー</li></ul> | 該当なし |
   | [!UICONTROL **ビルダー**] | <ul><li>セグメントビルダー</li><li>計算指標ビルダー</li></ul> | <ul><li>Reports &amp; Analytics（メニューと指標セレクター）</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **すべての場所で非表示**] | 該当なし | <ul><li>Reports &amp; Analytics（メニューと指標セレクター）</li><li>Analysis Workspace</li><li>セグメントビルダー</li><li>計算指標ビルダー</li></ul> |

1. 説明を入力します。
1. イベントを常に記録するかどうかを選択します。
1. パーティシペーション指標を有効または無効にします。

   >[!NOTE]
   >
   >パーティシペーションは、最大 100 個のカスタムイベントに対して有効にすることができます。100 を超える場合は、[計算指標](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)ビルダーでパーティシペーション指標を作成できます。

1. 「**[!UICONTROL 保存]**」をクリックします。
