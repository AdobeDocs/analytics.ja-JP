---
title: 仮想レポートスイートを特定の日付に制限
description: 仮想レポートスイートの日付範囲をステッチされたデータのみに限定する方法について説明します。
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 41%

---

# 仮想レポートスイートを特定の日付に制限

{{available-existing-customers}}

ステッチをオンにすると、特定の日付にステッチが始まります。 その日付が 6 月 1 日だと仮定しましょう。 CDA仮想レポートスイートには、6月1日より前に未結合データが含まれます。 6月1日より前にバーチャルレポートスイートのデータを非表示にして、ステッチ開始後に分析を日付範囲に集中させることができます。

仮想レポートスイートのデータを特定の日付に制限するには、次の操作を行います。

## 手順1：日次ローリング日付範囲を含む仮想レポートスイートの作成

仮想レポートスイートを設定する場合、「コンポーネント」の下に、日次ローリング日付範囲を持つ固定開始の日付範囲を追加します。 開始日固定は、ステッチを開始した日にする必要があります。

![](assets/rolling-daily.png)

## 手順 2：「除外 - 除外」セグメントの作成

次に、別の除外コンテナ内の除外コンテナに日付範囲を配置するヒットセグメントを作成します。 これは「除外する」ことです。

「除外された除外」の理由は、日付範囲がレポートの日付範囲を上書きするためです。 したがって、6 月 1 日以降を含めると、レポートの日付範囲は常に 6 月 1 日以降になります。 これは望ましくない結果につながります。 「除外を除外」すると、この動作が上書きされ、取得できるデータが適切な日付範囲に制限されます。

![](assets/exclude-exclude.png)

## 手順3：このセグメントをクロスデバイス Analytics仮想レポートスイートに適用する

![](assets/apply-segment.png)

## 手順 4：結果をレポートで確認

レポートは、ステッチが最初に実装された日と同じ日の、目的の日付に開始します。

![](assets/report-limited-dates.png)
