---
title: Report BuilderでのVisual Basic マクロの使用方法
description: VBA マクロを使用してExcel ブックとReport Builderの機能を拡張する方法について説明します。
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 64%

---

# Report Builder の Visual Basic マクロ

{{legacy-arb}}

Visual Basic （VBA） マクロには、Excel ブックの更新に役立つ機能が用意されています。 Visual Basicでは、ブック、Excel、およびWindowsにアクセスできます。

VBA マクロを実行する前に、最新バージョンのReport Builderを実行してログインする必要があります。

>[!IMPORTANT]
>
>セキュリティ上の理由から、マクロを含むブックをスケジュールすることはできません。

Adobeでは、3つのReport Builder API メソッドをサポートしています。

## `RefreshAllReportBuilderRequests()`

次のマクロは、アクティブなワークブック内のすべての Report Builder リクエストを最新の情報に更新します。`RefreshAllReportBuilderRequests()` まず Report Builder COM Add-in をその製品 ID で呼び出し、次に `RefreshAllRequests()` API コマンドを呼び出します。

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

`RefreshAllReportBuilderRequestsInActiveWorksheet()` マクロは、アクティブなワークブック内のすべての Report Builder リクエストを最新の情報に更新します。 `RefreshWorksheetRequests()` API 呼び出しは、ワークシートオブジェクトを引数として受け取ります。 この呼び出しは、Report Builder 要求を含むワークシートに対して使用できます。

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

`RefreshAllReportBuilderRequestsInCellsRange()` マクロは、セル出力が指定した範囲のセルと交差するすべての Report Builder リクエストを最新の情報に更新します。 次の使用例は、作業中のブック内の「Data」ワークシートで `B1:B54` の範囲を指すセル範囲を指定します。 範囲式は、サポートされる Excel 範囲式をすべてサポートしています。

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
