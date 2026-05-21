---
description: セル範囲に標準および制限付き書式を適用する方法を説明します。
title: Report Builderで日付を書式設定する方法
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 20%

---

# 日付のフォーマット

{{legacy-arb}}

Excelの書式/セル（Ctrl+1）機能で使用できる標準のセル書式設定に加えて、Report Builderを使用してセル範囲に限定された書式設定を適用できます。 これらの書式設定の選択は、選択した指標によって異なります。

行ラベルグリッドに[ディメンションを追加](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)した後、「**[!UICONTROL 書式]**」をクリックします。

「**[!UICONTROL 書式]**」メニューで、「**[!UICONTROL カスタムフォーマット]**」をクリックして、前付け／後付け機能と同様に、カスタマイズされた書式を日付に適用します。 例えば、日付の後に常に発生するテキスト（A.D. B.C.E. A.H.など）を入力できます。 [!UICONTROL 開始日]および[!UICONTROL 開始日と終了日]など、日付より前のテキストを追加できます。 さらに、日、月、年の略語からカスタム日付式を作成し、日付の一部の間にカスタム区切り記号を使用することもできます。 すべての日付形式は、括弧で囲まれた3つの略語のみで構成する必要があります。

次の表は、[!UICONTROL  カスタム形式] フィールドで日付省略形を使用する方法を示しています。

| 省略形 | 意味 | 2012年3月14日（水）を使用した例 |
|--- |--- |--- |
| MM/dd/yyy | フル数値データ | 03/14/2012 |
| M | 月数 | 3 |
| MM | 月のパディング 0 （月&lt; 10）の月数 | 03 |
| MMM | 月の短い名前 | 3 月 |
| MMMM | 月のロングネーム | 3月 |
| D | 日付のロングネーム | 2012 年 3 月 14 日水曜日 |
| d | 日数 | 14 |
| dd | 10日未満の日の0 パディングを含む日数 | 01 - 09 |
| ddd | 日の短い名前 | 水 |
| dddd | ロングネーム・オブ・デイ | 水曜日 |
| yy | 年2桁 | 10 |
| yyyy | フル 4桁の年 | 2012 |
