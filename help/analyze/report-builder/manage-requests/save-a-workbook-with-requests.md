---
description: リクエストを含むレポートの作成後、Excel のファイル／保存、またはファイル／名前を付けて保存をクリックしてレポートを保存できます。Report Builder では、レポートにリクエストが含まれているかどうかを検出します。これらの保存オプションのいずれかをクリックすると、「ワークブックに名前を付けて保存」フォームが表示されます。
seo-description: リクエストを含むレポートの作成後、Excel のファイル／保存、またはファイル／名前を付けて保存をクリックしてレポートを保存できます。Report Builder では、レポートにリクエストが含まれているかどうかを検出します。これらの保存オプションのいずれかをクリックすると、「ワークブックに名前を付けて保存」フォームが表示されます。
seo-title: リクエストを含むワークブックの保存
solution: Analytics
title: リクエストを含むワークブックの保存
topic: Report Builder
uuid: 31611031-0982-4124-9fc7-7888124aa603
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# リクエストを含むワークブックの保存

リクエストを含むレポートの作成後、Excel のファイル／保存、またはファイル／名前を付けて保存をクリックしてレポートを保存できます。Report Builder では、レポートにリクエストが含まれているかどうかを検出します。これらの保存オプションのいずれかをクリックすると、「ワークブックに名前を付けて保存」フォームが表示されます。

* Windows アプリケーションを使用して大規模な作業を行う場合、ワークシートのリクエストが予期せず失われないように、スプレッドシートのリクエストを頻繁に保存することをお勧めします。
* ワークブックに名前を付けるときには、作業履歴を保持できるようにファイル名にバージョン番号を付けることをご検討ください。For example, name your first workbook [!DNL web_forecast_01_01.xlsx].
* レポートが保存済みである場合、2 回目にこのレポートを保存するときは「[!UICONTROL テンプレートを保存]」フォームは表示されません。レポートにリクエストが含まれていない場合、このダイアログボックスは表示されません。代わりに、Excel の「[!UICONTROL 名前を付けて保存]」で使用される標準のフォームが表示されます。

## Filenames and location {#section_2406629E9B644CE08430826948977D5D}

The [!UICONTROL Save Template] form has some of the same functions as the standard Excel [!UICONTROL File] &gt; [!UICONTROL Save As] dialog box, such as a text box for entering the file name of the spreadsheet report using the conventional [!DNL .xls] file extension.

使用するファイル名は 255 文字以内である必要があります。また、ファイル名に次の文字を使用することはできません。

\ ? | &gt; &lt; : / * ' "

最後に、拡張 ASCII 文字セットに含まれない「Unicode 文字」を使用することはできません。

When saving the file to a location on your local or network drives, you may enter the full path in the text box, or click on the browse button  ![browse_button.gif](assets/browse_button.gif) adjacent to the [!UICONTROL Save As] text box.
