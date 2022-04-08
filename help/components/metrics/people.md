---
title: People
description: 一意の個人（通常複数のデバイスを持つ人）の数。
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '161'
ht-degree: 100%

---

# People

「人」指標には 2 つのバージョンがあります。

[クロスデバイス分析](../cda/overview.md)を使用しない [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=ja) のメンバーの場合、「人」指標は、レポートで表される人の数を統計的に導き出した数です。 これは、Device Co-op で識別される訪問者 ID の数に、Co-op で識別されないデバイスの数を加えたものです。

[クロスデバイス分析](../cda/overview.md)仮想レポートスイート内では、「ユーザー」指標は統計的に導出されたものではありません。代わりに、レポートで識別された個人の合計に、個人に属していることが識別されていないデバイスの数を加えたものです。

ある訪問者が訪問中と識別された場合、その訪問者は、再生が実行されるまで、2 人としてカウントされる可能性があります（未識別のユーザー 1 人と識別済みユーザー 1 人）。[再生](/help/components/cda/replay.md)は、レポートウィンドウ、再生頻度および成功率に応じて、この二重カウントを減らします。詳しくは、[一意のデバイス](unique-devices.md)を参照してください。
