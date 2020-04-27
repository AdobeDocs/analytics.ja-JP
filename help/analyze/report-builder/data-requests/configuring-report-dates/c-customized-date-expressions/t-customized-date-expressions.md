---
description: カスタム式を作成して、複雑な日付範囲を指定することができます。
title: カスタマイズされた日付式 - 概要
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: fa1b0b7fb24d0cd2c205fbbb6a1e526f243531f8

---


# カスタマイズされた日付式 - 概要

カスタム式を作成して、複雑な日付範囲を指定することができます。

週数と日数を正しく指定するために、式の作成時にカレンダーを参照することをお勧めします。 Excel には、期間の日数、勤務日数、月数、年数を計算できる、様々なビルトイン関数があります。これらの関数を数式で使用して、週や四半期などの他の期間を計算することもできます。

**カスタム式を有効にするには**

これは、を使用した例で **[!UICONTROL Rolling Dates]**&#x200B;す。

1. で、を使用 [!UICONTROL Request Wizard: Step 1]する代わりに、を **[!UICONTROL Preset Dates]**&#x200B;選択しま **[!UICONTROL Rolling Dates]**&#x200B;す。

   ![](assets/rolldates1.png)

1. 周期的な週、月、四半期、年に切り替えます。 次のオプションがどのように変更されるかを確認します。
1. その他のカスタマイズオプションを表示するには、をクリックし **[!UICONTROL Show Advanced Options]**&#x200B;ます。

   ![](assets/rolldates2.png)

1. 例えば、上記の日付を3か月前の最初の日から今月の最初の日まで月周期に変更すると、前のオプション部分の日付自体が更新され、次のように反映されます。

   ![](assets/rolldatesfor3.png)

1. 有効にする **[!UICONTROL Customize Expression]**. のオプションを選択す **[!UICONTROL Rolling Dates]**&#x200B;ると、カスタムの日付オプションの構文を簡単に確認できます。式

   ![](assets/rolldatesfor5.png)

   「アドバンスオプション」を使用して、カスタムの日付オプションを組み合わせることができます。式 例えば、年の初めから最後の月の終わりまでのデータを表示する場合は、次のように入力します。 `From: cy``To: cm-1d`. ウィザードでは、これらの日付は2020年1月1日 — 1/31/2020と表示されます。
