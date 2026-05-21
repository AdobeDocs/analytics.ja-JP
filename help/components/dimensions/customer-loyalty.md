---
title: 顧客の忠誠度
description: 訪問者が以前におこなった購入の数に基づくカテゴリ。
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 88%

---

# 顧客の忠誠度

「顧客ロイヤルティ」 [ ディメンション ](overview.md)は、サイトへの訪問者のうち、0件の事前購入、1件の事前購入、2件の事前購入、または3件以上の事前購入を行った訪問者の数を報告します。 このディメンションは、サイトが購入行動に与える影響を理解するうえで役立ちます。 また、このディメンションをセグメントで使用して、再購入する訪問者に焦点を当てることもできるので、新しい訪問者に対しても同様の動作を奨励できます。

## このディメンションへのデータ入力

アドビは、実装の [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) イベントに基づいて、このディメンションを自動的に設定します。 サイトに `purchase` イベントを実装する場合、このディメンションは常に機能します。

## ディメンション項目

ディメンション項目は次のとおりです。

* **非顧客**：ヒットの時点で、訪問者はこれまでに購入したことがありません。
* **新規顧客**:：ヒットの時点で、訪問者が以前に 1 回購入しました。
* **リターン顧客**:：ヒットの時点で、訪問者が以前に 2 回購入しました。
* **常連客**：ヒットの時点で、訪問者が以前に 3 回以上購入しました。

訪問者が購入する（`purchase` イベントをトリガーする）と、そのヒットとそれ以降のすべてのヒットが次の「バケット」に移動します。 例えば、初めてサイトで製品を購入した訪問者は「非顧客」から「新規顧客」に移動し、その注文は「新規顧客」に分類されます。 「非顧客」の分析コード項目には、その分析コードに属する注文を含めることはできません。
