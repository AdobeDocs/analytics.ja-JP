---
description: Report Builder のユーザーインターフェイスにアクセスすることなく、Excel の関数のみで Report Builder リクエストを操作できます。
title: Microsoft Excel の関数からの Report Builder 機能の呼び出し
topic: Report builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Microsoft Excel の関数からの Report Builder 機能の呼び出し

Report Builder のユーザーインターフェイスにアクセスすることなく、Excel の関数のみで Report Builder リクエストを操作できます。

例えば、他のソースからExcelで取り込んだデータに基づいて入力フィルターを適用するReport Builderリクエストを自動的に更新する場合があります。 このような処理を、string RefreshRequestsInCellsRange(..)関数を呼び出します。 すべての呼び出しは非同期的です。 呼び出しが完全に実行されるのを待たずに、即座に返されます。

>[!NOTE]この機能が動作するには、Report Builder 5.0（以降）がインストールされている必要があります。

次の表に、公開された関数のリストを示します。

| 関数名 | 説明 |
|---|---|
| string AsyncRefreshAll() | ワークブック内に存在するすべてのReport Builderリクエストを更新します。 |
| string AsyncRefreshRange(string rangeAddressInA1Format) | 指定したセル範囲アドレスに存在するすべてのReport Builderリクエストを更新します(A1形式のセルの範囲を表す文字列式ー。例：「Sheet1!A2:A10」)。 |
| string AsyncRefreshRangeAltTextParam() | MSフォームコントロールの代替テキストを通じて渡される、指定したセル範囲に存在するすべてのReport Builderリクエストを更新します。 |
| string AsyncRefreshActiveWorksheet() | アクティブなワークシートにあるすべてのReport Builderリクエストを更新します。 |
| string AsyncRefreshWorksheet(string worksheetName) | 指定したワークシート（タブに表示されるワークシート名）にあるすべてのReport Builderリクエストを更新します。 |
| string AsyncRefreshWorksheetAltTextParam(); | MSフォームコントロールの代替テキストを通じて渡された、特定のワークシート名に存在するすべてのReport Builderリクエストを更新します |
| string GetLastRunStatus() | 最後に実行された実行のステータスを示す文字列を返します。 |

report builder内でこれらの機能にアクセスするには、/に移動 [!UICONTROL Formulas] しま [!UICONTROL Insert Function]す。 カテゴリのリストの下部には、Adobe.ReportBuilder.Bridgeが表示されます。

![](assets/arb_functions.png)

## 数式でのこれらの関数の使用 {#section_034311081C8D4D7AA9275C1435A087CD}

例えば、数式

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

「セルP5の値がテキストまたは空白の場合は、セルP9の範囲を更新します。」と表示されます。

## 「コントロールの書式設定」での Report Builder 関数の使用 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

作成したコントロールにマクロを割り当て、そのコントロールをワークブックリクエストを更新する関数にすることができるようになりました。 例えば、関数AsyncRefreshActiveWorksheetは、ワークシート内のすべてのリクエストを更新します。 ただし、一部のリクエストのみを更新し、すべてのリクエストを更新しないようにしたい場合があります。

1. マクロパラメータを設定します。
1. コントロールを右クリックし、を選択しま **[!UICONTROL Assign Macro]**&#x200B;す。
1. Report Builderの関数名を入力します（パラメーターや括弧は入力しません）。

![](assets/assign_macro.png)

## 「コントロールの書式設定」から Report Builder の関数にパラメーターを渡す {#section_ECCA1F4990D244619DFD79138064CEF0}

パラメーターを取る2つの関数は、「コントロールの書式設定」で使用できますが、「代替テキスト」フィールドからのみ使用できます。

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

1. コントロールを右クリックし、を選択しま **[!UICONTROL Format Control]**&#x200B;す。

   ![](assets/format_control.png)

1. タブをクリッ [!UICONTROL Alt Text] クします。

   ![](assets/alt_text.png)

1. の下 [!UICONTROL Alternative text]に、更新するセル範囲を入力します。
1. report builderリストーのパラメーターを>> [!UICONTROL Formulas] で開 [!UICONTROL Insert Function]きます [!UICONTROL Adobe.ReportBuilder.Bridge]。

1. AltTextParam で終わる上記 2 つの関数のいずれかの関数名を入力して、「**[!UICONTROL OK]**」をクリックします。

