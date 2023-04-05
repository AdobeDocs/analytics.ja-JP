---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。
title: Activity Map の有効化
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: 87c2f559990674ee738e1ad57166cf192d58232c
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 66%

---

# Activity Map の有効化{#enable-activity-map}

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。

## 手順 1.実装コードを更新する {#section_5D1586289DF2489289B1B6C1C80C300D}

このActivity Mapモジュールは、AppMeasurement.js および Web SDK( バージョン2.15.0以降 ) の一部です。
AppMeasurement ライブラリまたは Web SDK は、インスタンス化の際にActivity Mapモジュールを読み込みます。

>[!NOTE]
>
>Activity Mapデータは、 **AppMeasurement** **バージョン 1.6** またはそれ以上 **Web SDK** **バージョン2.15.0** またはそれ以降


1. AppMeasurement と Web SDK のどちらを使用しているかに応じて、最新の JavaScript ライブラリをダウンロードします。

   - **AppMeasurement** コード (AppMeasurement_Javascript-1.6.zip) を  **[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL コードマネージャー]** および [実装する](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=ja).

      Activity Map モジュールを含めることによるコードの変更を視覚的に確認できるように、[実装コードのサンプル](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)を含めました。

   - **Web SDK** コード (alloy.js) を使用します。 詳しくは、 [SDK — オプション 2 をインストールします。事前にビルドされたスタンドアロンバージョンのインストール](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja#option-2%3A-installing-the-prebuilt-standalone-version) を参照してください。 必ずバージョン 2.15 以降を使用してください。

      詳しくは、 [リンクを追跡](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja) リンクトラッキングの実装方法と、 `region` クリックされたHTML要素の

      >[!NOTE]
      >
      >現在、顧客がページ間を移動すると、Web SDK でのリンクトラッキングがリンクイベントを送信しています。 これは、AppMeasurement の動作方法とは異なり、追加の課金対象ヒットがAdobeに送信される可能性があります。


1. 実装の検証:

   1. クリック可能な要素をクリックすると、s_sq という名前の cookie にデータが保存されます。
   1. Activity Map データは、トラッキングコール時のクエリ文字列で確認できます。以下に例を示します。

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. このレポートを&#x200B;**[!UICONTROL 地域別 Activity Map リンク]**&#x200B;によって分割すると、そのページのリンクと地域を確認できます。  ![](assets/am_breakdown.png){width="400px"}

## 手順 2.Activity Map レポートを有効にする {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

まず、レポートスイートレベルで Activity Map レポートを有効にする必要があります。

1. Adobe Analytics にログインし、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動してレポートスイートを選択し、**[!UICONTROL 設定を編集]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map レポート]** に移動します。
1. リンクデータが Activity Map レポートに収集されます。有効化をおこなうには、まず「**[!UICONTROL Activity Map レポートを有効にする]**」をクリックして変数を有効にする必要があります。

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

1. 約 1 時間後に、[Activity Map ページレポート](/help/analyze/activity-map/activitymap-reporting-analytics.md)を確認すると、ユーザーがリンクをクリックしたページがすべて表示されます。

## 手順 3.ユーザーを Activity Map アクセスグループに追加 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 「**[!UICONTROL ユーザーをグループに追加]**」をクリックします。

   Admin Console のグループ管理ページが表示されます。

1. [このグループにユーザーを追加](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=ja)して「**[!UICONTROL グループの保存]**」をクリックします。

1. これで、管理者ユーザーは、**[!UICONTROL Adobe Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL Activity Map]** から Activity Map をダウンロードできます。

>[!NOTE]
>
> 管理者以外のユーザーが Activity Map をダウンロードしたい場合、新規ユーザーグループを作成し、「ツール」および「レガシー ClickMap のインストール」の権限を付与します。Activity Map アクセスと組み合わせたこのレベルの権限は、ツールをダウンロードおよび使用する権限を付与します。
