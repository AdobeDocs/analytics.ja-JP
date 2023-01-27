---
description: データガバナンスのプライバシーラベル設定ダイアログでは、レポートスイートのプライバシーラベルと名前空間の概要を提供します。 また、ここから設定を.csv ファイルに書き出すこともできます。
title: データガバナンスのプライバシーラベルを表示/管理
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 9e8607691e6b144dd9e7b7a407bb2f02d27fbb1a
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 44%

---

# データガバナンスのプライバシーラベルを表示/管理

>[!NOTE]
>
>この更新された UI は現在、制限付きテストになっています。

この **[!UICONTROL データガバナンスに関するプライバシーラベル付け]** ダイアログには、レポートスイートのプライバシーラベルと名前空間の概要が表示されます。 また、ここから設定を.csv ファイルに書き出すこともできます。

## プライバシーラベルを表示 {#view-privacy}

1. Adobe Experience Cloud にログインします。
1. に移動します。  **[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL データの設定と収集]** > **[!UICONTROL データガバナンス]**.

   >[!NOTE]
   >
   >このメニュー項目が表示されない場合は、この機能への権限を持つ [Admin Console で製品プロファイル](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=ja)に追加する必要があります。

1. 右上で、プライバシーラベルを表示または管理するレポートスイートを選択します。

   ![](assets/privacy_labeling.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL コンポーネント名]** | この列には、このレポートスイートに含まれるすべてのコンポーネント（ディメンション、指標）が一覧表示されます。 |
| **[!UICONTROL ID]** | 識別データの「I」ラベルは、個人を特定できるデータまたは個人に連絡できるデータの分類に使用されます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#identity-data-labels) |
| **[!UICONTROL 感度]** | 機密データの「S」ラベルは、地理データなどの機密データの分類に使用されます。将来的に、他のタイプの機密情報を特定するために、追加の機密データラベルが導入される予定です。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL GDPR アクセス]** | データガバナンスラベルを使用すると、規制や企業のポリシーに準拠するためにプライバシー関連の注意事項や契約条件を反映したデータを分類できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL GDPR 削除]** | 削除ラベルは、ヒットとデータ主体との関連付けを許可する（つまり、データ主体の識別を許可する）値を含んだフィールドに対してのみ必要です。他の個人情報（お気に入り、閲覧／購入履歴、健康状態など）は、データ主体との関連付けがなくなるので、削除する必要はありません。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL 名前空間]** | 変数を ID-DEVICE または ID-PERSON としてラベル設定する場合、名前空間を提供するよう指示されます。以前定義した名前空間を使用することも、新しい名前空間を定義することもできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#section_F0A47AF8DA384A26BD56032D0ABFD2D7) |
| **[!UICONTROL カテゴリ]** | コンポーネントのタイプを指します（標準コンポーネント、コンバージョン変数など）。 |

{style=&quot;table-layout:auto&quot;}

## レポートスイートへのプライバシーラベルのコピー  {#copy-to-rs}

同じ DULE/データプライバシー設定を複数のレポートスイートに適用する場合は、次の手順に従います。

1. コピーする変数を選択します。 一度にコピーできる変数は 1 つだけです。
1. クリック **[!UICONTROL レポートスイートにコピー]** をクリックします。

   ![レポートスイートにコピー](assets/copy_to_reportsuite.png)

1. 結果の画面には、変数名、コピーしようとしている現在適用されているラベル、レポートスイートとその ID、ターゲットレポートスイートの設定が一致するかどうかが表示されます。

   ![レポートスイートへのラベルのコピー](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >選択したレポートスイートは、すべて Experience Cloud 組織にマッピングする必要があります。

   1 つの変数または変数のセットのラベルを別のレポートスイートにコピーする場合、コピーは、コピー先レポートスイートの対応する位置の変数に対しておこなわれます。標準コンポーネント、リスト変数、成功イベントの場合、ラベルは、 **同名** をクリックします。

   ただし、コンバージョン変数 (eVar) およびトラフィックDimension(prop) の場合、コピーは **同数** をクリックします。 例えば、eVar12 は、すべてのコピー先レポートスイートの eVar12 にコピーされます。コピーの対象を判断するうえで、これらの変数の名前は無視されます。対応する変数がコピー先レポートスイートで有効でない場合、その変数のコピーは失敗します。

   変数に対して定義された分類のラベルをコピーする場合、ラベルは、コピー先のレポートスイートの対応する変数の分類 (eVar7 ～eVar7 など ) にコピーされます。この変数の名前は、コピー先の分類と同じです。 そうでない場合、その分類のラベルのコピーは失敗します。

1. 設定が一致する 1 つ以上のレポートスイートの横のチェックボックスをオンにします。
1. 「**[!UICONTROL 適用]**」をクリックします。

   ラベルの適用後、ステータスメッセージが表示されます。 ステータスメッセージには、コピー先の変数または分類とコピーが失敗したレポートスイートの名前が含まれます。

   >[!IMPORTANT]
   >
   >常にコピー先レポートスイートをチェックして、ラベルが適切にコピーされていることを確認する必要があります。これは、ID または DEL ラベルを持つ変数で特に重要です。

## .csv ファイルへの書き出し {#export-csv}

選択したレポートスイートのすべての変数に関する現在のラベル定義をすべて含む CSV ファイルをダウンロードできます。法務チームがラベル設定の選択を確認し、このオプションを使用してレビューを容易に行うことをお勧めします。 データガバナンス UI にログインしてレビューを実行しなくても、法務チームと .CSV ファイルを共有できます。

1. クリック **[!UICONTROL CSV を書き出し]** 右上に、このダイアログが表示されます。

   ![](assets/export_csv.png)

1. すべてのデータガバナンス設定を書き出す 1 つ以上のレポートスイートを選択します。

## プライバシーラベルを編集 {#edit}

参照： [レポートスイートのプライバシーラベルの割り当てまたは編集](/help/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md).
