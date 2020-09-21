---
description: ダイレクト型ルールの条件の作成。
keywords: Dynamic Tag Management;rule;create rule;new rule;direct call rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: ダイレクト型ルールの条件の作成
uuid: bab0e058-a5b8-4039-8333-5e8f3d06ade4
translation-type: ht
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12
workflow-type: ht
source-wordcount: '77'
ht-degree: 100%

---


# ダイレクト型ルールの条件の作成

ダイレクト型ルールの条件の作成。

1. **[!UICONTROL 条件]**&#x200B;ダイアログから、直接呼び出しで `_satellite.track()` に渡す文字列を（引用符なしで）指定します。

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >ダイレクト型ルール内の `_satellite.track()` に渡される文字列を UI から指定するときは、上の説明のとおり、値を引用符で囲まないでください。[カスタマイズのページコード](/help/implement/other/dtm/c-aa-tool/customize-page-code.md)をエディターで挿入するときは引用符が必要です。

