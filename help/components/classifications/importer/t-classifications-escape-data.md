---
description: 分類ファイル内の分類データをエスケープする方法について手順を説明します。
title: 分類データのエスケープ
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: ht
source-wordcount: '100'
ht-degree: 100%

---

# 分類データのエスケープ

分類ファイル内の分類データをエスケープするには：

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
