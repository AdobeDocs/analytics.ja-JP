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

週数と日数を正しく指定するために、式を作成する際にカレンダーを参照することをお勧めします。 Excel には、期間の日数、勤務日数、月数、年数を計算できる、様々なビルトイン関数があります。これらの関数を数式で使用して、週や四半期などの他の期間を計算することもできます。

**カスタム式を有効にするには**

これは、の使用例です **[!UICONTROL Rolling Dates]**。

1. で、を使 [!UICONTROL Request Wizard: Step 1]用する代わりにを選 **[!UICONTROL Preset Dates]**&#x200B;択します **[!UICONTROL Rolling Dates]**。

   ![](assets/rolldates1.png)

1. 周期的な週単位、月単位、四半期単位、年単位に切り替えます。 次のオプションが変更されます。
1. その他のカスタマイズオプションを表示するには、をクリックし **[!UICONTROL Show Advanced Options]**&#x200B;ます。

   ![](assets/rolldates2.png)

1. 例えば、上記の日付を3か月前の最初の日から今月の初日まで月周期に変更すると、「前」オプション部分の日付が次のように更新されます。

   ![](assets/rolldatesfor3.png)

1. 有効にする **[!UICONTROL Customize Expression]**. のオプションを選択す **[!UICONTROL Rolling Dates]**&#x200B;ると、カスタム日付式の構文を簡単に確認できます。

   ![](assets/rolldatesfor5.png)

   「アドバンスオプション」を使用して、カスタムの日付式を組み合わせることができます。 例えば、年の初めから最後の月の終わりまでのデータを表示する場合は、次のように入力します。 `From: cy``To: cm-1d`. ウィザードでは、これらの日付は2020年1月1日 — 1/31/2020と表示されます。
