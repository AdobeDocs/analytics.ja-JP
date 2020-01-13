---
description: Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: グローバル変数
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# グローバル変数

Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。

これらの変数は、すべてのページ型ルールビーコンで実行されます。同じ効果を実現するには、[ページ型ルール](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md)を使用して、すべてのページで実行します。これらの変数は、[ダイレクト型ルール](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md)と[イベント型](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md)ルールでは実行されない可能性があります 。

## グローバル変数 - フィールドの説明 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png) **[!UICONTROL ／ツールを編集]**／**[!UICONTROL グローバル変数]**

| 要素 | 説明 |
|--- |--- |
| サーバー | 事前に定義済みの変数により、Adobe Analytics のサーバーディメンションが設定されます。「[ページ変数](/help/implement/js-implementation/page-variables/page-variables.md)」を参照してください。 |
| eVar | [eVar 変数](/help/implement/js-implementation/page-variables/evarn.md)は、カスタムコンバージョンレポートを作成するために使用します。 |
| prop | [Prop 変数](/help/implement/js-implementation/page-variables/propn.md)は、カスタムトラフィックレポートを作成するために使用します。 |
| 動的変数プレフィックス | 値の先頭に付ける特別なプレフィックスです。デフォルトのプレフィックスは「D=」です。「[動的変数](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/dynvars-overview.html)」を参照してください。 |
