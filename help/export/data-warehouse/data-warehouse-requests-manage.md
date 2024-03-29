---
description: リクエストマネージャーを使用して、リクエストの表示、複製、優先順位の再設定をおこなうことができます。
title: Data Warehouse リクエストの管理
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 4c9451c1df31ec22bf3f7b0198f294d8e57d79d5
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---

# Data Warehouse リクエストの管理

自分が行ったData Warehouseリクエストを表示および管理できます。 組織内の他のユーザーが行ったリクエストの表示と管理を行えるのは、管理者のみです。

次の節では、リクエストを管理する際に実行できるアクティビティについて説明します。

## リクエストの表示

デフォルトでは、自分が作成したリクエストのみが表示されます。ただし、ユーザーが自分のリクエストを組織内の他のユーザーに表示するように選択している場合を除きます ( [Data Warehouseリクエストの一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md)) をクリックします。 システム管理者は、すべてのリクエストを表示できます。

Data Warehouse要求を表示するには：

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

   Data Warehouseページには、おこなったすべてのリクエストが表示されます。 データは各列に表示されます。 以下が可能です。 [どの列を設定するかを設定](#configure-columns) が表示されます。

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. （オプション）リクエスト名をクリックして、次の情報を表示するダイアログを表示します。 <!-- Check this -->

   * リクエストの処理が開始したとき

   * 制限されたレート：組織で実行中のData Warehouseリクエストが多すぎます。 リクエストは、他のデータリクエストが完了するまで一時停止します。

## リクエストの編集

リクエストを編集する際は、次の点を考慮してください。

* スケジュールに従って実行するように設定されたリクエストのみを編集できます。

* リクエストに関連付けられているすべてのフィールドを編集できるわけではありません。 編集できないフィールドは淡色表示になります。

* 別のユーザーのリクエストを編集する管理者は、アクセスできる新しいアカウントと場所を選択する必要があります。

スケジュールされたリクエストを編集するには：

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、編集するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 「[!UICONTROL **編集**]」を選択します。

1. 必要に応じてリクエストを編集します。 淡色表示の設定オプションは編集できません。

   各設定オプションについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 選択 [!UICONTROL **変更を保存**].

## リクエストの履歴の表示

おこなったData Warehouse要求の履歴を表示できます。

1. Adobe Analyticsで、 [!UICONTROL **ツール**] > [!UICONTROL **Data Warehouse**].

1. Data Warehouseページで、履歴を表示するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 選択 [!UICONTROL **履歴を表示**].

   The [!UICONTROL **Data Warehouse要求の表示**] ページには、リクエストに関連付けられている個々のレポート配信のリストが表示されます。

   を選択します。 **列を設定** アイコン ![列を設定アイコン](assets/configure-column-icon.png) ：デフォルトで表示されていない列の非表示または表示を切り替えます。

   ![リクエスト履歴ページ](assets/dw-request-history.png)

   以下の列を表示できます。

   | 列 | 説明 |
   |---------|----------|
   | [!UICONTROL **作成日**] | レポートが作成された日時。<p>これは、リクエストを開始したユーザーのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **開始日**] | レポートが開始された日時。<p>これは、リクエストを開始したユーザーのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **完了日**] | レポートが完了した日時。<p>これは、リクエストを開始したユーザーのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **更新日**] | レポートが最後に更新された日時。<p>これは、リクエストを開始したユーザーのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **ステータス**] | レポート配信のステータス。 考えられるステータスは次のとおりです。<ul><li>[!UICONTROL **作成済み**]：レポートは作成されましたが、まだ処理されていません。</li><li>[!UICONTROL **保留中**]：レポートは処理を待機中です。</li><li>[!UICONTROL **処理中**]：レポートは現在処理中です。</li><li>[!UICONTROL **完了**]：レポートが完了し、使用できるようになりました。</li><li>[!UICONTROL **Scheduled**]：レポートはスケジュールされていますが、まだ開始されていません。</li><li>[!UICONTROL **キャンセル**]：レポートがユーザーによってキャンセルされました。</li><li>[!UICONTROL **エラー — 処理中**:] レポートでエラーが発生したので、処理できませんでした。</li><li>[!UICONTROL **エラー — 送信エラー**]：レポートが正常に生成されましたが、配信できませんでした。 次を確認します。 [宛先の設定](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)」をクリックし、レポートを再送信します。</li></ul>。 |
   | [!UICONTROL **送信元**] | レポートに含まれる全体的な期間の開始日。<p>これは、レポートスイートのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **設定値**] | レポートに含まれる全期間の終了日。 <p>これは、レポートスイートのタイムゾーンに表示されます。</p> |
   | [!UICONTROL **レガシーリクエスト ID**] | レガシーData Warehouseインターフェイスでレポートを識別するために使用される ID。 この ID は、カスタマーケアに問い合わせる際にAdobeで必要になる場合があります。 |
   | [!UICONTROL **レポート ID**] | 現在のData Warehouseインターフェイスでレポートを識別するために使用される ID。 この ID は、カスタマーケアに問い合わせる際にAdobeで必要になる場合があります。 |


1. レポート配信を選択し、次のいずれかのオプションを選択します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **宛先の詳細**] | リクエストに関連付けられたアカウントと場所の詳細を表示します。 これは、以前に設定したアカウントと場所です。詳しくは、 [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **レポートをキャンセル**] | レポートをキャンセルします。 ステータスが「 [!UICONTROL **完了**] または [!UICONTROL **キャンセル**]. |
   | [!UICONTROL **レポートの再実行**] | 最初の送信時と同じデータでレポートを再実行します。 次のいずれかのステータスのレポートを再実行できます。 [!UICONTROL **キャンセル**], [!UICONTROL **完了**], [!UICONTROL **エラー — 処理中**]&#x200B;または [!UICONTROL **エラー — 送信エラー**]. |
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
   | ステータス | 次のステータスを使用できます。<ul><li><p>**完了**：リクエストが正常に実行されました。</p></li><li><p>**キャンセル**：リクエストがユーザーによってキャンセルされました。</p></li><li><p>**Scheduled**：リクエストは、スケジュールに従って実行するように設定されます。</p></li><li><p>**失敗**：リクエストを完了できませんでした。 要求が引き続き失敗する場合は、カスタマーサポートにお問い合わせください。</p></li></ul> |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。 選択した列がData Warehouseページに表示され、関連情報が表示されます。

## リクエストのフィルターと並べ替え

1. を選択します。 **フィルター** アイコンをクリックします。Data Warehouseページの左側のレールに表示されます。

   ![リクエストのフィルタリング](assets/dw-filter.png)

1. を展開します。 [!UICONTROL **レポートスイート**], [!UICONTROL **所有者**]&#x200B;または [!UICONTROL **ステータス**] 「 」セクションで、リクエストのフィルタリング方法を選択します。

## リクエストの検索

1. Data Warehouseページ上部の検索フィールドで、表示するリクエスト名を指定します。

   リクエストは、入力に応じてフィルタリングされます。