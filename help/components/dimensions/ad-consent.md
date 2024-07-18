---
title: 広告プラットフォームの同意
description: サードパーティの広告プロバイダーに対する広告の同意の設定を参照してください。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
source-git-commit: 5df5cffbb6abf712cb36fd807ef54b8ebaae1c73
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# 広告プラットフォームの同意

「Ad Platform の同意 [ ディメンション ](overview.md) には、Google、Meta などのサードパーティ広告プロバイダーにデータを送信するために同意が収集されるかどうかが表示されます。

現在、このディメンションは、Googleでのみ使用されています。 欧州のプライバシー規制であるデジタル市場法（DMA）により、Googleは、自社のサーバーに送信され、欧州で収集されるデータには、同意が収集されるかどうかを示す必要があることを求めています。 一部の Analytics のお客様は、イベントデータをコンバージョンイベントとしてAdobe Advertising経由でGoogleに送信しています。

将来的には、このディメンションを使用して、他のサードパーティ広告プロバイダーの追加の同意情報のエンコーディングをサポートすることができます。

## このディメンションへのデータ入力

このディメンションは、次の [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md) からデータを収集します

* `contextData.['adConsent']`

コンテキストデータ変数には、Googleの同意フィールドの関連する値を入力します

* `ad_user_data` （最初の文字）と
* `ad_personalization` （2 番目の文字）。

詳しくは、[Google Ads API リファレンスの同意 ](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) を参照してください。

これらの各フィールドに指定可能な値は次のとおりです。

| 値 | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | 広告ユーザーデータに対するGoogleへの同意の付与。 | 広告のパーソナライゼーションに関するGoogleへの同意の付与。 |
| `N` | 広告ユーザーデータに関するGoogleへの同意を拒否します。 | 広告のパーソナライゼーションについて、Googleに同意していることを示します。 |
| `U` | 未指定。 | 未指定。 |

次の例では、広告ユーザーデータにはGoogleの同意を付与しますが、広告のパーソナライゼーションには同意しません。

```
contextData.['adConsent'] = "YN..."
```

現在、1 文字目と 2 文字目より後の文字は無視されます。

## データの使用

収集された広告同意データを使用できます。

* データフィード：広告の同意データは、`dataprivacydmaconsent` [ 列 ](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) を使用して利用できます。
* Data Warehouseレポート：広告の同意データは、**[!UICONTROL Ad Platform の同意]** ディメンションを使用して利用できます。

このコンテキストデータ変数を実装するためのロジックは、組織が決定します。 値は、設定されたヒットを超えて保持されないので、各ページでコンテキストデータ変数を設定する必要があります。

広告データをAdobe Advertising経由でAdobe AnalyticsからGoogleにコンバージョンイベントとして送信する場合は、Adobe Advertisingチームに相談して統合を支援してください。

詳しくは、[ プライバシーレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) を参照してください。
