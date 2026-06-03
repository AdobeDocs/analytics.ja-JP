---
title: ブラウザー
description: 使用されたブラウザーの名前とバージョン。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: bdd7a704c94394d6f6cedfbc07988bde69993691
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 43%

---

# ブラウザー

&#39;[!UICONTROL  ブラウザー]&#39; [ ディメンション ](overview.md)は、ヒットを送信するブラウザーの名前とバージョンを報告します。 このディメンションは、訪問者が最もよく使用するブラウザーを測定したい場合に便利です。 サイトの新しいバージョンをテストする場合、このディメンションのトップブラウザーでテストを実行し、品質管理の取り組みを最大限に活かすことができます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。 Adobeは[DeviceAtlas](https://deviceatlas.com/)と提携して、ユーザーエージェントとブラウザー間のルックアップを管理します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[ データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、使用するブラウザー名とバージョンが含まれます。 同じブラウザーの異なるバージョンは、別々のディメンション項目です。

一部のディメンション項目には、バージョン番号の代わりに `"(unknown version)"` が含まれます。 このディメンション項目は、Adobeがまだルックアップテーブルに追加していない最近のブラウザーリリースを参照しています。 ブラウザーは頻繁に更新されるので、特定のブラウザーの `"(unknown version)"` は、共通で一時的なものです。 アドビは、通常、月別メンテナンスリリース時に参照テーブルを更新します。

一部のディメンション項目には、マイナーバージョン番号として`.999`が含まれています（`"Chrome 148.999"`など）。 この値は、Adobeがブラウザーのマイナーバージョンを確実に判断できなかったことを示します。 ChromeまたはEdge ブラウザーが[ クライアントヒント ](/help/technotes/client-hints.md)なしでリクエストを送信する場合、ユーザーエージェント文字列内のマイナーバージョンは信頼できないと見なされます。 不正確なマイナーバージョンを持つ可能性のあるディメンション項目を膨らませる代わりに、Adobeはこれらのマイナーバージョンを`.999`に置き換えます。 同様に、ブラウザーで異常に高いバージョン番号（99999上）が報告された場合、Adobeはそれを`999.999`に正規化します。
