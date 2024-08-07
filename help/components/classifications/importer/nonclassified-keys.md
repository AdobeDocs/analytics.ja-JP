---
description: 未分類のキーは、「なし」というラベルの付いた単一の行項目として、分類レポートにグループ化されます。「なし」を分かりやすいラベルに変更すると便利です。
title: 未分類のキー
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# 未分類のキー

未分類のキーは、「なし」というラベルの付いた単一の行項目として、分類レポートにグループ化されます。「なし」を分かりやすいラベルに変更すると便利です。

## 未分類のキー {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分類のキーは、「*`None`*」というラベルの付いた単一の行項目として、分類レポートにグループ化されます。「*`None`*」を分かりやすいラベルに変更すると便利です。

例えば、トラッキングコードが関連付けられているモバイルキャンペーンのタイプを説明する情報が、トラッキングコードに含まれているとします。分類（モバイルキャンペーンタイプ）を使用し、これらのトラッキングコードを、モバイル用 Web、iOS アプリケーション、Android アプリケーションなどの分類にグループ化します。一部のキャンペーンは、モバイルキャンペーンではないのでモバイルキャンペータイプで分類されない可能性があります。未分類のトラッキングコードはすべて、[!UICONTROL  モバイルキャンペーンタイプ ] レポートの *`None`* の下にグループ化されます。

## 「なし」分類キーの名前変更  {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

レポートで *`none`* と表示される未分類のキーの名前を変更するには：

1. インポーターを使用して、ローカルファイルに分類を書き出します。
1. ファイルに行を追加し、キー列に `~none~` と入力します。
1. 追加した行の分類列に、内容の説明になる名前を入力します。

   この文書の例であれば、[!UICONTROL モバイルキャンペーンタイプ]という名前の列に「モバイルキャンペーン対象外」と入力することが考えられます。

   このエントリは、[!UICONTROL モバイルキャンペーンタイプ]レポートで *`None`* の名前を *`non-mobile campaign`* に変更します。

   ![未分類のキーの例](/help/components/classifications/importer/assets/non-classified-key.png)

1. [データをシステムにインポート](/help/components/classifications/importer/import-file.md)します。
