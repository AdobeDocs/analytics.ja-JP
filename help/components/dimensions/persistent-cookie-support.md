---
title: 永続的な cookie のサポート
description: 訪問者が永続的な cookie をサポートできるかどうかを指定します。
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 90%

---

# 永続的な cookie のサポート

「永続的なCookie サポート」の[ ディメンション ](overview.md)は、ヒットが永続的なソースから発生した訪問者識別子を使用したかどうかを示します。 最も一般的な永続的なソースは cookie からのものですが、モバイルヘッダーや他のソースも使用できます。

## このディメンションへのデータ入力

アドビは、ヒットの識別子のソースに基づいて、このディメンションの値をサーバーサイドで決定します。 直接設定することはできません。 これは、すべての実装で初期設定の状態で動作します。

## ディメンション項目

* **`Enabled`**：ヒットの訪問者識別子は、通常は永続的であるソースから取得されます。 最も一般的な例としては、 `aid`、`fid` または `mid` の各クエリ文字列パラメーターがあり、これらは cookie から値を導き出します。
* **`Disabled`**：ヒットの訪問者識別子は、IP + ユーザーエージェント文字列などのように、アドビが永続的と認識しないソースから取得されます。 このディメンション項目には、[`visitorID`](/help/implement/vars/config-vars/visitorid.md) 変数を使用したカスタム訪問者 ID も含まれます。

## 「Cookie サポート」と「永続的な Cookie のサポート」の違い

* **Cookie サポート**：AppMeasurement は汎用 cookie の設定を試みます。 ディメンション項目は、cookie が正常に設定されたかどうかを基にします。
* **永続的な cookie のサポート**：ディメンション項目は、ヒットの識別子が永続的なソース（cookie など）から生成されたものかどうかに基づきます。
