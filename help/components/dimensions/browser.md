---
title: ブラウザー
description: 使用されたブラウザーの名前とバージョン。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 35%
---
# ブラウザー

&#39;[!UICONTROL  ブラウザー]&#39; [ ディメンション ](overview.md)は、ヒットを送信するブラウザーの名前とバージョンを報告します。 このディメンションは、訪問者が最もよく使用するブラウザーを測定したい場合に便利です。 サイトの新しいバージョンをテストする場合、このディメンションの上位ブラウザーでテストを実行することで、品質管理を最大限に高めることができます。

## このディメンションへのデータ入力

Adobeは、このディメンションを`User-Agent` HTTP ヘッダーから取得し、Adobeが[DeviceAtlas](https://deviceatlas.com/)と連携して保持する内部ルックアップテーブルと照合します。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（ユーザーエージェントから派生） |
| **Web SDK / XDM フィールド** | なし（ユーザーエージェントから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[ データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、使用するブラウザー名とバージョンが含まれます。 同じブラウザーの異なるバージョンは、別々のディメンション項目です。

一部のディメンション項目には、バージョン番号の代わりに `"(unknown version)"` が含まれます。 このディメンション項目は、Adobeがまだルックアップテーブルに追加していない最近のブラウザーリリースを参照しています。 ブラウザーは頻繁に更新されるので、特定のブラウザーの `"(unknown version)"` は、共通で一時的なものです。 アドビは通常、月次メンテナンスリリース時に参照テーブルを更新します。

一部のディメンション項目には、マイナーバージョン番号として`.999`が含まれています（`"Chrome 148.999"`など）。 この値は、Adobeがブラウザーのマイナーバージョンを確実に判断できなかったことを示します。 ChromeまたはEdge ブラウザーが[ クライアントヒント ](/help/technotes/client-hints.md)なしでリクエストを送信する場合、ユーザーエージェント文字列内のマイナーバージョンは信頼できないと見なされます。 不正確なマイナーバージョンを持つ可能性のあるディメンション項目を膨らませる代わりに、Adobeはこれらのマイナーバージョンを`.999`に置き換えます。 同様に、ブラウザーで異常に高いバージョン番号（99999上）が報告された場合、Adobeはそれを`999.999`に正規化します。
