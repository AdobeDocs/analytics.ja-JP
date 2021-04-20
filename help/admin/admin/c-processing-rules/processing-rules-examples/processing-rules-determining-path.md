---
description: eVar の値を prop にコピーしてパス指定を有効にすることができます。
subtopic: Processing rules
title: eVar 値を prop にコピーしてパスを指定
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 100%

---

# eVar 値を prop にコピーしてパスを指定

eVar の値を prop にコピーしてパス指定を有効にすることができます。

値を設定する際、左側の変数は右側の変数からの値（空白の場合でも）を受け入れます。

| ルールセット | 値 |
|---|---|
| 条件 | なし（常に実行する） |
| アクション | prop1 の値を eVar1 で上書きする |

次のように、prop1 に値が含まれていない場合にのみ、このルールを変更して prop1 の値を設定できます。

| ルールセット | 値 |
|---|---|
| 条件 | prop1 が設定されていない場合 |
| アクション | prop1 の値を eVar1 で上書きする |

次に例を示します。

![](assets/overwrite-empty-prop.png)
