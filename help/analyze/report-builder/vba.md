---
title: Report Builderで Visual Basic マクロを使用する方法
description: VBA マクロを使用して、Excel のブックやReport Builderの機能を拡張する方法を説明します。
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 68%

---

# Report Builder の Visual Basic マクロ

Visual Basic (VBA) マクロには、Excel ブックを更新するのに役立つ機能が用意されています。 Visual Basic は、ブック、Excel、および Windows にアクセスできます。

VBA マクロを実行する前に、最新バージョンのReport Builderを実行し、ログインする必要があります。

>[!IMPORTANT]
>
>セキュリティ上の理由から、マクロを含むブックをスケジュールすることはできません。

アドビは 3 つの Report Builder API メソッドをサポートしています。

## `RefreshAllReportBuilderRequests()`

次のマクロは、アクティブなワークブック内のすべての Report Builder リクエストを最新の情報に更新します。`RefreshAllReportBuilderRequests()`まず Report Builder COM Add-in をその製品 ID で呼び出し、次に `RefreshAllRequests()` API コマンドを呼び出します。

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

`RefreshAllReportBuilderRequestsInActiveWorksheet()` マクロは、アクティブなワークブック内のすべての Report Builder リクエストを最新の情報に更新します。`RefreshWorksheetRequests()` API 呼び出しは、ワークシートオブジェクトを引数として受け取ります。  この呼び出しは、Report Builder 要求を含むワークシートに対して使用できます。

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

`RefreshAllReportBuilderRequestsInCellsRange()` マクロは、セル出力が指定した範囲のセルと交差するすべての Report Builder リクエストを最新の情報に更新します。次の使用例は、作業中のブック内の「Data」ワークシートで `B1:B54` の範囲を指すセル範囲を指定します。範囲式は、サポートされる Excel 範囲式をすべてサポートしています。

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
