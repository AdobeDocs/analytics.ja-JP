---
title: 初回購入までの日数
description: 訪問者の初回訪問から初回購入までの日数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---

# 初回購入までの日数

「初回購入までの日数」ディメンションは、訪問者してから最終的に購入するまでの日数をレポートします。例えば、訪問者が最初の訪問の 1 日後に購入した場合、それ以降の訪問またはイベントはすべて「1 日」ディメンション項目に属します。

最初に購入した後、その訪問者は cookie の有効期間が切れるまで同じディメンション項目に属します。

## このディメンションへのデータ入力

アドビは、実装の [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) イベントに基づいて、このディメンションを自動的に設定します。サイトに `purchase` イベントを実装する場合、このディメンションは常に機能します。

## ディメンション項目

ディメンション項目には、訪問者がサイトを初めて訪問してから最初に購入するまでの日数が含まれます。各日数は個別のディメンション項目です。「同じ日」は、訪問者の初回訪問と初回購入が同じ日に発生した場合に発生します。
