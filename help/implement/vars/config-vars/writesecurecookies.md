---
title: writeSecureCookies
description: AppMeasurement が Secure 属性を持つ cookie を設定することを許可します。
translation-type: tm+mt
source-git-commit: defb701d01747685a421b89a553f47efe40f1432
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 86%

---


# writeSecureCookies

この `writeSecureCookies` 変は、AppMeasurement が Analytics の [セキュリティで保護された cookie](https://en.wikipedia.org/wiki/Secure_cookie) を設定することを許可します。この設定は、AppMeasurement によって設定された訪問者 ID Cookie と、この `Util.CookieWrite()` メソッドを使用して設定した Cookie の両方に適用されます。AppMeasurement 2.18.0 以降が必要です。

>[!IMPORTANT]
>
> この `writeSecureCookies` 変数を有効にする場合は、サイト上のすべてのコンテンツが HTTPS 経由で安全に提供されていることを確認してください。この変数が有効になっており、ページに安全でないコンテンツが存在する場合、AppMeasurement は機能しません。

## Adobe Experience Platform Launch でのセキュア Cookie の書き込み

[!UICONTROL Adobe Analytics拡張機能の設定時に、セキュア] cookiesを作成する場合は、  Cookiesアコーディオンの下にあるチェックボックスを作成します。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. [!UICONTROL Cookies]アコーディオンを展開すると、[!UICONTROL 「セキュアcookieを書き込む]」チェックボックスが表示されます。

## AppMeasurement および Launch カスタムコードエディターの s.writeSecureCookies

この `s.writeSecureCookies` 変数は、AppMeasurement が cookie の作成時にセキュア属性を設定するかどうかを決定するブール値です。デフォルト値は `false` です。サイト上のすべてのコンテンツがセキュリティで保護されていて、AppMeasurement によって設定されるcookieにセキュリティで保護された属性を持たせたい場合は、この変数を `true` に設定します。

```js
s.writeSecureCookies = true;
```
