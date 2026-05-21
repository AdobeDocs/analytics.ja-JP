---
title: 一意のデバイス
description: 一意のデバイスの数。
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
TQID: https://experienceleague.adobe.com/7KUpaGPuFGBHTXj8L4MKnjOsi1YQtA8KUCIXSa-NtXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 73%

---

# 一意のデバイス

「一意のデバイス」指標[指標](overview.md)は、一意の未識別のデバイスと一意の仮想デバイスの数をカウントする[ クロスデバイス分析](../cda/overview.md)指標です。 未識別のデバイスとは、匿名のヒットを生成したデバイスのことです。 一意の仮想デバイスとは、デバイスごとに識別される個別のユーザーです。

## この指標の計算方法

各デバイスに関連付けられているすべての個別のユーザーを合計します（デバイスにステッチされていないヒットが含まれている場合は匿名を含む）。

この指標は、CDA 以外のレポートスイートの[ユニーク訪問者](unique-visitors.md)とは一致しません。 例えば、3 つの異なるアカウントが 1 つのデバイスを共有しているとします。 3つのアカウントがすべてレポートウィンドウでサイトにアクセスした場合、レポートには3つの一意のデバイスがCDAに表示されます。 CDA 以外の同じデータでは、ユニーク訪問者が 1 人と表示されます。

## 例

1. Sallyは広告を通じて電話でサイトにアクセスしましたが、ログインしていません。
1. Sally は既にログインしている家族用コンピューターで購入したいと思っています。 彼女は家族用コンピューターで購入します。
1. 次の日、彼女は携帯電話で注文を確認し、そこで認証します。
1. Bob の妻である Alice は、家族用コンピューターで自身のアカウントにログイン中、サイトを閲覧します。
1. Bob の弟である Charles も、家族用コンピューターで自身のアカウント中、サイトを閲覧します。

![一意のデバイス数](/help/components/metrics/assets/Unique_Devices_Count.png)

CDA 仮想レポートスイートでこのデータを表示すると、[再生](/help/components/cda/replay.md)で未認証のヒットをステッチする可能性があり、次のように表示されます。

* **一意のデバイス 5 台**：Bob（未認証）1 台 + Bob 2 台 + Alice 1 台 + Charles 1 台
* **4 人の[ユーザー](people.md)**：1 人の[識別済みユーザー](unidentified-people.md) + 3 人の[未識別のユーザー](identified-people.md)
