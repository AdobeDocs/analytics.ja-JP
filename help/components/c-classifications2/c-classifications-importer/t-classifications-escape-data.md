---
description: 分類ファイル内の分類データをエスケープする方法について手順を説明します。
seo-description: 分類ファイル内の分類データをエスケープする方法について手順を説明します。
seo-title: 分類データのエスケープ
solution: Analytics
subtopic: '分類      '
title: 分類データのエスケープ
topic: 管理ツール
uuid: 724edcc5-4990-4f24- afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 分類データのエスケープ

分類ファイル内の分類データをエスケープする方法について手順を説明します。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 分類ファイルの形式がバージョン 2.1 であることを確認します。

   バージョン 2.1 が有効な場合、次のような行が含まれています。

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). 次に例を示します。

```
My String "of data"
```

これをエスケープすると、次のようになります。

```
"My String ""of data"""
```
