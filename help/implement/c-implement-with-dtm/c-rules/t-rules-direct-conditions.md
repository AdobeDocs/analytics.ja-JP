---
description: ダイレクト型ルールの条件を作成します。
keywords: Dynamic Tag Management;ルール、ルールの作成;new rule;ダイレクト型ルール
seo-description: ダイレクト型ルールの条件を作成します。
seo-title: ダイレクト型ルールの条件の作成
solution: Marketing Cloud、Analytics、Target、Dynamic Tag Management
title: ダイレクト型ルールの条件の作成
uuid: bab0e058- a5b8-4039-8333-5e8f3d06ade4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ダイレクト型ルールの条件の作成

ダイレクト型ルールの条件を作成します。

1. **[!UICONTROL 条件]** ダイアログで、ダイレクト呼び出し `_satellite.track()` で渡される文字列を引用符なしで指定します。

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >If you specify the string that will be passed to `_satellite.track()` in your direct call using the UI, as described above, do not use quotation marks. If you insert [customized page code](../../../implement/c-implement-with-dtm/c-aa-tool/customize-page-code.md#concept_7D6390823DFE4D29AF9505CCE1A79C3B) using the editor, you must use quotation marks.

