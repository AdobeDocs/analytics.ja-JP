---
description: 有料検索検知は、検索エンジンと検索キーワードレポート内の自然検索と有料検索を区別します。
title: 有料検索検知
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
TQID: https://experienceleague.adobe.com/g26-86nQZ-k3kaID-Dq6qbwYkdqLpHDdUEswP-p361Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 95%

---

# 有料検索検知

[!UICONTROL 有料検索検知]は、[!UICONTROL 検索エンジン]と[!UICONTROL 検索キーワード]レポート内の自然検索と有料検索を区別します。 有料広告を使用する検索エンジンを指定し、有料広告から訪問した URL 内で見つかった文字列を指定できます。

## 設定オプション {#configuration}

次の表に、[有料検索検知を設定](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)する際に使用するフィールドとオプションを示します。

| オプション | 説明 |
| --- | --- |
| [!UICONTROL 検索エンジン] | ドロップダウンリストから検索エンジンを選択します。 検索エンジンごとに異なるクエリ文字列パラメーターを使用する場合は、エンジンを指定します。 通常は、値 `Any` で十分です。 |
| [!UICONTROL クエリ文字列] | 大文字と小文字を区別してクエリ文字列パラメーター（URL の「?」以降の部分）の任意の部分と一致させる文字列を指定します。 <br>**メモ**：[!UICONTROL 有料検索検知]では大文字と小文字が区別されます。 例えば、クエリ文字列パラメーターとして「PID」を指定するルールは「pid」とは一致しません。 組織が大文字と小文字を混在使用している場合、正確な値を別々のルールとして設定し、必要なすべてのクエリ文字列パラメーターが対象になるようにします。 |
