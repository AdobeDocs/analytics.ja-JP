---
description: Report Builder ユーザーインターフェイスにアクセスせずに、Report Builder関数でMicrosoft Excelを使用する方法を説明します。
title: Report Builder関数でMicrosoft Excelを使用する方法を説明します
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
TQID: https://experienceleague.adobe.com/cgDjTqGH0KzSrpg66sRfF8Kf81Q-WDwSWJ-OBvJK8DM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 6%

---

# Microsoft ExcelでのReport Builder関数の使用

{{legacy-arb}}

Report Builder関数を使用して、Report Builder ユーザーインターフェイスにアクセスせずに機能にアクセスできます。

例えば、他のソースからExcelに取り込まれたデータに基づいて、入力フィルターを使用してReport Builder リクエストを自動的に更新するには、文字列RefreshRequestsInCellsRange （。..）を使用します。 部門： すべての呼び出しは非同期であり、すぐに返され、完全に実行されるのを待つことはありません。

**要件**

* Report Builder 5.0 （またはそれ以降）が必要です。

次の表に、公開される関数を示します。

| 関数名 | タイプ | 説明 |
|:---| --- | ---|
| AsyncRefreshAll （） | string | ブック内にあるすべてのReport Builder リクエストを更新します。 |
| AsyncRefreshRange （string rangeAddressInA1Format） | string | 指定されたセル範囲アドレスに存在するすべてのReport Builder リクエストを更新します（A1 フォーマットのセル範囲を表す文字列式（例：「Sheet1!A2:A10」））。 |
| AsyncRefreshRangeAltTextParam （） | string | Ms フォームコントロールの代替テキストを通過する、指定されたセル範囲に存在するすべてのReport Builder リクエストを更新します。 |
| AsyncRefreshActiveWorksheet （） | string | アクティブなワークシートに存在するすべてのReport Builder リクエストを更新します。 |
| AsyncRefreshWorksheet （string worksheetName） | string | 指定したワークシート（タブに表示されるワークシート名）に存在するすべてのReport Builder リクエストを更新します。 |
| AsyncRefreshWorksheetAltTextParam （）; | string | Ms フォームコントロールの代替テキストを介して渡された特定のワークシート名に存在するすべてのReport Builder リクエストを更新します |
| tring GetLastRunStatus （） | string | 前回の実行のステータスを表す文字列を返します。 |

Report Builder関数にアクセスするには、**[!UICONTROL 数式]** > **[!UICONTROL 関数を挿入]**&#x200B;に移動します。 検索フィールドを使用して関数を検索するか、カテゴリを選択してそのカテゴリ内の関数を一覧表示します。

カテゴリ リストを展開した挿入関数ウィンドウを示す![ スクリーンショット。](assets/arb_functions.png)

## 例 {#section_034311081C8D4D7AA9275C1435A087CD}

次の例は、*セル P5の値がテキストまたは空白の場合、セル P9*&#x200B;の範囲を更新します。

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Report Builder関数と書式コントロールの使用 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

作成したコントロールにマクロを割り当てることができます。そのコントロールは、ワークブック リクエストを更新する関数にすることができます。 例えば、関数AsyncRefreshActiveWorksheetは、ワークシート内のすべてのリクエストを更新します。 ただし、特定のリクエストのみを更新したい場合があります。

1. マクロパラメーターを設定します。
1. コントロールを右クリックし、**[!UICONTROL マクロの割り当て]**&#x200B;を選択します。
1. Report Builder関数名を入力します（パラメーターや括弧はありません）。

マクロを割り当てウィンドウを表示する![ スクリーンショット。](assets/assign_macro.png)

## 書式コントロールを使用してReport Builder関数にパラメーターを渡す {#section_ECCA1F4990D244619DFD79138064CEF0}

パラメーターを取る2つの関数は、フォーマット制御で使用できます。 **代替テキスト：** フィールドを使用する必要があります：

* AsyncRefreshRange （string rangeAddressInA1Format）
* AsyncRefreshWorksheet （string worksheetName）

フォーマット制御を使用してReport Builder関数にパラメーターを渡すには

1. コントロールを右クリックして、**[!UICONTROL コントロールの書式設定]**&#x200B;を選択します。

   形式コントロールが選択されていることを示す![ スクリーンショット。](assets/format_control.png)

1. 「**[!UICONTROL 代替テキスト]**」タブをクリックします。

   代替テキスト タブと代替テキスト：フィールドを示す![ スクリーンショット。](assets/alt_text.png)

1. **[!UICONTROL 代替テキスト]**&#x200B;で、更新するセル範囲を入力します。
1. **[!UICONTROL 数式]** > **[!UICONTROL 関数を挿入]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**&#x200B;の下にあるReport Builder パラメーターのリストを開きます。

1. AltTextParam で終わる上記 2 つの関数のいずれかの関数名を入力して、「**[!UICONTROL OK]**」をクリックします。
