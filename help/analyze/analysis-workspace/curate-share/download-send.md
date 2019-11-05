---
description: 保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。
seo-description: 保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。
seo-title: PDF ファイルまたは CSV ファイルのダウンロード
title: PDF ファイルまたは CSV ファイルのダウンロード
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# PDF ファイルまたは CSV ファイルのダウンロード

保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。

この PDF または CSV ファイルの名前には、プロジェクトの現在の名前が使用されます。未保存のプロジェクトの場合、ダウンロードされたファイルにはプロジェクトの未保存の変更内容が含まれています。PDF または CSV の未保存のプロジェクトをスケジュールすることはできません。

> [!NOTE] また、CSV形式のフォールアウトビジュアライゼーションもサポートしています。

> [!NOTE] プロジェクトをPDFにレンダリングすると、ページ上の内容がレンダリングされます。 プロジェクトにカスタムサイズのビジュアライゼーションとパネルが含まれている場合、内容が切り詰められないように、自動サイズに変更する必要があります（右上隅のボタン）。

1. プロジェクトを作成するか、または開きます。
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* 桁区切り記号は含まれなくなりました。(The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components &gt; Report Settings &gt; Thousands Separator]**).
* 通貨記号は表示されません。
* パーセント記号は表示されません。
* 割合は小数形式です。例えば、75%は0.75と表される。
* 時間は秒単位で表示されます。
* コホートテーブルは生の値のみを表示します。割合が削除されます。
* 数値が無効な場合は、空のセルが表示されます。

>[!N注意：]
>
> カンマを小数点記号として使用する数値は、書き出したCSVで引き続き引用符で囲まれます。
