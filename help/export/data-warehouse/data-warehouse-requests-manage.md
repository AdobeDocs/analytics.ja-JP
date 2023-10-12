---
description: リクエストマネージャーを使用して、リクエストの表示、複製、優先順位の再設定をおこなうことができます。
title: Data Warehouse リクエストの管理
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 48455ca071b2137d4d1d9f8d6d5dce77aee25b5e
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 16%

---

# Data Warehouse リクエストの管理

{{release-limited-testing}}

>[!NOTE]
>
>すべてのお客様が間もなく利用できる新しいData Warehouse体験をお持ちでない場合は、 [Data Warehouseリクエストの管理（古いエクスペリエンス）](#manage-data-warehouse-requests-old-experience) をクリックします。


おこなったData Warehouseリクエストを管理できます。 次の節では、リクエストを管理する際に実行できるアクティビティについて説明します。 <!-- just those you have made? I think you can see other people's requests (you can filter by them). What can you do with other people's requests? Just view them?-->

## リクエストの表示

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

   Data Warehouseページには、おこなったすべてのリクエストが表示されます。 <!-- just those you have made? -->データは各列に表示されます。 以下が可能です。 [どの列を設定するかを設定](#configure-columns) が表示されます。

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. （オプション）リクエスト名をクリックして、次の情報を表示するダイアログを表示します。 <!-- Check this -->

   * リクエストの処理が開始したとき

   * 制限されたレート：組織で実行中のData Warehouseリクエストが多すぎます。 リクエストは、他のデータリクエストが完了するまで一時停止します。

## リクエストの編集

リクエストを編集する際は、次の点を考慮してください。

* スケジュールに従って実行するように設定されたリクエストのみを編集できます。

* リクエストに関連付けられているすべてのフィールドを編集できるわけではありません。 編集できないフィールドは淡色表示になります。

スケジュールされたリクエストを編集するには：

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、編集するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 「[!UICONTROL **編集**]」を選択します。

1. 必要に応じてリクエストを編集します。 淡色表示の設定オプションは編集できません。

   各設定オプションについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 選択 [!UICONTROL **変更を保存**].

## リクエストの履歴の表示

実行されたレポートの履歴を表示できます。

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、履歴を表示するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 選択 [!UICONTROL **履歴を表示**].

   The [!UICONTROL **Data Warehouse要求の表示**] ページには、個々のレポート配信のリストが表示されます。

   ![リクエスト履歴ページ](assets/dw-request-history.png)

1. レポート配信を選択し、次のいずれかのオプションを選択します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **宛先の詳細**] | リクエストに関連付けられたアカウントと場所の詳細を表示します。 これは、以前に設定したアカウントと場所です。詳しくは、 [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **レポートをキャンセル**] | レポートをキャンセルします。 ステータスが「 [!UICONTROL **完了**] または [!UICONTROL **キャンセル**]. |
   | [!UICONTROL **レポートを再実行**] | 最初の送信時と同じデータでレポートを再実行します。 次のいずれかのステータスのレポートを再実行できます。 [!UICONTROL **キャンセル**], [!UICONTROL **完了**], [!UICONTROL **エラー — 処理中**]&#x200B;または [!UICONTROL **エラー — 送信エラー**]. |
   | [!UICONTROL **レポートを再送信**] | 以前に生成されたレポートファイルを再送信します。 次のいずれかのステータスのレポートを再送信できます。 [!UICONTROL **完了**] または [!UICONTROL **エラー — 送信エラー**]. |

## リクエストのコピー

リクエストをコピーすると、すべての設定オプションが元のリクエストからコピーされます。

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、コピーするリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 選択 [!UICONTROL **コピー**].

   コピーData Warehouseリクエストページが表示されます。 すべての設定オプションは元のリクエストからコピーされます。

1. リクエストに関連する設定オプションを更新します。

   各設定オプションについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 選択 [!UICONTROL **変更を保存**].

## リクエストをキャンセル

スケジュールに従って実行するように設定されたリクエストのみをキャンセルできます。

予定リクエストをキャンセルする手順は、次のとおりです。

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、編集するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 選択 [!UICONTROL **キャンセル**].

   リクエストは、スケジュールされた時刻に実行されなくなります。

## 列の設定

列を追加または削除することで、リクエストごとに表示する情報を設定できます。

1. を選択します。 **列の設定** アイコンを使用して、Data Warehouseページの右上に表示されます。

   ![列の設定](assets/dw-configure-columns.png)

   以下の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | リクエスト名 | リクエストを作成した人の名前。 |
   | レポートスイート | リクエストに関連付けられたレポートスイート。 |
   | リクエスト発信者 | リクエストを作成したユーザー。 |
   | リクエスト日 | リクエストがおこなわれた日付。 |
   | ステータス | 次のステータスを使用できます。<ul><li><p>**完了**：リクエストが正常に実行されました。</p></li><li><p>**キャンセル**：リクエストがユーザーによってキャンセルされました。</p></li><li><p>**Scheduled**：リクエストは、スケジュールに従って実行するように設定されます。</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。 選択した列がData Warehouseページに表示され、関連情報が表示されます。

## リクエストのフィルターと並べ替え

1. を選択します。 **フィルター** アイコンをクリックします。Data Warehouseページの左側のレールに表示されます。

   ![リクエストのフィルタリング](assets/dw-filter.png)

1. を展開します。 [!UICONTROL **レポートスイート**], [!UICONTROL **所有者**]&#x200B;または [!UICONTROL **ステータス**] 「 」セクションで、リクエストのフィルタリング方法を選択します。

## リクエストの検索

1. Data Warehouseページ上部の検索フィールドで、表示するリクエスト名を指定します。

   リクエストは、入力に応じてフィルタリングされます。

## Data Warehouseリクエストの管理（古いエクスペリエンス）

>[!NOTE]
>
>次の情報は、組織がまだ新しいData Warehouse体験を持っていない場合にのみ適用されます。この情報は、近日中にすべての Analytics ユーザーが利用できるようになります。


リクエストマネージャーを使用して、リクエストの表示、複製、優先順位の再設定をおこなうことができます。

Data Warehouse で「**[!UICONTROL リクエスト管理]**」タブを選択します。

このタブでは次の操作が可能です。

* レポート名、適用されるセグメント、要求者、リクエスト日付、ステータス別に最近のレポートリクエストを表示します。
* リクエストを複製します。リクエストの横の「**[!UICONTROL 複製]**」をクリックします。

  >[!NOTE]
  >
  >この操作では、リクエストのみが複製されます。スケジュールまたは配信の詳細は複製されません。

* レポート名または要求者のログイン名でレポートを検索します。
* レポートをキュー内の新しい場所にドラッグアンドドロップして優先順位を設定し直します。
* リクエストがいつ処理を開始したかを確認するには、スケジュール済みのリクエスト ID をクリックして、表示されるポップアップを調べます。

ジョブをクリックすると、そのジョブの個々のリクエストが表示されます。

* 制限されたレート：組織で実行中のData Warehouseリクエストが多すぎます。 リクエストは、他のデータリクエストが完了するまで一時停止します。