---
description: Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。
keywords: Dynamic Tag Management, グローバル変数, サーバー変数, evar, prop, 動的変数プレフィックス, 動的変数
seo-description: Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。
seo-title: グローバル変数
solution: Experience Cloud, Analytics, Dynamic Tag Management
title: グローバル変数
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# グローバル変数

Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。

これらの変数は、ページ型ルールのすべてのビーコンによって起動します。同様のことを実現する別の方法として、[ページ型ルール](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706)セットをすべてのページで起動させることもできます。これらの変数は、[ダイレクト型ルール](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09)と[イベント型](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC)ルールでは実行されない可能性があります 。

## グローバル変数 - フィールドの説明 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png) **[!UICONTROL ／ツールを編集]**／**[!UICONTROL グローバル変数]**

| 要素 | 説明 |
|--- |--- |
| サーバー | 事前に定義済みの変数により、Adobe Analytics のサーバーディメンションが設定されます。「[ページ変数](/help/implement/js-implementation/c-variables/page-variables.md)」を参照してください。 |
| eVar | [eVar 変数](/help/implement/js-implementation/c-variables/page-variables.md)は、カスタムコンバージョンレポートを作成するために使用します。 |
| prop | [Prop 変数](/help/implement/js-implementation/c-variables/page-variables.md)は、カスタムトラフィックレポートを作成するために使用します。 |
| 動的変数プレフィックス | 値の先頭に付ける特別なプレフィックスです。デフォルトのプレフィックスは「D=」です。「[動的変数](/help/implement/js-implementation/c-variables/dynvars-overview.md)」を参照してください。 |
