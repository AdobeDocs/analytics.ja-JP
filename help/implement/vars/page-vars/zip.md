---
title: 郵便番号
description: レポートスイートの設定で許可されている場合は、「郵便番号」ディメンションを手動で入力します。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# 郵便番号

この変 `zip` 数を使用すると、レポートスイート設定の「郵便番号」オプションで許可されている場合に、 [!UICONTROL 「郵便番号] 」ディメンションを手動で入力できます。 以前のバージョンのAdobe Analyticsでは、この変数は手動でのみ設定できました。通常、小売サイトの配送先情報を入力する場合です。 Adobe Analyticsが強化され、地域データを使用してこの変数を自動的に設定できるようになりました。 この変数は、設定されたヒットの後では保持されません。

> [!IMPORTANT] レポートスイー [!UICONTROL ト設定の「Zip] 」オプションが目的の値に設定されていることを確認します。 geozipを常に使用する場合は、この変 [!UICONTROL 数を使用] できません。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Adobe Experience Platform Launchの郵便番号

郵便番号は、Analytics拡張機能（グローバル変数）の設定中にも、ルールでも設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL Zip] 」セクションを探します。

郵便番号は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.zipおよびカスタムコードエディターの起動

変数 `s.zip` は、通常郵便番号を含む文字列ですが、最大50バイトの任意の値を含めることができます。

```js
s.zip = "84043";
```
