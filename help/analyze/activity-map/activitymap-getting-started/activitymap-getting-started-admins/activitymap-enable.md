---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。
title: Activity Map の有効化
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: 営業者、管理者
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 99%

---


# Activity Map の有効化 {#enable-activity-map}

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。

## 手順 1.AppMeasurement（JavaScript）コードを v1.6 以上に更新 {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map モジュールは、AppMeasurement.js ファイルの一部です（ファイルの先頭にあります）。AppMeasurement ライブラリは、インスタンス化の際に Activity Map を読み込みます。

Activity Map のデータは、このバージョン以上の AppMeasurement に更新しない限り収集できません。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL コードマネージャー]**&#x200B;に移動して、最新の AppMeasurement コード（AppMeasurement_Javascript-1.6.zip）をダウンロードし、[実装します](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/js/overview.html)。

   Activity Map モジュールを含めることによるコードの変更を視覚的に確認できるように、[実装コードのサンプル](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)を含めました。

1. 実装の検証:

   1. クリック可能な要素をクリックすると、s_sq という名前の cookie にデータが保存されます。
   1. Activity Map データは、トラッキングコール時のクエリ文字列で確認できます。次に例を示します。

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. このレポートを&#x200B;**[!UICONTROL 地域別 Activity Map リンク]**&#x200B;によって分割すると、そのページのリンクと地域を確認できます。![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 手順 2.Activity Map レポートを有効にする {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

まず、レポートスイートレベルで Activity Map レポートを有効にする必要があります。

1. Adobe Analytics にログインし、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動してレポートスイートを選択し、**[!UICONTROL 設定を編集]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map レポート]** に移動します。
1. リンクデータが Activity Map レポートに収集されます。有効化をおこなうには、まず「**[!UICONTROL Activity Map レポートを有効にする]**」をクリックして変数を有効にする必要があります。

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

1. 約 1 時間後に、[Activity Map ページレポート](/help/analyze/activity-map/activitymap-reporting-analytics.md)を確認すると、ユーザーがリンクをクリックしたページがすべて表示されます。

## 手順 3.ユーザーを Activity Map アクセスグループに追加 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 「**[!UICONTROL ユーザーをグループに追加]**」をクリックします。

   Admin Console のグループ管理ページが表示されます。

1. [このグループにユーザーを追加](https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/user-groups/groups.html)して「**[!UICONTROL グループの保存]**」をクリックします。

1. これで、管理者ユーザーは、**[!UICONTROL Adobe Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL Activity Map]** から Activity Map をダウンロードできます。

>[!NOTE]
>
> 管理者以外のユーザーが Activity Map をダウンロードしたい場合、新規ユーザーグループを作成し、「ツール」および「レガシー ClickMap のインストール」の権限を付与します。Activity Map アクセスと組み合わせたこのレベルの権限は、ツールをダウンロードおよび使用する権限を付与します。
