---
title: 広告プラットフォームの同意
description: サードパーティの広告プロバイダーの広告の同意に関する設定を参照してください。
feature: Dimensions
source-git-commit: 043f2c2b2e3e50570e2f0367680274a1f2670492
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# 広告プラットフォームの同意

「広告プラットフォームの同意」 [ディメンション](overview.md) は、Google、Meta などのサードパーティの広告プロバイダーにデータを送信するために同意を収集するかどうかを表示します。

現在、このディメンションはGoogleに対してのみ使用されています。 Googleでは、プライバシーに関する規制 (DMA) がヨーロッパで定められているので、では自社のサーバーに送信され、ヨーロッパで収集されたデータに同意が収集されたかどうかを示す必要があります。 Analytics の一部のお客様は、イベントデータをコンバージョンイベントとしてAdobe Advertising経由でGoogleに送信します。

今後、このディメンションは、他のサードパーティの広告プロバイダーに対する追加の同意情報のエンコードをサポートするために使用できます。

## このディメンションへのデータ入力

このディメンションは、次のデータを収集します [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

コンテキストデータ変数に、Google同意フィールドに関連する値を入力します

* `ad_user_data` （1 文字目）と
* `ad_personalization` （2 文字目）

詳しくは、 [Google Ads API リファレンスの同意](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) を参照してください。

これらの各フィールドに指定できる値は次のとおりです。

| 値 | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | 広告ユーザーデータに対してGoogleに同意します。 | 広告のパーソナライゼーションに関するGoogleの同意を得ます。 |
| `N` | 広告ユーザーデータに対するGoogleの同意を拒否します。 | 広告のパーソナライゼーションに対するGoogleへの拒否の同意。 |
| `U` | 未指定。 | 未指定。 |

次の例では、広告ユーザーデータに対するGoogleに対する同意を許可しますが、広告のパーソナライゼーションに対する同意は許可しません。

```
contextData.['adConsent'] = "YN..."
```

最初と 2 番目の文字を超える文字は現在、無視されます。

## データを使用

収集された広告同意データは以下の場合に使用できます。

* データフィード：広告の同意データは、 `dataprivacydmaconsent` [列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Data Warehouseレポート：広告の同意データは、 **[!UICONTROL 広告プラットフォームの同意]** ディメンション。

組織は、このコンテキストデータ変数を実装するロジックを決定します。 この値は、設定されたヒットの後は保持されないので、各ページでコンテキストデータ変数を設定する必要があります。

Adobe Advertising経由でAdobe Analyticsから広告データをコンバージョンイベントとしてGoogleに送信する場合、統合に関してAdobe Advertisingチームに問い合わせてください。

詳しくは、 [プライバシーレポート](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
