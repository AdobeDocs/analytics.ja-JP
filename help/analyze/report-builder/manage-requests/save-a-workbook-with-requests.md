---
description: リクエストを含むレポートの作成後、Excel のファイル／保存、またはファイル／名前を付けて保存をクリックしてレポートを保存できます。Report Builder では、レポートにリクエストが含まれているかどうかを検出します。これらの保存オプションのいずれかをクリックすると、「ワークブックに名前を付けて保存」フォームが表示されます。
title: リクエストを含むワークブックの保存
topic: Report builder
uuid: 31611031-0982-4124-9fc7-7888124aa603
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# リクエストを含むワークブックの保存

リクエストを含むレポートの作成後、Excel のファイル／保存、またはファイル／名前を付けて保存をクリックしてレポートを保存できます。Report Builder では、レポートにリクエストが含まれているかどうかを検出します。これらの保存オプションのいずれかをクリックすると、「ワークブックに名前を付けて保存」フォームが表示されます。

* Windows アプリケーションを使用して大規模な作業を行う場合、ワークシートのリクエストが予期せず失われないように、スプレッドシートのリクエストを頻繁に保存することをお勧めします。
* ワークブックに名前を付けるときには、作業履歴を保持できるようにファイル名にバージョン番号を付けることをご検討ください。例えば、最初のワークブックには [!DNL web_forecast_01_01.xlsx] のような名前を付けます。
* If you have already saved the report, the [!UICONTROL Save Template] form is not displayed when saving the report a second time. レポートにリクエストが含まれていない場合、このダイアログボックスは表示されません。Instead, the standard Excel [!UICONTROL Save As] form is displayed.

## ファイル名と場所 {#section_2406629E9B644CE08430826948977D5D}

The [!UICONTROL Save Template] form has some of the same functions as the standard Excel [!UICONTROL File] > [!UICONTROL Save As] dialog box, such as a text box for entering the file name of the spreadsheet report using the conventional [!DNL .xls] file extension.

使用するファイル名は 255 文字以内である必要があります。また、ファイル名に次の文字を使用することはできません。

\ ? | > &lt; : / * &#39; &quot;

最後に、拡張 ASCII 文字セットに含まれない「Unicode 文字」を使用することはできません。

When saving the file to a location on your local or network drives, you may enter the full path in the text box, or click on the browse button  ![browse_button.gif](assets/browse_button.gif) adjacent to the [!UICONTROL Save As] text box.
