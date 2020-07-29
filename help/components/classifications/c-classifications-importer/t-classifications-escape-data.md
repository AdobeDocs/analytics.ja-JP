---
description: 分類ファイル内の分類データをエスケープする方法について手順を説明します。
subtopic: Classifications
title: 分類データのエスケープ
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 100%

---


# 分類データのエスケープ

分類ファイル内の分類データをエスケープする方法について手順を説明します。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 分類ファイルの形式がバージョン 2.1 であることを確認します。

   バージョン 2.1 が有効な場合、次のような行が含まれています。

   >[!NOTE]
   >
   >バージョン 2.1 の形式を指定するには、**[!UICONTROL 分類インポーター]**&#x200B;ページ（[!UICONTROL ブラウザーの書き出し]または [!UICONTROL FTP の書き出し]）でファイルを書き出すときに[!UICONTROL 引用の出力]を有効にします。

1. 特殊文字を含むフィールドを二重引用符（`"`）で囲みます。

エスケープされたセル内では、2 つの二重引用符文字（`" "`）を使用することによって、二重引用符文字を指定できます。次に例を示します。

```
My String "of data"
```

これをエスケープすると、次のようになります。

```
"My String ""of data"""
```
