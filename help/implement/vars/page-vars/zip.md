---
title: zip
description: レポートスイートの設定で許可されている場合は、「郵便番号」ディメンションを手動で入力します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# zip

The `zip` variable allows you to manually populate the &#39;Zip Code&#39; dimension if the [!UICONTROL Zip Option] in report suite settings allows it. 以前のバージョンの Adobe Analytics では、この変数は手動でのみ設定できました。通常、小売サイトの配送先情報を入力する場合です。Adobe Analytics が強化され、地域データを使用してこの変数を自動的に設定できるようになりました。この変数は、設定されたヒットの後では保持されません。

>[!IMPORTANT] レポートスイー [!UICONTROL Zip Option] トの設定が目的の値に設定されていることを確認します。 You cannot use this variable if [!UICONTROL geo zip] is always used. 詳しくは、『管理者ユーザーガイド』の[一般的なアカウント設定](/help/admin/admin/general-acct-settings-admin.md)を参照してください。

## Adobe Experience Platform Launch での zip

zip は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Zip] section.

zip は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および Launch カスタムコードエディターでの s.zip

`s.zip` 変数は、通常、郵便番号を含む文字列ですが、最大 50 バイトの任意の値を含めることができます。

```js
s.zip = "84043";
```
