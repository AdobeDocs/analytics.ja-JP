---
title: 郵便番号
description: レポートスイートの設定で許可されている場合は、「郵便番号」ディメンションを手動で入力します。
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# 郵便番号

`zip` 変数を使用すると、レポートスイート設定の「[!UICONTROL 郵便番号オプション]」で許可されている場合に、「郵便番号」ディメンションを手動で入力できます。以前のバージョンの Adobe Analytics では、この変数は手動でのみ設定できました。通常、小売サイトの配送先情報を入力する場合です。Adobe Analytics が強化され、地域データを使用してこの変数を自動的に設定できるようになりました。この変数は、設定されたヒットの後では保持されません。

>[!IMPORTANT]
>
> レポートスイート設定の「[!UICONTROL 郵便番号オプション]」が目的の値に設定されていることを確認します。[!UICONTROL geozip] を常に使用する場合は、この変数を使用できません。詳しくは、『管理者ユーザガイド』の「[一般的なアカウント設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)」を参照してください。

## Adobe Analytics 拡張機能を使用した郵便番号

郵便番号は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL zip] セクションを探します。

zip は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.zip

`s.zip` 変数は、通常、郵便番号を含む文字列ですが、最大 50 バイトの任意の値を含めることができます。

```js
s.zip = "84043";
```
