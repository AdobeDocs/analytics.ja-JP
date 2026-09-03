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
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 34%

---

# ヒットタイプ

「ヒットの種類」 [ ディメンション ](overview.md)は、ヒットがAdobe データ収集サーバーに送信されたときに、モバイルアプリが前景または背景にあるかどうかを判断します。 このディメンションは、モバイルアプリケーション用のデータを含むレポートスイートにのみ関連します。 AppMeasurementを通じて収集されたブラウザーデータでは、ヒットは常に`"Foreground"`と報告されます。

## このディメンションへのデータ入力

このディメンションは、バージョン 4.13.6 以降でのすべてのモバイル SDK 実装で初期設定のまま機能します。 モバイル SDKは、各ヒットが前景または背景のどちらに発生したかを示すために、[`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md)変数（`cp` クエリパラメーター）を設定します。 モバイル SDKを使用しない場合は、`"Foreground"`の下のすべてのヒットが一覧表示されます。 [仮想レポートスイート ](../vrs/vrs-mobile-visit-processing.md)の設定時に&#x200B;**[!UICONTROL バックグラウンドヒットによる新しい訪問の開始を防止]**&#x200B;が選択されている場合、バックグラウンドヒットによって[[!UICONTROL 訪問]](../metrics/visits.md)と[[!UICONTROL  ユニーク訪問者]](../metrics/unique-visitors.md)が膨らむことはありません。

## ディメンション項目

ディメンション項目には、`"Foreground"` および `"Background"` が含まれます。 バックグラウンドヒットは、トラッキング対象のアプリケーションがバックグラウンドにあるモバイルデバイスでのみ発生します。
