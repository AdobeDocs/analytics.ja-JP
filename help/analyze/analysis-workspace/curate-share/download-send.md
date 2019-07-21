---
description: 保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。
seo-description: 保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。
seo-title: PDF ファイルまたは CSV ファイルのダウンロード
title: PDF ファイルまたは CSV ファイルのダウンロード
uuid: 8af5f3d7-5870-4ed6-8a9f- ef290a48ef5f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# PDF ファイルまたは CSV ファイルのダウンロード

保存済みのプロジェクトも未保存のプロジェクトも、PDF および CSV 形式でダウンロードできます。

この PDF または CSV ファイルの名前には、プロジェクトの現在の名前が使用されます。未保存のプロジェクトの場合、ダウンロードされたファイルにはプロジェクトの未保存の変更内容が含まれています。PDF または CSV の未保存のプロジェクトをスケジュールすることはできません。

>[!NOTE]
>
>また、CSV形式のフォールアウトビジュアライゼーションもサポートしています。

>[!NOTE]
>
>PDFにプロジェクトをレンダリングすると、ページ上のアイテムがレンダリングされます。プロジェクトにカスタムサイズのビジュアライゼーションとパネルが含まれている場合、内容が切り詰められないように、自動サイズに変更する必要があります（右上隅のボタン）。

1. プロジェクトを作成するか、または開きます。
1. **[!UICONTROL プロジェクト]** / **[!UICONTROL CSVダウンロード（またはダウンロード）をクリックします。]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* 桁区切り記号は含まれなくなりました。(The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components &gt; Report Settings &gt; Thousands Separator]**).
* 通貨記号は表示されません。
* 記号は表示されません。
* 割合は小数形式です。例えば、75%は0.75で表されます。
* 時間は秒単位で表示されます。
* コホートテーブルには、生の値のみが表示されます。パーセントは削除されます。
* 数値が無効な場合は、空のセルが表示されます。

>[!Ntoo:]
>
> 小数点区切り文字としてコンマを使用する数値は、書き出されたCSVでも引き続き引用符で囲まれます。