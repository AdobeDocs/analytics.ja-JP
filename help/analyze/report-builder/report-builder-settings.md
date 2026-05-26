---
title: Report Builderの設定
description: Report Builderの設定を行う方法について説明します。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
TQID: https://experienceleague.adobe.com/aHEmYs37KDXtaoAbFiI6WBCvmdhN0RrMWDl-CeEotKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: f571897740322c1f10255c54fbf745091752a507
workflow-type: tm+mt
source-wordcount: 285
ht-degree: 24%

---

# Report Builder の設定


「**設定**」ペインを使用して、UI で表示される言語やオフラインモードで動作するかどうかなど、アプリケーションレベルの設定を行います。 設定は直ちに適用され、変更されるまで、今後のすべてのセッションに対して設定されます。

Report Builder 設定を変更するには

1. **設定** アイコンを選択します。

1. オフライン モードを無効にする[有効にする](#off-line-mode)、[言語を選択](#language)または[&#x200B; トラブルシューティングを有効にする](#troubleshooting)に変更を加えます。

1. 「**[!UICONTROL 適用]**」を選択します。

   ![Report Builderの日付範囲ペインに「キャンセルして適用」ボタンが表示されている。](./assets/report-builder-settings.png){zoomable="yes"}

## オフラインモード

オフラインモードでデータブロックを作成および編集する場合、データは取得されません。 代わりに、シミュレーションデータを使用して、リクエストの実行を待たずに迅速に作業できるようにします。 オンラインに戻ったら、![更新](/help/assets/icons/Refresh.svg) **[!UICONTROL データブロックを更新]**&#x200B;または![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL すべてのデータブロックを更新]**&#x200B;し、実際のデータでデータブロックを更新します。

オフラインモードを有効にするには

1. 「![設定](/help/assets/icons/Setting.svg)」を選択します。

1. **[!UICONTROL オフライン モードを有効にする]**&#x200B;をオンに切り替えます。

1. **[!UICONTROL 指標データ]**&#x200B;のフィールドに正の整数を入力します。

1. 「**[!UICONTROL 適用]**」を選択します。


## 言語

Report Builder インターフェイスの言語を選択できます。 サポートされているすべてのCustomer Journey Analytics言語を使用できます。

Report Builder インターフェイスで使用する言語を選択するには：

1. **[!UICONTROL 言語]** ドロップダウンメニューから言語を選択します。

1. **適用を選択します。**

## トラブルシューティング

サポートチケットのトラブルシューティングとヘルプで、Report Builder リクエストのログ記録を有効にします。 **[!UICONTROL Report Builder]** パネルで、次の操作を行います。

1. 「![設定](/help/assets/icons/Setting.svg)」を選択します。
1. 「**[!UICONTROL Report Builder リクエストデータブロックをweb コンソールに記録]**&#x200B;します。 <br/> リクエストはweb ブラウザーコンソールに送信されます。 Web ブラウザーの開発者向けツールの一部として、コンソールログを開く方法については、web ブラウザーのドキュメントを参照してください。
