---
title: Report Builder の Visual Basic マクロ
description: VBA を使用して、Excel のブックや Report Builder の機能を拡張します。
translation-type: ht
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---


# Report Builder の Visual Basic マクロ

VBA マクロは Visual Basic マクロとも呼ばれ、Microsoft Excel だけでは操作できない方法でブックを操作できます。Visual Basic は、ブック、Excel、Windows にもアクセスできます。

アドビは 3 つの Report Builder API メソッドをサポートしています。最新バージョンの Report Builder がインストールされていることを確認し、マクロを実行する前にログインします。

>[!IMPORTANT]
>
>セキュリティ上の理由から、マクロを含むブックをスケジュールすることはできません。

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
