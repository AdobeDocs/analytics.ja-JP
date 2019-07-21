---
description: デバイスで JavaScript が有効、無効、不明のいずれであるかに基づいて指標を表示します。
seo-description: デバイスで JavaScript が有効、無効、不明のいずれであるかに基づいて指標を表示します。
seo-title: JavaScript サポート
solution: Analytics
title: JavaScript サポート
topic: レポート
uuid: 7b95001a- cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript サポート

デバイスで JavaScript が有効、無効、不明のいずれであるかに基づいて指標を表示します。

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

JavaScript レポートは、生データの javascript 列に対応します。

javascript は訪問レベルのフィールドであるため、訪問の最初のヒットの値をその後も保持します。javascript 列の値は、j_jscript 列の最初の値に基づきます（visit_referrer が訪問の最初のリファラーの値のみを保持するのと同様です）。

j_jscript の値は、Adobe Analytics イメージリクエストのパラメーター j から取得されます。

次に例を示します。

| ヒット | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

上記のように、最初のヒットに j_jscript の値が含まれていない場合、JavaScript は無効と表示されます。訪問のその後のヒットで JavaScript のバージョンが特定されても、無効という表示は変更されません。
