---
description: カスタム式を作成して、複雑な日付範囲を指定することができます。
title: カスタマイズされた日付式 - 概要
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 25%

---

# カスタマイズされた日付式

カスタム式を作成して、複雑な日付範囲を指定することができます。

式を作成する場合は、カレンダーを参照して、週と日数を正しく指定します。 Excel には、期間の日数、勤務日数、月数、年数を計算できる、様々なビルトイン関数があります。これらの関数を数式で使用して、週や四半期などの他の期間を計算することもできます。

**カスタム式を有効にするには**

次の例は、に対してカスタム式を有効にする方法を示しています。 **[!UICONTROL 相対日付]**.

1. 次の日： [!UICONTROL リクエストウィザード：ステップ 1]を使用する代わりに、 **[!UICONTROL 事前設定日]**&#x200B;を選択します。 **[!UICONTROL 相対日付]**.

   ![周期的な日付が選択されているスクリーンショット。](assets/rolldates1.png)

1. 週次、月次、四半期、年次の周期に切り替えます。 以下のオプションがどのように変化するかに注目してください。
1. その他のカスタマイズオプションについては、 **[!UICONTROL アドバンスオプションを表示]**.

   ![「詳細オプションを表示」をハイライトしたスクリーンショット。](assets/rolldates2.png)

1. 例えば、上の日付を月次的に 3 ヶ月前の最初の日から今月の最初の日に変更した場合、「前日」オプション部分の日付は次の内容を反映して更新されます。

   ![3 ヶ月前の最初の日から今月の最初の日までの相対日付を示すスクリーンショット。](assets/rolldatesfor3.png)

1. 有効にする **[!UICONTROL 式をカスタマイズ]**. 以下のオプションを選択します。 **[!UICONTROL 相対日付]**&#x200B;を使用すると、カスタム日付式の構文を簡単に確認できます。

   ![「式をカスタマイズ」を選択した状態で表示したスクリーンショット。](assets/rolldatesfor5.png)

   「詳細オプション」を使用して、カスタムの日付式を組み合わせることができます。 例えば、年初から過去 1 か月の終わりまでのデータを表示する場合は、次のように入力します。 `From: cy` `To: cm-1d`. ウィザードでは、これらの日付は 1/1/2020-1/31/2020と表示されます。
