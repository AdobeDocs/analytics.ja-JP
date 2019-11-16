---
description: 未分類のキーは、「なし」というラベルの付いた単一の行項目として、まとめて分類レポートにグループ化されます。「なし」を分かりやすいラベルに変更すると便利です。
solution: Analytics
subtopic: Classifications
title: 未分類のキー
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 未分類のキー

未分類のキーは、「なし」というラベルの付いた単一の行項目として、まとめて分類レポートにグループ化されます。「なし」を分かりやすいラベルに変更すると便利です。

## 未分類のキー {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Non-classified keys are grouped together in classification reports as a single line item labeled *`None`*. It can be useful to rename *`None`* to something more descriptive.

例えば、トラッキングコードが関連付けられているモバイルキャンペーンのタイプを説明する情報が、トラッキングコードに含まれているとします。分類（モバイルキャンペーンタイプ）を使用し、これらのトラッキングコードを、モバイル用 Web、iOS アプリケーション、Android アプリケーションなどの分類にグループ化します。一部のキャンペーンは、モバイルキャンペーンではないのでモバイルキャンペータイプで分類されない可能性があります。すべての未分類のトラッキングコードは「*`None`*&#x200B;という名前に変更され、[!UICONTROL モバイルキャンペーンタイプ]レポートに反映されます。

## 「なし」分類キーの名前変更{#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. インポーターを使用して、ローカルファイルに分類をエクスポートします。
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. 追加した行の分類列に、内容の説明になる名前を入力します。

   この文書の例であれば、[!UICONTROL モバイルキャンペーン名]という名前の列に「モバイルキャンペーン対象外」と入力することが考えられます。

   この入力によって、 *`None`* to *`non-mobile campaign`* in the [!UICONTROL Mobile Campaign Type] report.
1. [データをシステムにインポート](/help/components/c-classifications2/c-classifications-importer/import-file.md)します。
