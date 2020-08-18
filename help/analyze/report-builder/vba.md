---
title: Report BuilderのVisual Basicマクロ
description: VBAを使用して、ExcelのブックやReport Builderの機能を拡張します。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Report BuilderのVisual Basicマクロ

VBAマクロはVisual Basicマクロとも呼ばれ、Microsoft Excelだけでは操作できない方法でブックを操作できます。 Visual Basicでは、ブック、Excel、Windowsにもアクセスできます。

Adobeは3つのReport BuilderAPIメソッドをサポートしています。 最新バージョンのreport builderがインストールされていることを確認し、マクロを実行する前にログインします。

>[!IMPORTANT]
>
>セキュリティ上の理由から、マクロを含むブックをスケジュールすることはできません。

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. 開始を行うには、Report BuilderCOM-追加inをその製品IDから呼び出し、 `RefreshAllRequests()` APIコマンドを呼び出します。

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. API呼び出しは、ワークシートオブジェクトを引数として受け取ります。 `RefreshWorksheetRequests()` この呼び出しは、Report Builder要求を含むワークシートに対して使用できます。

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. 次の使用例は、作業中のブック内の&quot;Data&quot;ワークシート `B1:B54` の範囲を指すセル範囲を指定します。 範囲式は、サポートされるExcel範囲式をすべてサポートしています。

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
