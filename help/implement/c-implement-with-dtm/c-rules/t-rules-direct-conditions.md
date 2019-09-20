---
description: ダイレクト型ルールの条件の作成.
keywords: Dynamic Tag Management；ルール；ルールの作成；新規ルール；ダイレクト型ルール
seo-description: ダイレクト型ルールの条件の作成.
seo-title: ダイレクト型ルールの条件の作成
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: ダイレクト型ルールの条件の作成
uuid: bab0e058-a5b8-4039-8333-5e8f3d06ade4
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# ダイレクト型ルールの条件の作成

ダイレクト型ルールの条件の作成.

1. In the **[!UICONTROL Conditions]** dialog, specify the string that will be passed to `_satellite.track()` in your direct call, without quotes.

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >If you specify the string that will be passed to `_satellite.track()` in your direct call using the UI, as described above, do not use quotation marks. If you insert [customized page code](../../../implement/c-implement-with-dtm/c-aa-tool/customize-page-code.md#concept_7D6390823DFE4D29AF9505CCE1A79C3B) using the editor, you must use quotation marks.

