---
description: データガバナンスのプライバシーラベリングダイアログは、レポートスイートのプライバシーラベルおよび名前空間の概要を提供します。また、ここから .csv ファイルに設定を書き出すこともできます。
title: データガバナンスのプライバシーラベリングの表示／管理
feature: Data Governance
role: Admin
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 94%

---

# データガバナンスのプライバシーラベリングの表示／管理

**[!UICONTROL データガバナンスのプライバシーラベリング]**&#x200B;ダイアログは、レポートスイートのプライバシーラベルおよび名前空間の概要を提供します。また、ここから .csv ファイルに設定を書き出すこともできます。

## プライバシーラベルの表示 {#view-privacy}

1. Adobe Experience Cloud にログインします。
2. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]**／**[!UICONTROL データ設定と収集]**／**[!UICONTROL データガバナンス]**&#x200B;に移動します。

   >[!NOTE]
   >
   >このメニュー項目が表示されない場合は、この機能への権限を持つ [Admin Console の製品プロファイル ](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=ja) に追加するか、Admin Console内のレポートスイートへのアクセス権を付与されている必要があります。

3. 右上で、プライバシーラベルを表示または管理したいレポートスイートを選択します。

   ![](assets/privacy_labeling.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL コンポーネント名]** | この列には、このレポートスイートの一部であるすべてのコンポーネント（ディメンション、指標）がリストされます。 |
| **[!UICONTROL ID]** | 識別データの「I」ラベルは、個人を特定できるデータまたは個人に連絡できるデータの分類に使用されます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=ja#data-privacy-identity-labels) |
| **[!UICONTROL 機密性]** | 機密データの「S」ラベルは、地理データなどの機密データの分類に使用されます。将来的に、他のタイプの機密情報を特定するために、追加の機密データラベルが導入される予定です。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=ja#sensitive-data-labels) |
| **[!UICONTROL GDPR アクセス]** | データガバナンスラベルを使用すると、規制や企業のポリシーに準拠するためにプライバシー関連の注意事項や契約条件を反映したデータを分類できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=ja#data-privacy-access-labels) |
| **[!UICONTROL GDPR 削除]** | 削除ラベルは、ヒットとデータ主体との関連付けを許可する（つまり、データ主体の識別を許可する）値を含んだフィールドに対してのみ必要です。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=ja#data-privacy-delete-labels) |
| **[!UICONTROL 名前空間]** | 変数を ID-DEVICE または ID-PERSON としてラベル設定する場合、名前空間を提供するよう指示されます。以前定義した名前空間を使用することも、新しい名前空間を定義することもできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=ja#provide-namespace) |
| **[!UICONTROL カテゴリ]** | コンポーネントのタイプ（標準コンポーネント、コンバージョン変数など）を指します |

{style="table-layout:auto"}

## レポートスイートへのプライバシーラベルのコピー  {#copy-to-rs}

複数のレポートスイートに同じデータプライバシー設定を割り当てる場合は、次の手順に従います。

1. コピーする変数を選択します。コピーできるのは、一度に 1 つの変数のラベルのみであることに注意してください。
1. データガバナンスダイアログの下部にある「**[!UICONTROL レポートスイートにコピー]**」をクリックします。

   ![レポートスイートにコピー](assets/copy_to_reportsuite.png)

1. 表示される画面には、変数名、コピーしようとしている現在適用されているラベル、レポートスイートとその ID およびターゲットのレポートスイートの設定に一致しているかどうかが表示されます。

   ![レポートスイートへのラベルのコピー](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >選択したレポートスイートは、すべて Experience Cloud 組織にマッピングする必要があります。

   1 つの変数または変数のセットのラベルを別のレポートスイートにコピーする場合、コピーは、コピー先レポートスイートの対応する位置の変数に対して行われます。標準コンポーネント、リスト変数および成功イベントの場合、ラベルは、コピー先レポートスイートの&#x200B;**同じ名前**&#x200B;を持つ変数にコピーされます。

   ただし、コンバージョン変数（eVar）およびトラフィックディメンション（prop）の場合、コピーは、コピー先レポートスイート内にある&#x200B;**同じ数**&#x200B;を持つ変数に対して行われます。例えば、eVar12 は、すべてのコピー先レポートスイートの eVar12 にコピーされます。コピーの対象を判断するうえで、これらの変数の名前は無視されます。対応する変数がコピー先レポートスイートで有効でない場合、その変数のコピーは失敗します。

   変数用に定義された分類用にラベルをコピーする場合、ラベルは、コピーする分類と同じ名前を持つ、コピー先レポートスイートの対応する変数（eVar7 から eVar7）の分類にコピーされます。そうでない場合、その分類のラベルのコピーは失敗します。

1. 設定が一致する 1 つまたは複数のレポートスイートの横にあるチェックボックスをオンにします。
1. 「**[!UICONTROL 適用]**」をクリックします。

   ラベルが適用されると、ステータスメッセージが表示されます。ステータスメッセージには、コピー先の変数または分類とコピーが失敗したレポートスイートの名前が含まれます。

   >[!IMPORTANT]
   >
   >常にコピー先レポートスイートをチェックして、ラベルが適切にコピーされていることを確認する必要があります。これは、ID または DEL ラベルを持つ変数で特に重要です。

## .csv ファイルへの書き出し {#export-csv}

選択したレポートスイートのすべての変数に関する現在のすべてのラベル定義を含む CSV ファイルをダウンロードします。アドビでは、法務チームがラベリングの選択を確認することをお勧めしていますが、このオプションを使用すると、確認が容易になります。データガバナンス UI にログインしてレビューを実行しなくても、法務チームと .CSV ファイルを共有できます。

1. 右上で **[!UICONTROL CSV を書き出し]**&#x200B;をクリックすると、次のダイアログが表示されます。

   ![](assets/export_csv.png)

1. すべてのデータガバナンス設定を書き出したい 1 つまたは複数のレポートスイートを選択します。

## プライバシーラベルの編集 {#edit}

[レポートスイートのプライバシーラベルの割り当てまたは編集](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)を参照してください。
