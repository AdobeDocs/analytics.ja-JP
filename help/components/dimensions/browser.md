---
title: ブラウザー
description: 使用されたブラウザーの名前とバージョン。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 59%

---

# ブラウザー

&#39;[!UICONTROL &#x200B; ブラウザー]&#39; [&#x200B; ディメンション &#x200B;](overview.md)は、ヒットを送信するブラウザーの名前とバージョンを報告します。 このディメンションは、訪問者が最もよく使用するブラウザーを測定したい場合に便利です。 サイトの新しいバージョンをテストする場合、このディメンションのトップブラウザーでテストを実行し、品質管理の取り組みを最大限に活かすことができます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。 Adobeは[DeviceAtlas](https://deviceatlas.com/)と提携して、ユーザーエージェントとブラウザー間のルックアップを管理します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、使用するブラウザー名とバージョンが含まれます。 同じブラウザーの異なるバージョンは、別々のディメンション項目です。

一部のディメンション項目には、バージョン番号の代わりに `"(unknown version)"` が含まれます。 このディメンション項目は、Adobeがまだルックアップテーブルに追加していない最近のブラウザーリリースを参照しています。 ブラウザーは頻繁に更新されるので、特定のブラウザーの `"(unknown version)"` は、共通で一時的なものです。 アドビは、通常、月別メンテナンスリリース時に参照テーブルを更新します。