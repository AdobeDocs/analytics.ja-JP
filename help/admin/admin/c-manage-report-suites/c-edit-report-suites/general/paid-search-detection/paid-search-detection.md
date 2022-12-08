---
description: 有料検索検知は、検索エンジンと検索キーワードレポート内の自然検索と有料検索を区別します。
title: 有料検索検知
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---

# 有料検索検知

[!UICONTROL 有料検索検知]は、[!UICONTROL 検索エンジン]と[!UICONTROL 検索キーワード]レポート内の自然検索と有料検索を区別します。有料広告を使用する検索エンジンを指定し、有料広告から訪問した URL 内で見つかった文字列を指定できます。

## 設定オプション {#section_0C2CFA0AF77B47098BE37CB024665D0D}

次の表に、[有料検索検知を設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)する際に使用するフィールドとオプションを示します。

| オプション | 説明 |
| --- | --- |
| [!UICONTROL 検索エンジン] | ドロップダウンリストから検索エンジンを選択します。検索エンジンごとに異なるクエリー文字列パラメーターを使用する場合は、エンジンを指定します。通常は、値 `Any` で十分です。 |
| [!UICONTROL クエリ文字列] | 大文字と小文字を区別してクエリ文字列パラメーター（URL の「?」以降の部分）の任意の部分と一致させる文字列を指定します。<br>**メモ**：[!UICONTROL 有料検索検知]では大文字と小文字が区別されます。例えば、クエリ文字列パラメーターとして「PID」を指定するルールは「pid」とは一致しません。組織が大文字と小文字を混在使用している場合、正確な値を別々のルールとして設定し、必要なすべてのクエリ文字列パラメーターが対象になるようにします。 |
