---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: レポートの送信先の設定リクエストのData Warehouse
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 15%

---

# スケジュールリクエストのData Warehouseオプションの設定

>[!AVAILABILITY]
>
>この記事 ( およびこの節の他のData Warehouse記事 ) で説明するData Warehouse機能の一部は、リリースの制限付きテスト段階でのみ使用でき、お使いの環境ではまだ使用できない場合があります。
>
>すべてのお客様がまだ利用できない機能について、およびこれらの機能のリリースのタイムラインについて詳しくは、 [リリースノート](/help/release-notes/latest.md).
>
>このメモは、機能が一般入手可能になったら削除されます。Analytics リリースプロセスについて詳しくは、[Adobe Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

設定リクエストを作成する際には、様々な設定オプションをData Warehouseできます。 次の情報では、リクエストのスケジュールオプションを設定する方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

スケジュール・リクエストのオプションをData Warehouseするには：

1. Adobe Analyticsでのリクエストの作成を開始するには、「 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **スケジュールオプション**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **今すぐレポートを送信**] | レポートを 1 回限りのレポートとして送信します。 このオプションを選択すると、すべてのスケジュールオプションが非表示になります。 |
   | [!UICONTROL **後で使用するようにスケジュール**] | レポート配信のスケジュール設定オプションを提供します。 すべてのオプションについては、以下で説明します。 |
   | [!UICONTROL **レポート頻度**] | レポートの配信頻度。 <p>次のオプションがあります。</p><ul><li>1 時間ごと</li><p>[!UICONTROL **1 時間ごと**] は、 [!UICONTROL **日付範囲**] オプションを [!UICONTROL **一般設定**] タブが [!UICONTROL **過去 1 時間**].</p><li>毎日</li><li>毎週</li><li>毎月</li><li>毎年</li></ul><p>選択した頻度に応じて、追加のオプションが表示されます。</p> |
   | [!UICONTROL **開始日 :**] | 新しいスケジュールを開始する日付。 |
   | [!UICONTROL **時刻**] | レポートを送信する時刻。 |
   | [!UICONTROL **配信終了オプション**] | スケジュールされた配信を終了するタイミングを選択します。 終了しない、特定の回数を超えた後に終了する、特定の日付に終了するなどを選択できます。 |

   {style="table-layout:auto"}

1. 引き続き、 [!UICONTROL **通知 E メール**] タブをクリックします。 詳しくは、 [通知リクエスト用の通知電子メールのData Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

