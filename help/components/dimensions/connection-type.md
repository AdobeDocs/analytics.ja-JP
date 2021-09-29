---
title: 接続タイプ
description: 訪問者がインターネットに接続する方法。
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# 接続タイプ

「接続タイプ」ディメンションは、訪問者がインターネットに接続した方法を示します。 このディメンションは、訪問者がサイトを閲覧する際にどのようにインターネットに接続するかを判断するのに役立ちます。 これを使用して、訪問者の接続速度に基づいてサイトのコンテンツを最適化できます。

## このディメンションへのデータ入力

このディメンションでは、[`ct` クエリ文字列 ](/help/implement/validate/query-parameters.md) とAdobeサーバー側ロジックの組み合わせを使用します。 Adobeは、値を決定するために次のルールを使用します。

1. `ct` クエリ文字列が `"modem"` に等しい場合は、ディメンション項目を `"Modem"` に設定します。 AppMeasurement は、サポートされていない Internet Explorer ブラウザーでのみこのデータを収集し、このディメンション項目は一般的ではありません。
1. ヒットの IP アドレスを確認し、Adobe内部のルックアップテーブルを参照します。 IP アドレスが携帯電話会社からのものである場合は、ディメンション項目を `"Mobile Carrier"` に設定します。
1. `ct` クエリ文字列が `"lan"` に等しい場合は、ディメンション項目を `"LAN/Wifi"` に設定します。
1. ヒットが [ データソース ](/help/import/c-data-sources/datasrc-home.md) から発生した場合、または特別なタイプのヒットと見なされる場合は、ディメンション項目を `"Not specified"` に設定します。
1. 上記の規則がいずれも満たされない場合、デフォルト値は `"LAN/Wifi"` です。

## ディメンション項目

Dimension項目には、`LAN/Wifi`、`Mobile Carrier`、`Modem`、`Not Specified` が含まれます。

* **`LAN/Wifi`**:訪問者が固定回線または Wi-Fi ホットスポットを通じてインターネットに接続した。
* **`Mobile Carrier`**:訪問者が携帯電話会社を通じてインターネットに接続した。
* **`Modem`**:訪問者が、サポートされていない Internet Explorer ブラウザーのモデムを介してインターネットに接続した。
* **`Not Specified`**:ヒットに接続タイプがありませんでした。
