---
description: Report BuilderユーザーインターフェイスにアクセスせずにReport Builder機能でMicrosoft Excel を使用する方法を説明します。
title: Report Builder機能でMicrosoft Excel を使用する方法を学ぶ
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 43%

---

# Microsoft Excel でのReport Builder関数の使用

Report Builder関数を使用すると、ユーザーインターフェイスにアクセスせずにReport Builderにアクセスできます。

例えば、他のソースから Excel に取り込んだデータに基づいて、入力フィルターを使用してReport Builderリクエストを自動的に更新するには、文字列 RefreshRequestsInCellsRange(..) 関数. すべての呼び出しは非同期的で、即座に返され、完全に実行されるのを待ちません。

**要件**

* Report Builder5.0（以降）が必要です。

次の表に、公開された関数を示します。

| 関数名 | タイプ | 説明 |
|:---| --- | ---|
| AsyncRefreshAll() | string | ワークブックに存在するすべての Report Builder リクエストを更新します。 |
| AsyncRefreshRange(string rangeAddressInA1Format) | string | 指定したセル範囲のアドレスに存在するすべての Report Builder リクエストを更新します（A1 形式でセルの範囲を表す文字列。「Sheet1!A2:A10」など）。 |
| AsyncRefreshRangeAltTextParam() | string | MS フォームコントロールの代替テキストから渡される、指定されたセル範囲にあるすべての Report Builder リクエストを更新します。 |
| AsyncRefreshActiveWorksheet() | string | アクティブなワークシートにあるすべての Report Builder リクエストを更新します。 |
| AsyncRefreshWorksheet(string worksheetName) | string | 指定したワークシート（タブに表示されるワークシート名）にあるすべての Report Builder リクエストを更新します。 |
| AsyncRefreshWorksheetAltTextParam(); | string | MS フォームコントロールの代替テキストから渡される、特定のワークシート名にあるすべての Report Builder リクエストを更新します。 |
| GetLastRunStatus() の文字列 | string | 最後に実行した関数のステータスを示す文字列を返します。 |

Report Builder機能にアクセスするには、 **[!UICONTROL 数式]** > **[!UICONTROL 関数の挿入]**. 検索フィールドを使用して関数を検索するか、カテゴリを選択してそのカテゴリの関数をリストします。

![カテゴリリストが展開された「関数の挿入」ウィンドウを示すスクリーンショット。](assets/arb_functions.png)

## 例 {#section_034311081C8D4D7AA9275C1435A087CD}

次の例は、を示しています。 *セル P5 の値が文字列または空白の場合は、セル P9 の範囲を更新します*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## 「コントロールの書式設定」での Report Builder 関数の使用  {#section_26123090B5BD49748C8D8ED7A1C5ED84}

作成したコントロールにマクロを割り当て、そのコントロールに、ワークブックリクエストを更新する関数を指定することができます。 例えば、関数 AsyncRefreshActiveWorksheet は、ワークシートのすべてのリクエストを更新します。ただし、場合によっては、特定のリクエストのみを更新する必要があります。

1. コントロールを配置します。
1. コントロールを右クリックして、**[!UICONTROL マクロの割り当て]**&#x200B;を選択します。
1. Report Builder関数名を入力します（パラメータや括弧は使用できません）。

![[ マクロの割り当て ] ウィンドウを示すスクリーンショット。](assets/assign_macro.png)

## 書式コントロールを使用してReport Builder関数にパラメーターを渡す {#section_ECCA1F4990D244619DFD79138064CEF0}

Format Control では、パラメータを取る 2 つの関数を使用できます。 次を使用する必要があります。 **代替テキスト：** フィールド：

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

書式コントロールを使用してReport Builder関数にパラメータを渡すには

1. コントロールを右クリックして、**[!UICONTROL コントロールの書式設定]**&#x200B;を選択します。

   ![フォーマットコントロールが選択されていることを示すスクリーンショット。](assets/format_control.png)

1. 「**[!UICONTROL 代替テキスト]**」タブをクリックします。

   ![「代替テキスト」タブと「代替テキスト」フィールドを示すスクリーンショット。](assets/alt_text.png)

1. 「**[!UICONTROL 代替テキスト]**」に、更新するセルの範囲を入力します。
1. の下のReport Builderパラメータのリストを開く **[!UICONTROL 数式]** > **[!UICONTROL 関数の挿入]**> **[!UICONTROL Adobe.ReportBuilder.ブリッジ]**.

1. AltTextParam で終わる上記 2 つの関数のいずれかの関数名を入力して、「**[!UICONTROL OK]**」をクリックします。
