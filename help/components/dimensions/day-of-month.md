---
title: 月間通算日
description: 月を問わず、月間通算日を数値で表します。
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
TQID: https://experienceleague.adobe.com/jSrKlf4a5f-6MTrQwwUcvRJep4chAUyOsj5hFjE1HRg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 140
ht-degree: 87%

---

# 月間通算日

「月の日」ディメンション [1&rbrace;は、任意の月の数値をディメンション項目としてレポートします。 &#x200B;](overview.md)例えば、1 月 1 日から 3 月 31 日のレポートがある場合、各月の最初の月は同じディメンション項目にグループ化されます。 このレポートは、日別にレポートを分類するが、ディメンション項目として静的な日数を必要としない場合に役立ちます。 このディメンションは、選択した日付範囲でロールするので、予定レポートのディメンションとして特に役立ちます。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。 レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

ディメンション項目には、ヒットが発生した日を表す数字 `1` ～ `31` が含まれます。
