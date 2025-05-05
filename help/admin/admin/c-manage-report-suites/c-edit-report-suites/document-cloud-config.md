---
description: Adobe AnalyticsでDocument Cloudデータを表示できます
title: Document Cloud レポートの設定
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 9%

---

# Document Cloud レポートの設定

Adobe Analyticsで使用できるPDF固有のディメンションと指標を設定できます。

## PDFレポートを有効にすると追加されるコンポーネント

PDFレポートが適切に設定されている場合、Adobe Analyticsでは次のディメンションと指標を使用できます。

**ディメンション：**

* PDF検索語句

* PDFズームレベル

* PDFアクション

* PDFページ番号

* PDFファイル名

**指標：**

* PDFビュー

* PDF ページビュー

* PDFのダウンロード

* PDF検索

* 使用されたPDFーブックマーク

* PDFコピーテキスト

* PDF印刷

## Adobe AnalyticsでPDFレポートを有効にする

1. **[!UICONTROL Analytics]**/**[!UICONTROL 管理者]**/**[!UICONTROL レポートスイート]**/**`<select report suite>`**/**[!UICONTROL 設定を編集]**/9&rbrace;Document Cloud管理 **/[!UICONTROL **&#x200B; Document Cloudレポート &#x200B;**]に移動します。**

1. Adobe Document CloudPDFページで、「[!UICONTROL **管理レポートを有効にする**]」を選択します。

1. Adobe Analyticsにデータを送信するようにAdobe Document Cloudを設定するには、[Adobe Document Cloud JavaScript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html) を使用します。
