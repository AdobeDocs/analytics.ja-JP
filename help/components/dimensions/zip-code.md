---
title: 郵便番号
description: 訪問者の郵便番号（ZIP コード）。
feature: Dimensions
exl-id: 597619f8-a581-4491-beb2-c14b1f7b7bec
TQID: https://experienceleague.adobe.com/XHrUXKHrXiH0wsUr0klmPmA-DEq5T5yu18KLNT7oYeo
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
source-wordcount: '330'
ht-degree: 61%
---
# 郵便番号

「郵便番号」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者の郵便番号を報告します。 このディメンションを使用して、ローカル広告の成功についての詳細を理解したり、サイトのパフォーマンスが世界のどこで最も高いかを確認したりできます。

## このディメンションへのデータ入力

このディメンションは、データを入力する方法が複数ある点で独自です。 次のいずれかを使用するか、両方を組み合わせて使用できます。

* [`zip`](/help/implement/vars/page-vars/zip.md)変数を使用して直接郵便番号を設定します。
* 位置情報データから取得するように設定します。 geo zipを使用する場合、変数は設定されません。 AppMeasurementの実装では、このディメンションはそのまま機能します。 Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Geo Lookup]を有効にします。

「[!UICONTROL 一般的なアカウント設定]」の「[郵便番号](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)」オプションは、このディメンションに入力する方法を制御します。 以下の参照テーブルは、`zip`変数を直接設定する場合に適用されます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`zip`](/help/implement/vars/page-vars/zip.md) |
| **Web SDK / XDM フィールド** | [`placeContext.geo.postalCode`](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/data-types/geo) |
| **クエリパラメーター** | [`zip`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<zip>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 50 バイト |
| **永続性** | ヒット |

## ディメンション項目

ディメンション項目には、訪問者の郵便番号または郵便コードが含まれます。

## 郵便番号（postal code）がサポートされている国

* オーランド諸島
* アルバニア
* アルジェリア
* アルゼンチン
* アルメニア
* オーストリア
* オーストラリア
* バングラデシュ
* バルバドス
* ベルギー
* ブラジル
* ブルガリア
* カナダ
* チリ
* 中国
* コロンビア
* コスタリカ
* クロアチア
* チェコ共和国
* デンマーク
* エクアドル
* エジプト
* エストニア
* フィンランド
* フランス
* グルジア
* ドイツ
* ジブラルタル
* ギリシャ
* グレナダ
* グアテマラ
* 香港特別行政区
* ハンガリー
* インド
* インドネシア
* アイルランド
* イスラエル
* イタリア
* 日本
* ヨルダン
* カザフスタン
* キルギスタン
* ラトビア
* レバノン
* リトアニア
* ルクセンブルグ
* マレーシア
* マルタ
* モーリシャス
* メキシコ
* モロッコ
* モザンビーク
* ネパール
* オランダ
* ニュージーランド
* ノルウェー
* パキスタン
* パナマ
* ペルー
* フィリピン
* ポーランド
* ポルトガル
* プエルトリコ
* カタール
* ルーマニア
* ロシア連邦
* サウジアラビア
* セネガル
* セルビア
* シンガポール
* スロベニア
* 南アフリカ
* 韓国
* スペイン
* スリランカ
* スウェーデン
* スイス
* 台湾地域
* タイ
* チュニジア
* トルコ
* ウクライナ
* アラブ首長国連邦
* 英国
* 米国
* ウルグアイ
* ウズベキスタン
* ベネズエラ
* ベトナム
