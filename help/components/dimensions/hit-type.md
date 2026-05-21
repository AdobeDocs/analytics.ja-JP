---
title: ヒットタイプ
description: ヒットがフォアグラウンドヒットかバックグラウンドヒットかを判定します。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# ヒットタイプ

「ヒットの種類」 [ ディメンション ](overview.md)は、ヒットがAdobe データ収集サーバーに送信されたときに、モバイルアプリが前景または背景にあるかどうかを判断します。 このディメンションは、モバイルアプリケーション用のデータを含むレポートスイートにのみ関連します。 AppMeasurement で収集されたブラウザーデータは、常に「フォアグラウンド」としてヒットをレポートします。

## このディメンションへのデータ入力

このディメンションは、バージョン 4.13.6 以降でのすべてのモバイル SDK 実装で初期設定のまま機能します。 モバイル SDK を使用していない場合、すべてのヒットは「フォアグラウンド」ディメンション項目下にリストされます。 「バックグラウンドのヒット数の従来のレポートおよび属性を無効にします」がオンの場合、バックグラウンドヒットは、[仮想レポートスイート](../vrs/vrs-mobile-visit-processing.md)にのみ表示されます。

## ディメンション項目

ディメンション項目には、`"Foreground"` および `"Background"` が含まれます。 モバイルアプリケーションがバックグラウンドでなかった場合に送信されたヒットは、`"Foreground"` ディメンション項目に属します。 モバイルアプリがバックグラウンドであった場所に送信されたヒットは、`"Background"` ディメンション項目に属します。
