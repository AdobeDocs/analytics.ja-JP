---
title: writeSecureCookies
description: AppMeasurement が Secure 属性を持つ cookie を設定することを許可します。
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 76%

---

# writeSecureCookies

この `writeSecureCookies` 変は、AppMeasurement が Analytics の [セキュリティで保護された cookie](https://en.wikipedia.org/wiki/Secure_cookie) を設定することを許可します。この設定は、AppMeasurement によって設定された訪問者 ID Cookie と、この `Util.CookieWrite()` メソッドを使用して設定した Cookie の両方に適用されます。AppMeasurement 2.18.0 以降が必要です。

`writeSecureCookies` は、AppMeasurement JavaScript（`s_fid`、`s_cc`、`s_sq`）によって設定された Cookie にのみ適用されます。`https` の応答（`s_vi` と `s_ecid`）で設定された Cookie は、Adobe カスタマーサポートに問い合わせることで「セキュア」に設定できます。

Analytics の cookie について詳しくは、[こちら](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=ja)を参照してください。

>[!WARNING]
>
> この `writeSecureCookies` 変数を有効にする場合は、サイト上のすべてのコンテンツが HTTPS 経由で安全に提供されていることを確認してください。この変数が有効になっており、ページに安全でないコンテンツが存在する場合、データ収集が正しく機能しません。

## Web SDK でのセキュア cookie の使用

サイトで HTTPS プロトコルを使用している場合、Web SDK で設定されるすべての cookie に対してセキュア属性が設定されます。

## Adobe Analytics拡張機能を使用したセキュア Cookie の書き込み

「[!UICONTROL 安全な Cookie を書き込む]」は、Adobe Analytics 拡張機能を設定する際の [!UICONTROL Cookie] アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. [!UICONTROL Cookies] アコーディオンを展開すると、「[!UICONTROL 安全な Cookie を書き込む]」チェックボックスが表示されます。

## AppMeasurementーおよび Analytics 拡張機能のカスタムコードエディターの s.writeSecureCookies

この `s.writeSecureCookies` 変数は、AppMeasurement が cookie の作成時にセキュア属性を設定するかどうかを決定するブール値です。デフォルト値は `false` です。サイト上のすべてのコンテンツがセキュリティで保護されていて、AppMeasurement によって設定されるcookieにセキュリティで保護された属性を持たせたい場合は、この変数を `true` に設定します。

```js
s.writeSecureCookies = true;
```
